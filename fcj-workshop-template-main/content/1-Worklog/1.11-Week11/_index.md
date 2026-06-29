---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Integrate all platform components end-to-end: IoT Core → S3 → Glue → API Gateway → Amplify.
* Perform comprehensive testing and resolve integration issues.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ----------------------------------------- |
| 2   | - Review full system architecture and identify integration gaps <br> - Map data flow: device → IoT Core → S3 → Glue → API → Dashboard | 20/10/2025 | 20/10/2025 | |
| 3   | - End-to-end integration testing: simulate sensor data through the full pipeline <br> - Fix issues with IoT rule routing and Lambda triggers | 21/10/2025 | 21/10/2025 | |
| 4   | - **Practice:** <br>&emsp; + Run full data flow test with 5 simulated devices <br>&emsp; + Verify data appears correctly on the dashboard <br>&emsp; + Debug latency and missing data issues | 22/10/2025 | 22/10/2025 | |
| 5   | - Performance and load testing of API Gateway and Lambda <br> - Optimize Glue ETL job execution time | 23/10/2025 | 23/10/2025 | |
| 6   | - **Practice:** <br>&emsp; + Fix all identified bugs <br>&emsp; + Final integration test with all components running <br>&emsp; + Document known limitations | 24/10/2025 | 24/10/2025 | |


### Week 11 Achievements:

* Successfully completed end-to-end integration of the entire IoT Weather Platform.

* Verified that sensor data flows correctly from simulated devices through IoT Core, S3, Glue ETL, API Gateway, and finally appears on the Amplify-hosted dashboard.

* Fixed several integration bugs including IoT rule misconfiguration and Lambda timeout issues.

* Optimized Glue ETL job performance by reducing unnecessary data scans.

* Documented all known limitations and planned improvements for the final week.
