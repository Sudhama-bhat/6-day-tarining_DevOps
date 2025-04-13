# DevOps and AWS Introduction - README

## 📅 Session Summary

### No assignment was given on this day.

---

## 🧠 Day 1: Introduction to DevOps

### What is DevOps?

DevOps is a **cultural and technical approach** that combines software development (Dev) and IT operations (Ops) to enable **faster, more reliable, and more collaborative software delivery**.

- DevOps emphasizes:
  - **Automation**
  - **Collaboration**
  - **Integration**

### Why DevOps?

- **Breaks silos** between Dev and Ops
- **Reduces delays, miscommunications, and bottlenecks**
- **Improves speed and quality of software deployment**

### Key Concepts in DevOps

- **CI/CD (Continuous Integration & Continuous Deployment)**:
  - Enables quick feature releases and faster bug fixes
- **DevOps Pipeline**:
  - Automated workflow for building, testing, and deploying code

### Common DevOps Tools

- **Version Control**: Git
- **CI/CD**: Jenkins, GitHub Actions
- **Containerization**: Docker
- **Monitoring**: Various tools for reliability

---

## 💼 4 Factors for Successful Business with DevOps

1. Faster delivery of services  
2. High quality without compromise  
3. Reduced spending  
4. High availability of services

---

## ☁️ Introduction to Cloud

### What is Cloud?

Cloud refers to **remote services** hosted in **data centers** (collections of servers).

### Types of Cloud

- **Public Cloud**
- **Private Cloud**

### Cloud Service Models

1. **IaaS** – Infrastructure as a Service  
2. **PaaS** – Platform as a Service  
3. **SaaS** – Software as a Service

---

## 🌐 AWS Overview

### Key AWS Features

- Autoscaling services  
- High availability (up to **99.11%**)  
- On-demand scalability and flexibility

### Important AWS Services for Us

1. **Compute**:
   - EC2 (Elastic Compute Cloud) – for application deployment
2. **Containers**:
   - EKS (Elastic Kubernetes Service)
3. **Databases**:
   - DynamoDB (NoSQL)
   - RDS (Relational Database Service)

---

## 🖥️ EC2 (Elastic Compute Cloud)

When configuring EC2 instances:

- Choose:
  - Operating System
  - Server Configuration
  - Storage Capacity

---

## 🔐 Linux Permissions

To grant permissions in **Amazon Linux**, use:

```bash
visudo
```

---

## 🐧 Linux Server Families

### 1. **Red Hat Family**

- Amazon Linux, Oracle Linux, SUSE Linux, Red Hat Linux
- Use `httpd` (Hyper Text Transfer Protocol Daemon)

### 2. **Debian Family**

- Ubuntu OS, Debian OS
- Use **Apache** or **Nginx** server

---

## 📦 Package Management (Red Hat Family)

To install packages, use:

```bash
yum
# y - yellow
# u - update
# m - modify
```

### Useful Commands

```bash
which httpd             # Check if httpd is installed
service httpd status    # Check if httpd is running

# If httpd is not running:
service httpd start
```

---

*End of Session Summary.*