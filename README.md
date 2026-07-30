
# AWS Web-Tier Infrastructure Automation (Terraform)

This repository contains the Terraform configuration files required to deploy a fully automated, highly available Web-tier architecture on AWS. By using Infrastructure as Code (IaC), this project ensures consistent, repeatable, and documented environment setups.

### Automated Components:
* **Networking (`vpc.tf`):** Custom VPC with Public subnets across multiple AZs, and Internet Gateways.
* **Security (`sg.tf`, `iam.tf`):** Granular Security Group rules for tier-to-tier isolation and IAM roles for EC2-to-S3 access.
* **Compute (`web_asg.tf`):** Auto Scaling Groups for the Web (Frontend) tiers.
* **Load Balancing (`applb.tf`):** Application Load Balancers to distribute traffic across the compute clusters.
* **Storage (`s3.tf`):** S3 buckets for static assets and application logs.

## 🛠 Tech Stack
* **IaC Tool:** Terraform (HCL)
* **Cloud Provider:** AWS
* **Bootstrapping:** Shell Scripting (`apache.sh`)
* **Architecture:** Web-Tier

## 📂 File Definitions
* `main.tf`: Provider configuration and core resource orchestration.
* `apache.sh`: User Data script to automate web server installation and app deployment.
* `keypair.tf`: Manages SSH access keys for secure instance management.
* `output.tf`: Defines the endpoints (ALB DNS, RDS Endpoint) generated after deployment.

## 🚀 How to Deploy
1. **Initialize:** `terraform init` to download providers.
2. **Plan:** `terraform plan` to review the infrastructure changes.
3. **Apply:** `terraform apply` to provision the resources on AWS.
