# ☁ AWS Application Load Balancer Deployment

## 📌 Project Overview

This project demonstrates the design and implementation of an **Application Load Balancer (ALB)** to distribute traffic across multiple EC2 instances, ensuring **high availability, fault tolerance, and traffic management**.

The setup includes:

* 3 EC2 instances
* 4 Target Groups
* Multiple hosted websites
* Health monitoring using CloudWatch

---


## 🛠 Technologies Used

* Amazon EC2 (3 Instances)
* Application Load Balancer
* Target Groups
* Amazon CloudWatch
* Security Groups
* Apache Web Server
* Linux (Amazon Linux 2)

---

## 🧱 Infrastructure Details

### 🖥 EC2 Instances

* M1 – Hosts 2 websites
* M2 – Hosts 2 websites
* M3 – Hosts 2 websites

Each server runs Apache web server.

---

### 🎯 Target Group Configuration

| Target Group | Mapped Instances |
| ------------ | ---------------- |
| T1           | M1               |
| T2           | M2               |
| T3           | M3               |
| T4           | M1, M2, M3       |

This configuration allows:

* Single-instance routing
* Multi-instance load distribution
* Path-based routing
* Fault tolerance testing

---

### ⚖ Application Load Balancer

* Listener: HTTP (Port 80)
* Configured routing rules:

  * Path-based routing
  * Target group forwarding
* Distributes incoming traffic across registered targets
* Performs health checks automatically

---

## 🔐 Security Configuration

* EC2 Security Group:

  * Allow HTTP (80) from ALB
  * Allow SSH (22) from My IP
* ALB Security Group:

  * Allow HTTP (80) from 0.0.0.0/0
* Health checks enabled for all target groups

---

## 📊 Monitoring & Logging

Used **Amazon CloudWatch** to:

* Monitor instance health
* Track CPU utilization
* Observe request count
* Analyze target health status
* Validate failover behavior during testing

---

## 🧪 Testing & Incident Simulation

Performed:

* Stopping one EC2 instance → Verified traffic reroutes automatically
* High traffic simulation → Observed load distribution
* Health check failure testing → Confirmed automatic removal of unhealthy targets
* Service restoration after instance restart

This validated:

* High Availability
* Fault Tolerance
* Automatic Recovery Behavior

---

## 📈 Key Features

* Traffic distribution across multiple servers
* Path-based routing
* Target group isolation
* Health-based routing
* Improved availability
* Basic resilience testing

---

## 🎯 Learning Outcomes

* Understanding ALB architecture
* Target Group configuration
* Path-based routing rules
* Health check configuration
* CloudWatch monitoring
* High availability design principles
* Incident troubleshooting basics

---

## 🔒 Security & Best Practices

* Restricted SSH access
* Backend instances not publicly exposed directly
* Load balancer acts as entry point
* Health checks configured properly

---

## 👩‍💻 Author

Shanmuga Priya.S
(Cloud & DevOps Learner)
