---
title: "Week 8 Worklog"
date: 2026-04-15
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Learn AWS Glue: crawlers, ETL jobs, and data catalog.
* Build a data processing pipeline to transform raw IoT data stored in S3.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - AWS Glue overview: Data Catalog, crawlers, databases, tables <br> - Glue vs traditional ETL tools | 03/06/2026 | 03/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Glue Crawlers: scanning S3 to auto-generate schema <br> - Glue Data Catalog as centralized metadata store | 04/06/2026 | 04/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Practice:** <br>&emsp; + Create Glue Crawler on raw IoT data S3 bucket <br>&emsp; + Run crawler and verify generated schema | 05/06/2026 | 05/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Glue ETL Jobs: PySpark scripts for data transformation <br> - Job triggers and scheduling | 06/06/2026 | 06/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Practice:** <br>&emsp; + Create Glue ETL job to transform and clean IoT data <br>&emsp; + Write processed data to output S3 bucket <br>&emsp; + Verify results with Athena | 07/06/2026 | 07/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

---

**Rookwork Project — Phase 2: Spring Boot Backend & PostgreSQL Database**

| Day | Rookwork Task | Start Date | Completion Date | Reference Material |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Initialize Spring Boot project: configure Spring Security (JWT + OAuth2) <br> - Design PostgreSQL schema for core entities (User, Workspace, Task) | 03/06/2026 | 03/06/2026 | |
| 3 | - Set up Amazon RDS PostgreSQL Multi-AZ: create DB instance and subnet groups <br> - Configure Flyway for database migration management | 04/06/2026 | 04/06/2026 | |
| 4 | - Implement core APIs: Authentication (register, login, refresh token) <br> - Write Flyway migration scripts V1 — initial schema setup | 05/06/2026 | 05/06/2026 | |
| 5 | - Implement CRUD APIs: Workspace, Project, Task management <br> - Configure Spring Data JPA repositories | 06/06/2026 | 06/06/2026 | |
| 6 | - **Review & test Phase 2:** <br>&emsp; + Unit test main API endpoints <br>&emsp; + Verify RDS connectivity from local environment <br>&emsp; + Plan EC2 deployment tasks (Phase 3) | 07/06/2026 | 07/06/2026 | |


### Week 8 Achievements:

* Understood the AWS Glue ecosystem and its role in the data lake architecture.

* Created and ran Glue Crawlers to automatically catalog raw IoT data from S3.

* Wrote a PySpark ETL job to clean, transform, and aggregate IoT sensor readings.

* Stored processed data in a separate S3 output bucket in Parquet format.

* Queried and verified transformed data using Amazon Athena.

* **[Rookwork Phase 2]** Initialized Spring Boot project, set up Amazon RDS PostgreSQL Multi-AZ, configured Flyway migration, and implemented Authentication APIs along with core CRUD endpoints.
