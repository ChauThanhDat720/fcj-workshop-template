---
title: "Week 11 Worklog"
date: 2026-04-17
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Integrate all platform components end-to-end: IoT Core → S3 → Glue → API Gateway → Amplify.
* Perform comprehensive testing and resolve integration issues.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Review full system architecture and identify integration gaps <br> - Map data flow: device → IoT Core → S3 → Glue → API → Dashboard | 24/06/2026 | 24/06/2026 |  |
| 3 | - End-to-end integration testing: simulate sensor data through the full pipeline <br> - Fix issues with IoT rule routing and Lambda triggers | 25/06/2026 | 25/06/2026 |  |
| 4 | - **Practice:** <br>&emsp; + Run full data flow test with 5 simulated devices <br>&emsp; + Verify data appears correctly on the dashboard <br>&emsp; + Debug latency and missing data issues | 26/06/2026 | 26/06/2026 |  |
| 5 | - Performance and load testing of API Gateway and Lambda <br> - Optimize Glue ETL job execution time | 27/06/2026 | 27/06/2026 |  |
| 6 | - **Practice:** <br>&emsp; + Fix all identified bugs <br>&emsp; + Final integration test with all components running <br>&emsp; + Document known limitations | 28/06/2026 | 28/06/2026 |  |

---

**Rookwork Project — Phase 5: S3 File Storage (VPC Endpoint) & Amazon SES Email Integration**

| Day | Rookwork Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Create a dedicated Amazon S3 bucket for File Storage (attachments) <br> - Configure VPC S3 Gateway Endpoint so EC2 writes files to S3 via internal routing (no internet) | 24/06/2026 | 28/06/2026 | |
| 3 | - Implement file upload/download in Spring Boot Backend (AWS SDK for S3) <br> - Generate pre-signed URLs for users to securely download files via CloudFront | 24/06/2026 | 28/06/2026 | |
| 4 | - Configure Amazon SES: verify domain and create email identity <br> - Implement email notification service in Spring Boot: send Workspace invitation emails | 24/06/2026 | 28/06/2026 | |
| 5 | - End-to-end test file upload feature: Frontend → EC2 → S3 Endpoint → S3 <br> - Test email invitation flow: Backend → SES → user inbox | 24/06/2026 | 28/06/2026 | |
| 6 | - **Review & test Phase 5:** <br>&emsp; + Verify complete file upload/download and email notification features <br>&emsp; + Security assessment: S3 bucket policies, SES sending limits <br>&emsp; + Prepare for Phase 6: Full system testing & handover | 24/06/2026 | 28/06/2026 | |

### Week 11 Achievements:

* Successfully completed: Review full system architecture and identify integration gaps

* Successfully completed: Map data flow: device → IoT Core → S3 → Glue → API → Dashboard

* Successfully completed: End-to-end integration testing: simulate sensor data through the full pipeline

* Successfully completed: Fix issues with IoT rule routing and Lambda triggers

* Successfully completed: Run full data flow test with 5 simulated devices

* Successfully completed: Verify data appears correctly on the dashboard

* Successfully completed: Debug latency and missing data issues

* Successfully completed: Performance and load testing of API Gateway and Lambda

* Successfully completed: Optimize Glue ETL job execution time

* Successfully completed: Fix all identified bugs

* Successfully completed: Final integration test with all components running

* Successfully completed: Document known limitations

* **[Rookwork]** Create a dedicated Amazon S3 bucket for File Storage (attachments)

* **[Rookwork]** Configure VPC S3 Gateway Endpoint so EC2 writes files to S3 via internal routing (no internet)

* **[Rookwork]** Implement file upload/download in Spring Boot Backend (AWS SDK for S3)

* **[Rookwork]** Generate pre-signed URLs for users to securely download files via CloudFront

* **[Rookwork]** Configure Amazon SES: verify domain and create email identity

* **[Rookwork]** Implement email notification service in Spring Boot: send Workspace invitation emails

* **[Rookwork]** End-to-end test file upload feature: Frontend → EC2 → S3 Endpoint → S3

* **[Rookwork]** Test email invitation flow: Backend → SES → user inbox

* **[Rookwork]** Verify complete file upload/download and email notification features

* **[Rookwork]** Security assessment: S3 bucket policies, SES sending limits

* **[Rookwork]** Prepare for Phase 6: Full system testing & handover

