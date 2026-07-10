---
title: "Week 9 Worklog"
date: 2026-04-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Learn AWS Amplify: hosting, CI/CD, and environment management.
* Build and deploy a Next.js web application on Amplify.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - AWS Amplify overview: hosting, backend, and CI/CD pipeline <br> - Amplify vs CloudFront + S3 static hosting comparison | 10/06/2026 | 10/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Next.js project setup for Amplify deployment <br> - Amplify environment variables and build settings | 11/06/2026 | 11/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Practice:** <br>&emsp; + Connect GitHub repository to Amplify <br>&emsp; + Configure build settings for Next.js <br>&emsp; + Deploy first version of the web app | 12/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Real-time dashboard design: displaying IoT sensor data <br> - Connecting Next.js frontend to API Gateway endpoints | 13/06/2026 | 13/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Practice:** <br>&emsp; + Implement data fetching from API Gateway <br>&emsp; + Build real-time charts for weather data <br>&emsp; + Deploy and verify on Amplify | 14/06/2026 | 14/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

---

**Rookwork Project — Phase 3: Deploy Backend to EC2 + ALB + NAT Gateway**

| Day | Rookwork Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Launch Amazon EC2 instance (t3.medium) in Private Subnet <br> - Configure Application Load Balancer (ALB): target groups, health checks, listener rules | 10/06/2026 | 10/06/2026 | |
| 3 | - Package Spring Boot application into a Docker image <br> - Push image to Amazon ECR and configure EC2 to pull and run the container | 11/06/2026 | 11/06/2026 | |
| 4 | - Configure NAT Gateway for EC2 Private Subnet outbound traffic <br> - Verify EC2 → RDS connectivity within the Private Network | 12/06/2026 | 12/06/2026 | |
| 5 | - Configure ALB HTTPS Listener with ACM certificate <br> - Set up Auto Scaling Group for EC2 (min: 1, desired: 1) | 13/06/2026 | 13/06/2026 | |
| 6 | - **Review & test Phase 3:** <br>&emsp; + Test API calls through ALB endpoint <br>&emsp; + Verify EC2 can reach RDS and access internet via NAT <br>&emsp; + Plan Frontend development tasks (Phase 4) | 14/06/2026 | 14/06/2026 | |


### Week 9 Achievements:

* Successfully deployed a Next.js application on AWS Amplify with automatic CI/CD from GitHub.

* Configured Amplify build settings and environment variables for different deployment stages.

* Built a real-time dashboard UI to display weather sensor data fetched from API Gateway.

* Implemented dynamic charts to visualize temperature, humidity, and other sensor readings.

* Understood the Amplify hosting lifecycle and how to manage multiple environments (dev/prod).

* **[Rookwork Phase 3]** Deployed Spring Boot Backend to Amazon EC2 via Docker container, configured HTTPS ALB, NAT Gateway, and verified internal EC2 ↔ RDS connectivity successfully.
