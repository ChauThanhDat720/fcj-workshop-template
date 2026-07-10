---
title: "Week 7 Worklog"
date: 2026-04-17
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

{{% notice info %}}
🚀 **Rookwork Project Start:** From Week 7 (27/05/2026), alongside deep-diving into AWS services, the **Rookwork** project — a multi-platform team collaboration management system — officially began development.
{{% /notice %}}

### Week 7 Objectives:

* Learn AWS IoT Core: device connection, MQTT protocol, topics, and rules.
* Understand how to ingest sensor data from edge devices into the AWS cloud.
* Begin **Rookwork** project development: set up project structure, define modules, and plan system architecture.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - AWS IoT Core overview: device registry, message broker, rules engine <br> - MQTT protocol: topics, QoS levels, retain messages | 27/05/2026 | 27/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - IoT Core Thing creation and certificates <br> - Device policies for secure MQTT connection | 28/05/2026 | 28/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Practice:** <br>&emsp; + Create IoT Thing with certificate <br>&emsp; + Simulate device publishing MQTT messages <br>&emsp; + Subscribe to topics in MQTT test client | 29/05/2026 | 29/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - IoT Rules Engine: SQL-like rule queries <br> - Route messages to S3, Lambda, DynamoDB | 30/05/2026 | 30/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Practice:** <br>&emsp; + Create IoT rule to forward data to S3 <br>&emsp; + Trigger Lambda from IoT rule <br>&emsp; + End-to-end data ingestion test | 31/05/2026 | 31/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

---

**Rookwork Project — Phase 1: Architecture Design & AWS Infrastructure Setup**

| Day | Rookwork Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Design the overall AWS architecture diagram for Rookwork <br> - Identify required services: EC2, RDS, S3, SES, CloudFront, WAF, Route 53 | 27/05/2026 | 27/05/2026 | |
| 3 | - Initialize Amazon VPC: configure Public/Private Subnets, Internet Gateway <br> - Set up NAT Gateway for Private Subnet outbound traffic | 28/05/2026 | 28/05/2026 | |
| 4 | - Configure AWS IAM: create roles and policies for EC2, RDS, S3 <br> - Set up Security Groups for each tier (ALB, EC2, RDS) | 29/05/2026 | 29/05/2026 | |
| 5 | - Configure Amazon Route 53: register hosted zone, create DNS records <br> - Set up AWS Certificate Manager (ACM) for SSL/TLS | 30/05/2026 | 30/05/2026 | |
| 6 | - **Review & finalize Phase 1:** <br>&emsp; + Verify all VPC, subnet, and routing table configurations <br>&emsp; + Validate IAM permissions and Security Groups <br>&emsp; + Plan detailed tasks for Phase 2 | 31/05/2026 | 31/05/2026 | |

### Week 7 Achievements:

* Successfully completed: AWS IoT Core overview: device registry, message broker, rules engine

* Successfully completed: MQTT protocol: topics, QoS levels, retain messages

* Successfully completed: IoT Core Thing creation and certificates

* Successfully completed: Device policies for secure MQTT connection

* Successfully completed: Create IoT Thing with certificate

* Successfully completed: Simulate device publishing MQTT messages

* Successfully completed: Subscribe to topics in MQTT test client

* Successfully completed: IoT Rules Engine: SQL-like rule queries

* Successfully completed: Route messages to S3, Lambda, DynamoDB

* Successfully completed: Create IoT rule to forward data to S3

* Successfully completed: Trigger Lambda from IoT rule

* Successfully completed: End-to-end data ingestion test

* **[Rookwork]** Design the overall AWS architecture diagram for Rookwork

* **[Rookwork]** Identify required services: EC2, RDS, S3, SES, CloudFront, WAF, Route 53

* **[Rookwork]** Initialize Amazon VPC: configure Public/Private Subnets, Internet Gateway

* **[Rookwork]** Set up NAT Gateway for Private Subnet outbound traffic

* **[Rookwork]** Configure AWS IAM: create roles and policies for EC2, RDS, S3

* **[Rookwork]** Set up Security Groups for each tier (ALB, EC2, RDS)

* **[Rookwork]** Configure Amazon Route 53: register hosted zone, create DNS records

* **[Rookwork]** Set up AWS Certificate Manager (ACM) for SSL/TLS

* **[Rookwork]** Verify all VPC, subnet, and routing table configurations

* **[Rookwork]** Validate IAM permissions and Security Groups

* **[Rookwork]** Plan detailed tasks for Phase 2

