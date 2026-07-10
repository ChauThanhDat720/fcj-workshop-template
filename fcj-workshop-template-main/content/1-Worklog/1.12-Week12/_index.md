---
title: "Week 12 Worklog"
date: 2026-04-15
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Final deployment of the IoT Weather Platform to production.
* Complete technical documentation and prepare the internship report.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Final review of all AWS resources and costs <br> - Verify AWS budget alerts are configured correctly | 01/07/2026 | 01/07/2026 |  |
| 3 | - Production deployment: final CDK stack deployment <br> - Configure CloudWatch alarms and dashboards for monitoring | 02/07/2026 | 02/07/2026 |  |
| 4 | - **Practice:** <br>&emsp; + Final end-to-end production test <br>&emsp; + Verify all Cognito user accounts are active <br>&emsp; + Monitor system health for 24 hours | 03/07/2026 | 03/07/2026 |  |
| 5 | - Write technical documentation: architecture diagrams, API docs, deployment guide <br> - Prepare demo for the internship presentation | 04/07/2026 | 04/07/2026 |  |
| 6 | - Complete internship report <br> - Submit final deliverables <br> - Conduct cleanup of unused resources | 15/07/2026 | 15/07/2026 |  |

---

**Rookwork Project — Phase 6: End-to-End Testing, Security Review & System Handover**

| Day | Rookwork Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - End-to-end testing of the entire Rookwork system: Login → Create Workspace → Invite member (SES) → Upload file (S3) → Manage Tasks <br> - Record all test results | 01/07/2026 | 01/07/2026 | |
| 3 | - Security review: check IAM least-privilege, Security Group rules, and S3 bucket policies <br> - Verify JWT token expiry, CORS policy, and WAF rules are working correctly | 02/07/2026 | 02/07/2026 | |
| 4 | - Configure Amazon CloudWatch: create alarms for EC2 CPU, RDS connections, ALB 5xx errors <br> - Set up AWS Budgets: configure cost threshold alerts | 03/07/2026 | 03/07/2026 | |
| 5 | - Write Rookwork technical documentation: AWS architecture diagram, API reference, deployment guide <br> - Prepare handover documentation and system demo for supervisor | 04/07/2026 | 04/07/2026 | |
| 6 | - **Finalize & Hand over Phase 6:** <br>&emsp; + Demo the complete Rookwork system <br>&emsp; + Clean up unnecessary AWS resources (Multi-AZ dev, NAT Gateway test) <br>&emsp; + Confirm AWS costs are within budget | 15/07/2026 | 15/07/2026 | |


### Week 12 Achievements:

* Successfully deployed the complete IoT Weather Platform to production using AWS CDK.

* Configured CloudWatch monitoring and alerts for all critical components.

* All 5 lab member accounts created and verified in Amazon Cognito.

* Completed full technical documentation including system architecture, API reference, and deployment guide.

* Delivered a successful demo of the platform to the internship supervisors.

* Cleaned up development resources and finalized AWS cost within the $0.70/month budget.

* Completed and submitted the internship report on time.

* **[Rookwork Phase 6]** Completed end-to-end testing of the full Rookwork system, conducted a thorough security review, configured CloudWatch monitoring, finalized technical documentation, and successfully demonstrated and handed over the system to the supervisor.
