
# 📘 DevOps Training - Day 3

## 🧠 Topics Covered

### ✅ Terraform – Infrastructure as Code (IaC)
Terraform is an **IaC tool** used to automate cloud resource creation like EC2, VPCs, Subnets, Databases, Load Balancers, etc.

#### 🔧 What we need to do:
1. **Install Terraform** on your Linux machine.
2. **Set the Terraform path** in your environment variables.
3. **Install AWS CLI** and configure credentials using:
   ```bash
   aws configure
   ```

---

### 📂 Terraform Script Structure

Terraform scripts use specific blocks:

- **provider**: To define which cloud to use (`aws`, `azure`, etc.)
- **resource**: To define the specific resource (e.g., EC2, VPC)
- **variable**: To allow dynamic values in the script
- **output**: To print values like IP addresses or resource IDs

---

### 🖥️ EC2 Instance Terraform Script (`ec2.tf`)

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "web" {
  ami           = "ami-02f624c08a83ca16f"
  instance_type = "t2.micro"
  key_name      = "Nidhi-server"
  tags = {
    Name = "Sudhama"
  }
}
```

#### 📝 EC2 Parameters Required:
1. Amazon Machine Image (AMI)
2. Instance Type
3. Key Pair Name
4. Storage (optional but recommended)
5. Instance Name (via `tags`)

---

### 📜 Terraform CLI Commands

| Command              | Description |
|----------------------|-------------|
| `terraform init`     | Initializes Terraform and downloads the necessary providers |
| `terraform validate` | Checks for syntax errors in the script |
| `terraform plan`     | Previews the resources to be created |
| `terraform apply`    | Creates resources on AWS |
| `terraform destroy`  | Deletes all resources created by Terraform |

> ⚠️ `terraform.tfstate` file stores the state of infrastructure — keep it safe and secure.

---

## 🔐 IAM in AWS
IAM (Identity and Access Management) is used to control access to AWS services. When using Terraform, ensure proper permissions using:
- Access keys
- IAM roles
- Policies

---

## 🐳 Docker – Containerization

Docker is a tool used for **OS-level virtualization**. It helps in:
- Reducing cost
- Creating platform-independent applications
- Making applications portable
- Efficient resource utilization

---

### 🏗️ Why Docker?

- Supports **microservices architecture**
- Containers are lightweight, portable, and isolated
- Can run on any environment with Docker installed

---

### 🆚 Monolithic vs Microservices

| Feature          | Monolithic Architecture              | Microservices Architecture                  |
|------------------|----------------------------------------|---------------------------------------------|
| Structure        | All modules in one application         | Independent services for each module        |
| Failure Impact   | One crash affects whole application    | Only that specific service is affected      |
| Scalability      | Harder to scale                        | Easily scalable per service                 |
| Cost             | Lower (initially)                      | Higher due to multiple servers              |
| Maintenance      | Difficult as it grows                  | Easier and modular                          |

---

### 🧩 Docker in Microservices

- Each service has:
  - Its **own Dockerfile**
  - A separate **Docker image**
  - Runs inside an **independent container**

---

### 🛠️ Final Summary

- Use Terraform to **automate cloud infrastructure**
- Use Docker to **run modular, scalable, and portable apps**
- Combine both for a **powerful DevOps workflow**
- Store your Terraform state files securely
- Use IAM for fine-grained access control

---

*End of Day 3 Notes*
```