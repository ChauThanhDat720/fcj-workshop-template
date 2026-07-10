---
title : "Introduction"
date : 2024-01-01 
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---

#### System Architecture

![Rookwork AWS Architecture](/images/5-Workshop/rookwork_aws_architecture.jpg)

The system operates through the following main processing flows:

**① DNS Resolution & CDN:**
- **Route 53** resolves the domain name and routes users to the system.
- **CloudFront** distributes the static frontend from **FE Static S3**, combined with **AWS WAF** to protect against web exploits.

**② Routing & Compute Backend:**
- API traffic flows through the **Internet Gateway** → **ALB (Application Load Balancer)** → load-balanced to **EC2 instances** placed inside *Private Subnets*.
- EC2 accesses the internet for outbound calls via the **NAT Gateway** (step 6.1 — Route to Internet).

**③ Database & Storage:**
- Business data is stored on **Amazon RDS PostgreSQL**, deployed in a **Multi-AZ** setup (step 7 — DB Replication) for disaster recovery.
- File attachments are written by EC2 to **Amazon S3** via the **S3 Gateway Endpoint** using Internal Routing (steps 8 & 9) — bypassing the public internet and reducing internal bandwidth costs to zero.
- Users download files directly via **Direct File Access** (step 10).

**④ Shared Services:**
- **Amazon SES** delivers email notifications (e.g., workspace invitations) triggered from EC2 (steps 6.2 & 6.3).
- **AWS Certificate Manager (ACM)** manages SSL/TLS certificates, and **AWS IAM** controls system-wide permissions.