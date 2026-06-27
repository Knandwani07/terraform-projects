# Infrastructure as Code: Deploying AWS S3 Bucket with Terraform 🏗️

Provision an Amazon S3 bucket on AWS using Terraform while learning the fundamentals of **Infrastructure as Code (IaC)**.

---

## 📖 About this project

This project demonstrates how to provision and manage an Amazon S3 bucket using Terraform. Instead of manually creating cloud resources through the AWS Management Console, the infrastructure is defined in code, making deployments consistent, repeatable, and easier to maintain.

The project introduces the core concepts of Terraform, including providers, variables, outputs, state management, and Infrastructure as Code (IaC) best practices.

---

## 🎯 Project Objectives

- Implement Infrastructure as Code (IaC) using Terraform.
- Provision an Amazon S3 bucket on AWS.
- Understand Terraform project structure.
- Learn Terraform state management.
- Automate cloud infrastructure provisioning.

---

## 🛠️ Technologies Used

- Terraform
- Amazon Web Services (AWS)
- Amazon S3
- AWS CLI

---

## 📂 Project Structure

```text
terraform-aws-s3-bucket/
│
├── architecture.md            # Project architecture diagram with architectural components
├── main.tf                    # Defines the AWS provider and S3 bucket resource
├── variables.tf               # Declares reusable input variables
├── terraform.tfvars           # Stores values assigned to input variables
├── outputs.tf                 # Displays output values after deployment
├── workflow.md                # Step-by-step implementation guide
├── code_explaination.md       # Detailed explanation of each Terraform configuration file 
├── .gitignore                 # Excludes generated and sensitive files
└── README.md                  # Project overview and documentation
```

### File Description

| File | Description |
|------|-------------|
| **architecture.md** | Explains the project architecture, deployment flow, and the interaction between Terraform components and AWS services. |
| **main.tf** | Defines the Terraform configuration, including the AWS provider and the Amazon S3 bucket resource. |
| **variables.tf** | Declares reusable input variables, making the configuration flexible and easier to maintain. |
| **terraform.tfvars** | Stores values assigned to the declared variables without modifying the source code. |
| **outputs.tf** | Defines output values displayed after successful infrastructure deployment. |
| **code_explaination.md** | Provides a detailed explanation of each Terraform configuration file, including main.tf, variables.tf, terraform.tfvars, and outputs.tf, along with how they work together to provision the infrastructure. |
| **workflow.md** | Documents the complete implementation process, Terraform commands, explanations, and deployment workflow. |
| **.gitignore** | Prevents Terraform-generated files, state files, and other unnecessary files from being committed to Git. |
| **README.md** | Provides an overview of the project, prerequisites, technologies, and project documentation. |

---

## 📋 Prerequisites

Before running this project, ensure you have:

- AWS Account
- AWS CLI installed and configured
- Terraform installed
- IAM permissions to create Amazon S3 buckets

---

## 📚 Concepts Covered

- Infrastructure as Code (IaC)
- Terraform Workflow
- AWS Provider Configuration
- Variables
- Outputs
- Terraform State Management
- AWS CLI Authentication
- Amazon S3
- Infrastructure Automation

---

## 📖 Implementation Guide

The complete implementation process, including Terraform commands, explanations, screenshots, and deployment workflow, is available in **WORKFLOW.md**.

---

## 🤝 Let's Connect

- 💼 **LinkedIn:** https://www.linkedin.com/in/khushi-nandwani/
- 💻 **GitHub:** https://github.com/Knandwani07
- ✍️ **Dev Community:** https://dev.to/khushi_nandwani07
- 📝 **Medium:** https://medium.com/@khushinandwanii
- 🌐 **Portfolio:** https://main.d1n4wt6uo5bfx6.amplifyapp.com/

---

⭐ **If you found this project helpful, consider giving it a star!**
