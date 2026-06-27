# 🛠️ Execution Workflow

This document outlines the complete workflow for provisioning an Amazon S3 bucket on AWS using Terraform. It covers each stage of the Infrastructure as Code (IaC) lifecycle, from authentication and project setup to infrastructure deployment, verification, state management, and cleanup.

---

# I. AWS CLI Configuration

Before Terraform can provision resources on AWS, it must authenticate with your AWS account using the AWS CLI.

Run the following command to verify that the configured AWS credentials are valid and to confirm the identity of the authenticated IAM user or role.

```bash
aws sts get-caller-identity
```

Successful authentication ensures Terraform has the required permissions to provision infrastructure.

---

# II. Project Structure Setup

Organize the Terraform project into separate configuration files to improve readability, maintainability, and scalability.

```text
terraform-aws-s3-bucket/
│
├── architecture-diagram.md
├── main.tf
├── variables.tf
├── terraform.tfvars
├── outputs.tf
├── workflow.md
├── code_explaination.md
├── .gitignore
└── README.md
```

The project structure separates infrastructure configuration, variable declarations, variable values, outputs, documentation, and architecture into dedicated files, making the project easier to understand and maintain.

---

# III. Provider Configuration

Configure the AWS Provider by defining the provider source, version constraint, and deployment region.

The provider configuration establishes communication between Terraform and AWS, enabling Terraform to provision and manage cloud resources.

---

# IV. Variables Definition

Declare reusable input variables for the AWS Region and the Amazon S3 bucket name.

Using variables makes the Terraform configuration flexible, reusable, and easier to maintain across multiple environments.

---

# V. Variable Values Configuration

Assign values to the declared variables using the `terraform.tfvars` file.

Separating configuration values from the Terraform code allows the same infrastructure configuration to be reused without modifying the source files.

---

# VI. Amazon S3 Bucket Resource Creation

Define an Amazon S3 bucket resource in the Terraform configuration.

The bucket name is referenced through an input variable, allowing the same configuration to create different buckets by changing only the variable values.

---

# VII. Output Configuration

Define output values that display important information after Terraform provisions the infrastructure.

Outputs provide an easy way to retrieve resource attributes without manually searching within AWS.

---

# VIII. Terraform Initialization

Initialize the Terraform working directory before provisioning any infrastructure.

```bash
terraform init
```

This command downloads the required provider plugins, prepares the working directory, and generates the dependency lock file.

---

# IX. Configuration Validation and Formatting

Validate the Terraform configuration to identify syntax or configuration errors.

```bash
terraform validate
```

Format the Terraform configuration according to HashiCorp's recommended coding style.

```bash
terraform fmt
```

Validating and formatting the configuration helps ensure consistency and reduces the likelihood of deployment errors.

---

# X. Preview Changes

Generate an execution plan to preview the infrastructure changes before applying them.

```bash
terraform plan
```

Reviewing the execution plan allows you to verify the resources Terraform intends to create, modify, or destroy before any changes are made.

---

# XI. Apply Configuration

Provision the infrastructure using Terraform.

```bash
terraform apply
```

After reviewing the execution plan, confirm the operation by entering **yes**. Terraform then provisions the Amazon S3 bucket and updates the infrastructure state.

---

# XII. AWS Console Verification

After the deployment completes, verify that the Amazon S3 bucket has been successfully created by checking the AWS Management Console.

This confirms that Terraform provisioned the infrastructure in the intended AWS Region.

---

# XIII. Terraform State Management

View the resources currently managed by Terraform.

```bash
terraform state list
```

Inspect the detailed state of the Amazon S3 bucket.

```bash
terraform state show aws_s3_bucket.my_bucket
```

Terraform state management enables Terraform to track infrastructure resources and safely manage future updates.

---

# XIV. Output Display

Display the output values defined in the Terraform configuration.

```bash
terraform output
```

This command provides quick access to the values defined in the project's output configuration after the infrastructure has been provisioned.

---

# XV. Infrastructure Cleanup

Remove all infrastructure managed by Terraform.

```bash
terraform destroy
```

After confirming the execution plan by entering **yes**, Terraform deletes the Amazon S3 bucket and removes it from the Terraform state, completing the infrastructure lifecycle.

---

# 📂 Source Code

The complete Terraform configuration files used in this project are available in this repository.

**GitHub Repository:**  
https://github.com/Knandwani07/terraform-aws-s3-bucket

The repository includes all Terraform configuration files, project documentation, architecture diagram, and supporting resources required to reproduce this project.
