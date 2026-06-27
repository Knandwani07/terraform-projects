# 📄 Terraform Configuration Explanation

This document explains each Terraform configuration file used in this project and describes how they work together to provision an Amazon S3 bucket on AWS.

---

# 📁 Project Files

The project consists of the following Terraform configuration files:

* `main.tf`
* `variables.tf`
* `terraform.tfvars`
* `outputs.tf`

Each file has a specific responsibility, making the project modular, readable, and easier to maintain.

---

# 📄 main.tf

The `main.tf` file is the core of the Terraform project. It defines the infrastructure that Terraform will provision on AWS.

In this project, `main.tf` performs the following tasks:

* Defines the Terraform block.
* Specifies the required AWS Provider.
* Configures the AWS Provider.
* Creates the Amazon S3 bucket resource.

### Terraform Block

The Terraform block specifies the providers required by the project and their version constraints.

#### Purpose

* Initializes Terraform.
* Downloads the required provider.
* Ensures version compatibility.

### Required Provider

The required provider tells Terraform which cloud provider to use.

#### Components

* **source** → Specifies the provider source.
* **hashicorp/aws** → Official AWS Provider maintained by HashiCorp.
* **version = "~> 6.0"** → Uses AWS Provider version 6.x while preventing automatic upgrades to the next major version.

### Provider Block

The provider block configures the AWS Provider.

#### Purpose

* Connects Terraform to AWS.
* Specifies the deployment region.

In this project, the region is retrieved using the input variable:

```hcl
region = var.aws_region
```

This allows the same Terraform configuration to be reused across different AWS Regions.

### Resource Block

The resource block defines the infrastructure Terraform will create.

In this project, the resource is:

* Amazon S3 Bucket

#### Components

* **resource** → Declares an infrastructure resource.
* **aws_s3_bucket** → Amazon S3 Bucket resource type.
* **my_bucket** → Local resource name.
* **bucket = var.bucket_name** → Assigns the bucket name from the input variable.

---

# 📄 variables.tf

The `variables.tf` file declares all input variables used throughout the project.

Instead of hardcoding values inside the Terraform configuration, variables make the project reusable and configurable.

### Variables Used

## aws_region

Stores the AWS Region where the infrastructure will be deployed.

### bucket_name

Stores the name of the Amazon S3 bucket.

### Variable Attributes

Every variable contains:

* **description** → Explains the purpose of the variable.
* **type** → Specifies the accepted data type.
* **default** *(optional)* → Provides a default value if no value is supplied.

Using variables improves:

* Reusability
* Flexibility
* Maintainability

---

# 📄 terraform.tfvars

The `terraform.tfvars` file stores the values assigned to the variables declared in `variables.tf`.

Instead of modifying the Terraform configuration every time a deployment changes, only the values inside this file need to be updated.

### Example Values

* AWS Region
* Amazon S3 Bucket Name

### Benefits

* Separates configuration from infrastructure code.
* Makes the project reusable.
* Simplifies deployments across different environments.

---

# 📄 outputs.tf

The `outputs.tf` file defines values that Terraform displays after successfully provisioning the infrastructure.

Outputs provide quick access to important information about the deployed resources.

### Outputs Used

## bucket_name

Displays the name of the created Amazon S3 bucket.

## bucket_arn

Displays the Amazon Resource Name (ARN) of the bucket.

### Benefits

* Easy access to deployed resource information.
* Simplifies referencing resources in larger Terraform projects.
* Improves automation and scripting.

---

# 🔄 How the Files Work Together

The Terraform configuration files work together in the following sequence:

```text
terraform.tfvars
        │
        ▼
variables.tf
        │
        ▼
main.tf
        │
        ▼
AWS Provider
        │
        ▼
Amazon S3 Bucket
        │
        ▼
outputs.tf
```

### Workflow Explanation

1. Variable values are read from `terraform.tfvars`.
2. Variables are declared in `variables.tf`.
3. `main.tf` uses these variables to configure the AWS Provider and create the Amazon S3 bucket.
4. Terraform provisions the infrastructure on AWS.
5. `outputs.tf` displays important information about the deployed resource.

---

# 📚 Key Concepts

Through these configuration files, the project demonstrates:

* Infrastructure as Code (IaC)
* Provider Configuration
* Resources
* Variables
* Variable Values
* Outputs
* Infrastructure Provisioning
* Project Organization
* Reusable Terraform Configurations

---

# 📌 Summary

Each Terraform configuration file has a specific responsibility. By separating providers, resources, variables, values, and outputs into dedicated files, the project becomes easier to understand, maintain, and scale. This modular approach follows Terraform best practices and provides a solid foundation for building more complex cloud infrastructure projects.
