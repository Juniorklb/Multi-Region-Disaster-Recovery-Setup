#  AWS Multi-Region Disaster Recovery Setup

This project demonstrates how to design and implement a Multi-Region Disaster Recovery (DR) architecture on AWS. The goal is to ensure high availability, business continuity, and minimal downtime in the event of a regional failure.

---

## Architecture Overview

The setup includes a primary region hosting the live application and a secondary region ready to take over in case of failure. Key services used:

- **Amazon EC2** – Web server deployment in both regions
- **Amazon S3** – Cross-region replication for object storage
- **Amazon RDS** – Read replica or snapshot-based recovery
- **Amazon Route 53** – DNS health checks and failover routing
- **Amazon CloudWatch & SNS** – Monitoring and alerting
- **IAM & AMIs** – Security and image-based replication

---

##  Disaster Recovery Strategy

- **RTO (Recovery Time Objective):** < 15 minutes  
- **RPO (Recovery Point Objective):** Near real-time (with replication enabled)

### DR Types Implemented
- **Pilot Light:** Minimal standby infrastructure, scalable during failover
- **Warm Standby:** Resources pre-provisioned in the secondary region
- **Automated Failover:** Route 53 + CloudWatch for health monitoring and traffic redirection

---

## 🛠️ Setup Steps

1. **Deploy EC2 and RDS in Primary Region**
2. **Enable S3 Cross-Region Replication**
3. **Create RDS Read Replica or setup snapshot replication**
4. **Create AMIs and replicate EC2 setup manually or via IaC (e.g., CloudFormation)**
5. **Configure Route 53 with health checks and failover routing policies**
6. **Set up CloudWatch alarms and SNS topics for failover alerts**
7. **Test failover scenario by simulating a regional outage**

---

## 📊 Architecture Diagram

![Multi-Region DR Architecture](architecture-diagram.png) 

---

## 🧠 What I Learned

- How to build fault-tolerant cloud architecture
- Designing for high availability and resilience
- Hands-on with Route 53 DNS failover and health checks
- Managing cross-region replication and recovery strategies

---

## 🚀 Future Enhancements

- Automate full DR setup using Terraform or AWS CloudFormation
- Add continuous database syncing via DMS or AWS Backup
- Integrate with CI/CD for rapid re-deployment

---

##  Status

- Project Completed — Fully functional Multi-Region DR setup with successful failover test.

---

## 📁 Project Structure

