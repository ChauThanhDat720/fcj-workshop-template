---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Learn AWS Glue: crawlers, ETL jobs, and data catalog.
* Build a data processing pipeline to transform raw IoT data stored in S3.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ----------------------------------------- |
| 2   | - AWS Glue overview: Data Catalog, crawlers, databases, tables <br> - Glue vs traditional ETL tools | 29/09/2025 | 29/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Glue Crawlers: scanning S3 to auto-generate schema <br> - Glue Data Catalog as centralized metadata store | 30/09/2025 | 30/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - **Practice:** <br>&emsp; + Create Glue Crawler on raw IoT data S3 bucket <br>&emsp; + Run crawler and verify generated schema | 01/10/2025 | 01/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Glue ETL Jobs: PySpark scripts for data transformation <br> - Job triggers and scheduling | 02/10/2025 | 02/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Practice:** <br>&emsp; + Create Glue ETL job to transform and clean IoT data <br>&emsp; + Write processed data to output S3 bucket <br>&emsp; + Verify results with Athena | 03/10/2025 | 03/10/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Week 8 Achievements:

* Understood the AWS Glue ecosystem and its role in the data lake architecture.

* Created and ran Glue Crawlers to automatically catalog raw IoT data from S3.

* Wrote a PySpark ETL job to clean, transform, and aggregate IoT sensor readings.

* Stored processed data in a separate S3 output bucket in Parquet format.

* Queried and verified transformed data using Amazon Athena.
