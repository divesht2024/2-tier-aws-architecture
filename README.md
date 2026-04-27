# 🚀 2-Tier AWS Architecture on AWS

## 📌 Project Overview

This project demonstrates the design and implementation of a 2-tier architecture on AWS**.

The infrastructure separates the **application layer** and **database layer** into different network tiers to improve security, maintainability, and performance.

* **Tier 1 – Web/Application Layer:** Amazon EC2 deployed in a Public Subnet
* **Tier 2 – Database Layer:** Amazon RDS deployed in a Private Subnet

This architecture follows cloud best practices by allowing public access only to the application server while keeping the database isolated from direct internet exposure.

---

## ☁️ AWS Services Used

| Service          | Purpose                            |
| ---------------- | ---------------------------------- |
| Amazon VPC       | Isolated private network           |
| Public Subnet    | Hosts internet-facing EC2 instance |
| Private Subnet   | Hosts internal RDS database        |
| Internet Gateway | Enables internet access            |
| Route Tables     | Controls network traffic           |
| Amazon EC2       | Application / Web server           |
| Amazon RDS       | Managed relational database        |
| Security Groups  | Firewall and access control        |

---

## 🔄 Request Flow
```text
User Browser
   ↓
Internet
   ↓
Internet Gateway
   ↓
EC2 Instance (Application Layer)
   ↓
Amazon RDS (Database Layer)
   ↓
Response to User
```
---

## 🔐 Security Architecture

✔ Database deployed in private subnet
✔ No direct public access to RDS
✔ Security Groups restrict inbound/outbound traffic
✔ SSH access can be limited to trusted IPs only
✔ Application and database layers are logically separated

---

## ⚙️ Key Features Implemented

* Custom Amazon VPC
* Public and Private Subnet Design
* EC2 Web/Application Hosting
* RDS Database Connectivity
* Secure Network Segmentation
* Internet Gateway Integration
* Controlled Security Group Rules

---

## 📚 Skills Demonstrated

* AWS Cloud Architecture Design
* Networking Fundamentals (VPC/Subnets)
* Compute Deployment (EC2)
* Database Integration (RDS)
* Security Best Practices
* Troubleshooting & Connectivity
* Cloud Project Documentation

---

## 📸 Screenshots

Store screenshots in the `/screenshots` folder:

* EC2 Running State
* RDS Instance Dashboard
* VPC Configuration
* Security Group Rules
* Successful DB Connection

---

## 📂 Repository Structure
```text
2-tier-aws-architecture/
│── README.md
│── architecture/
│   ├── 2-tier-aws-architecture.drawio
│   └── 2-tier-aws-architecture.png
│── screenshots/
│── docs/
│   ├── architecture-explanation.md
│   └── aws-services-used.md
```

---

## 🎯 Project Outcome

This project demonstrates how to deploy a secure 2-tier workload on AWS using industry-standard architecture principles. It is an excellent foundational project for Cloud Engineer, DevOps Engineer, and Solutions Architect portfolios.

---

## 👨‍💻 Author

DIVESH M. TAYADE
AWS | Cloud Engineer | DevOps Enthusiast
