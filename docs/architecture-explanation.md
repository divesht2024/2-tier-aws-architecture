# 🏗️ Architecture Explanation – 2-Tier AWS Architecture

## 📌 Overview

This project demonstrates a **2-tier architecture on AWS** where the application layer and database layer are separated into different tiers for better security, scalability, and maintainability.

The architecture uses:

* **Tier 1 – Application Layer:** Amazon EC2 instance in a Public Subnet
* **Tier 2 – Database Layer:** Amazon RDS instance in a Private Subnet

This setup follows common cloud best practices by exposing only the application server to the internet while keeping the database private.

---

## 🧱 Architecture Components

### 1. Amazon VPC

A Virtual Private Cloud (VPC) provides an isolated network environment for AWS resources.

Used to create:

* Public subnet
* Private subnet
* Route tables
* Security boundaries

---

### 2. Public Subnet

The public subnet hosts resources that need internet access.

Resources deployed:

* Amazon EC2 instance (Web/Application Server)

The subnet route table contains a route to the Internet Gateway.

---

### 3. Private Subnet

The private subnet hosts sensitive backend resources.

Resources deployed:

* Amazon RDS Database

This subnet does not allow direct internet access.

---

### 4. Internet Gateway (IGW)

The Internet Gateway allows communication between the VPC and the public internet.

Used for:

* User traffic reaching the EC2 instance
* Outbound internet access for public resources

---

### 5. Amazon EC2

EC2 is used as the application server.

Responsibilities:

* Host website / application
* Process user requests
* Connect to database

---

### 6. Amazon RDS

Amazon RDS is the managed relational database service.

Responsibilities:

* Store application data
* Handle database backups
* Improve availability using Multi-AZ (optional)

---

### 7. Security Groups

Security Groups act as virtual firewalls.

Typical rules:

**EC2 Security Group**

* Allow HTTP (80) from internet
* Allow HTTPS (443) from internet
* Allow SSH (22) from trusted IP only

**RDS Security Group**

* Allow MySQL/PostgreSQL port only from EC2 Security Group

---

## 🔄 Traffic Flow

1. User opens website in browser
2. Request reaches Internet Gateway
3. Traffic is routed to EC2 instance in Public Subnet
4. EC2 application processes request
5. EC2 connects securely to RDS in Private Subnet
6. Response is sent back to user

---

## 🔐 Security Design

* Database is not publicly accessible
* Only EC2 can communicate with RDS
* SSH access can be restricted by IP
* Separate subnet design improves isolation

---

## 🎯 Key Learning Outcomes

By building this project, the following AWS concepts are practiced:

* VPC Networking
* Public vs Private Subnets
* EC2 Deployment
* RDS Connectivity
* Security Groups
* Basic Cloud Architecture Design

---

## 📌 Conclusion

This 2-tier AWS architecture is a strong beginner-to-intermediate cloud project that demonstrates networking, compute, and database integration using AWS best practices.
