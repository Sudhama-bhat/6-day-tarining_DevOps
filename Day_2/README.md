# DevOps and AWS - Day 2

## 📅 Session Summary

---

## 🚀 Day 2: Launching EC2 Instance on AWS

### Objective

Today, we learned how to create an AWS account and launch an EC2 (Elastic Compute Cloud) instance, which is a virtual server in Amazon's cloud platform.

This is an essential step in cloud computing and DevOps, allowing us to host applications, run services, or practice deployments in an isolated environment.

---

## 🛠️ Steps to Launch an EC2 Instance

1. Log in to your [AWS Management Console](https://aws.amazon.com/console/)
2. Navigate to **EC2 Dashboard** under the **Compute** section.
3. Click **"Launch Instance"**
4. Give your instance a **Name**
5. Select an **Instance Type** (e.g., t2.micro for Free Tier)
6. Choose an **Operating System** (Amazon Linux, Ubuntu, etc.)
7. Create or select an existing **Key Pair** (required for SSH access)
8. Configure the **Security Group** (allow at least SSH - port 22)
9. Click **"Launch Instance"**
10. Wait until the instance status shows **Running**
11. Click on the instance and then on **"Connect"**
12. Copy the **Public IPv4 Address**
13. Use **PuTTY** (Windows) or **Terminal** (Mac/Linux) to connect:
    - PuTTY:
      - Hostname: `ec2-user@<public-ip>`
      - Load the `.ppk` private key file under SSH > Auth
    - Terminal (Linux/Mac):
      ```bash
      chmod 400 your-key.pem
      ssh -i "your-key.pem" ec2-user@<public-ip>
      ```
14. Confirm connection: You are now logged into your EC2 instance! 🎉

---

## 🧠 Why This Matters

- **Real-World Use Case**: Most modern applications run on cloud platforms like AWS.
- **Hands-On Practice**: Working with EC2 provides foundational experience with cloud computing.
- **DevOps Integration**: These instances are later used in automated pipelines for CI/CD processes.

---

## 🔐 Key Notes

- Always **secure your key pair** (.pem or .ppk file).
- Only open necessary ports in your **Security Group** for better security.
- Amazon Linux default username: `ec2-user`
- Ubuntu default username: `ubuntu`

---

*End of Day 2 Summary*