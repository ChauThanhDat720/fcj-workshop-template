---
title: "Worklog Tuần 8"
date: 2026-04-15
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Học AWS Glue: crawlers, ETL jobs và data catalog.
* Xây dựng pipeline xử lý dữ liệu để transform raw IoT data lưu trong S3.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Tổng quan AWS Glue: Data Catalog, crawlers, databases, tables <br> - So sánh Glue với các ETL tool truyền thống | 03/06/2026 | 03/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Glue Crawlers: quét S3 để tự động tạo schema <br> - Glue Data Catalog là kho metadata tập trung | 04/06/2026 | 04/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Thực hành:** <br>&emsp; + Tạo Glue Crawler trên S3 bucket chứa raw IoT data <br>&emsp; + Chạy crawler và kiểm tra schema được tạo | 05/06/2026 | 05/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Glue ETL Jobs: PySpark script để transform dữ liệu <br> - Job triggers và scheduling | 06/06/2026 | 06/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Thực hành:** <br>&emsp; + Tạo Glue ETL job để transform và làm sạch IoT data <br>&emsp; + Ghi dữ liệu đã xử lý vào S3 output bucket <br>&emsp; + Xác minh kết quả bằng Athena | 07/06/2026 | 07/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

---

**Dự án Rookwork — Phase 2: Xây dựng Backend Spring Boot & Database PostgreSQL**

| Thứ | Công việc Rookwork | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Khởi tạo project Spring Boot: cấu hình Spring Security (JWT + OAuth2) <br> - Thiết kế schema database PostgreSQL cho các entity chính (User, Workspace, Task) | 03/06/2026 | 03/06/2026 | |
| 3 | - Cấu hình Amazon RDS PostgreSQL Multi-AZ: tạo DB instance, subnet groups <br> - Thiết lập Flyway để quản lý database migration | 04/06/2026 | 04/06/2026 | |
| 4 | - Implement các API cốt lõi: Authentication (register, login, refresh token) <br> - Viết Flyway migration scripts V1 — khởi tạo schema ban đầu | 05/06/2026 | 05/06/2026 | |
| 5 | - Implement CRUD API: Workspace, Project, Task management <br> - Cấu hình Spring Data JPA repositories | 06/06/2026 | 06/06/2026 | |
| 6 | - **Review & kiểm thử Phase 2:** <br>&emsp; + Unit test các API endpoint chính <br>&emsp; + Xác minh kết nối RDS từ local environment <br>&emsp; + Lập kế hoạch deploy lên EC2 (Phase 3) | 07/06/2026 | 07/06/2026 | |

### Kết quả đạt được tuần 8:

* Hoàn thành: Tổng quan AWS Glue: Data Catalog, crawlers, databases, tables

* Hoàn thành: So sánh Glue với các ETL tool truyền thống

* Hoàn thành: Glue Crawlers: quét S3 để tự động tạo schema

* Hoàn thành: Glue Data Catalog là kho metadata tập trung

* Hoàn thành: Tạo Glue Crawler trên S3 bucket chứa raw IoT data

* Hoàn thành: Chạy crawler và kiểm tra schema được tạo

* Hoàn thành: Glue ETL Jobs: PySpark script để transform dữ liệu

* Hoàn thành: Job triggers và scheduling

* Hoàn thành: Tạo Glue ETL job để transform và làm sạch IoT data

* Hoàn thành: Ghi dữ liệu đã xử lý vào S3 output bucket

* Hoàn thành: Xác minh kết quả bằng Athena

* **[Rookwork]** Khởi tạo project Spring Boot: cấu hình Spring Security (JWT + OAuth2)

* **[Rookwork]** Thiết kế schema database PostgreSQL cho các entity chính (User, Workspace, Task)

* **[Rookwork]** Cấu hình Amazon RDS PostgreSQL Multi-AZ: tạo DB instance, subnet groups

* **[Rookwork]** Thiết lập Flyway để quản lý database migration

* **[Rookwork]** Implement các API cốt lõi: Authentication (register, login, refresh token)

* **[Rookwork]** Viết Flyway migration scripts V1 — khởi tạo schema ban đầu

* **[Rookwork]** Implement CRUD API: Workspace, Project, Task management

* **[Rookwork]** Cấu hình Spring Data JPA repositories

* **[Rookwork]** Unit test các API endpoint chính

* **[Rookwork]** Xác minh kết nối RDS từ local environment

* **[Rookwork]** Lập kế hoạch deploy lên EC2 (Phase 3)

