# AWS Custom VPC with Terraform

This project provisions a secure, custom Virtual Private Cloud (VPC) architecture in Amazon Web Services (AWS) using Terraform. It follows cloud security best practices by separating workloads into public and private subnets.

---

## 🏗️ Architecture Overview

The Terraform script provisions the following resources:
* **Custom VPC** (`10.0.0.0/16`) with DNS support and hostnames enabled.
* **Public Subnet** (`10.0.1.0/24`) in `us-east-1a` with auto-assigned public IP addresses.
* **Private Subnet** (`10.0.2.0/24`) in `us-east-1b` for isolated workloads.
* **Internet Gateway (IGW)** attached to the VPC to enable internet access for public resources.
* **Public Route Table** routing internet-bound traffic (`0.0.0.0/0`) through the Internet Gateway.
* **Route Table Association** linking the public subnet to the public route table.

---

## 🛠️ Prerequisites

Make sure you have the following installed on your local machine:
* [Terraform](https://www.developer.hashicorp.com/terraform/downloads)
* [AWS CLI](https://aws.amazon.com/cli/) (configured with your AWS credentials using `aws configure`)

---

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/aws-custom-vpc-terraform.git](https://github.com/YOUR_USERNAME/aws-custom-vpc-terraform.git)
   cd aws-custom-vpc-terraform
   terraform init
   terraform plan
   terraform apply -auto-approve
