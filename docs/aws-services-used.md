# ☁️ AWS Services Used – 2-Tier AWS Architecture

## 📌 Overview

This project uses core AWS services to build a secure and scalable **2-tier architecture**.
The application layer runs on Amazon EC2, while the database layer runs on Amazon RDS inside a private subnet.

# 🧱 Services Used

## 1. Amazon VPC

### Purpose:

Provides a private and isolated network environment for AWS resources.

### Used For:

* Creating custom network boundaries
* Hosting subnets
* Managing routing and connectivity

### In This Project:

All resources are deployed inside a custom VPC.

---

## 2. Public Subnet

### Purpose:

Hosts resources that need direct internet access.

### In This Project:

* Amazon EC2 instance is placed here

### Why:

The application server must receive user traffic.

---

## 3. Private Subnet

### Purpose:

Hosts internal resources not exposed to the internet.

### In This Project:

* Amazon RDS database is placed here

### Why:

To improve security and restrict direct access.

---

## 4. Internet Gateway (IGW)

### Purpose:

Connects the VPC to the public internet.

### In This Project:

Used to allow users to access the EC2 instance.

### Attached To:

* VPC

---

## 5. Route Tables

### Purpose:

Control network traffic routing inside VPC.

### In This Project:

### Public Route Table:

* Sends internet traffic to Internet Gateway

### Private Route Table:

* Internal communication only

---

## 6. Amazon EC2

### Purpose:

Virtual server used to host applications.

### In This Project:

Used as:

* Web Server
* Application Server

### Example Uses:

* Apache / Nginx
* Node.js / Java / Python apps

---

## 7. Security Groups

### Purpose:

Acts as instance-level firewall.

### In This Project:

### EC2 Security Group:

* Allow HTTP (80)
* Allow HTTPS (443)
* Allow SSH (22) from trusted IP

### RDS Security Group:

* Allow DB port only from EC2

---

## 8. Amazon RDS

### Purpose:

Managed relational database service.

### In This Project:

Stores application data.

### Supported Engines:

* MySQL
* PostgreSQL
* MariaDB
* SQL Server

---

# 🔄 How Services Work Together

1. User accesses website
2. Request enters via Internet Gateway
3. Route table forwards traffic to Public Subnet
4. EC2 processes request
5. EC2 connects privately to RDS database
6. Response returns to user

---

# 🎯 Summary Table

| AWS Service      | Role in Project       |
| ---------------- | --------------------- |
| Amazon VPC       | Private network       |
| Public Subnet    | Hosts EC2             |
| Private Subnet   | Hosts RDS             |
| Internet Gateway | Internet connectivity |
| Route Tables     | Traffic routing       |
| Amazon EC2       | Application server    |
| Security Groups  | Firewall control      |
| Amazon RDS       | Managed database      |

---

# 📌 Conclusion

These AWS services together create a secure, practical, and scalable 2-tier cloud architecture suitable for learning, portfolios, and real-world fundamentals.
