---
title: "Worklog Tuần 7"
date: 2026-04-17
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

{{% notice info %}}
🚀 **Bắt đầu dự án Rookwork:** Từ tuần 7 (27/05/2026), song song với việc học các dịch vụ AWS chuyên sâu, dự án **Rookwork** — hệ thống quản lý làm việc nhóm đa nền tảng — chính thức được triển khai phát triển.
{{% /notice %}}

### Mục tiêu tuần 7:

* Học AWS IoT Core: kết nối thiết bị, giao thức MQTT, topics và rules.
* Hiểu cách đưa dữ liệu cảm biến từ edge device lên AWS cloud.
* Bắt đầu phát triển dự án **Rookwork**: thiết lập cấu trúc dự án, phân chia module và lên kế hoạch kiến trúc hệ thống.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Tổng quan AWS IoT Core: device registry, message broker, rules engine <br> - Giao thức MQTT: topics, QoS levels, retain messages | 27/05/2026 | 27/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Tạo IoT Thing và certificates <br> - Device policies để kết nối MQTT bảo mật | 28/05/2026 | 28/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Thực hành:** <br>&emsp; + Tạo IoT Thing với certificate <br>&emsp; + Giả lập thiết bị gửi MQTT messages <br>&emsp; + Subscribe topics trong MQTT test client | 29/05/2026 | 29/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - IoT Rules Engine: câu query kiểu SQL <br> - Định tuyến messages đến S3, Lambda, DynamoDB | 30/05/2026 | 30/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Thực hành:** <br>&emsp; + Tạo IoT rule chuyển data đến S3 <br>&emsp; + Trigger Lambda từ IoT rule <br>&emsp; + Kiểm tra toàn bộ luồng data ingestion | 31/05/2026 | 31/05/2026 | <https://cloudjourney.awsstudygroup.com/> |

---

**Dự án Rookwork — Phase 1: Thiết kế kiến trúc & Cấu hình hạ tầng AWS**

| Thứ | Công việc Rookwork | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Thiết kế sơ đồ kiến trúc AWS tổng thể cho Rookwork <br> - Xác định các dịch vụ cần dùng: EC2, RDS, S3, SES, CloudFront, WAF, Route 53 | 27/05/2026 | 27/05/2026 | |
| 3 | - Khởi tạo Amazon VPC: cấu hình Public/Private Subnets, Internet Gateway <br> - Thiết lập NAT Gateway cho Private Subnet outbound traffic | 28/05/2026 | 28/05/2026 | |
| 4 | - Cấu hình AWS IAM: tạo roles và policies cho EC2, RDS, S3 <br> - Thiết lập Security Groups cho từng tầng (ALB, EC2, RDS) | 29/05/2026 | 29/05/2026 | |
| 5 | - Cấu hình Amazon Route 53: đăng ký hosted zone, tạo DNS records <br> - Thiết lập AWS Certificate Manager (ACM) cho SSL/TLS | 30/05/2026 | 30/05/2026 | |
| 6 | - **Review & hoàn thiện Phase 1:** <br>&emsp; + Kiểm tra toàn bộ cấu hình VPC, subnet, routing table <br>&emsp; + Verify IAM permissions và Security Groups <br>&emsp; + Lập kế hoạch chi tiết cho Phase 2 | 31/05/2026 | 31/05/2026 | |

### Kết quả đạt được tuần 7:

* Hoàn thành: Tổng quan AWS IoT Core: device registry, message broker, rules engine

* Hoàn thành: Giao thức MQTT: topics, QoS levels, retain messages

* Hoàn thành: Tạo IoT Thing và certificates

* Hoàn thành: Device policies để kết nối MQTT bảo mật

* Hoàn thành: Tạo IoT Thing với certificate

* Hoàn thành: Giả lập thiết bị gửi MQTT messages

* Hoàn thành: Subscribe topics trong MQTT test client

* Hoàn thành: IoT Rules Engine: câu query kiểu SQL

* Hoàn thành: Định tuyến messages đến S3, Lambda, DynamoDB

* Hoàn thành: Tạo IoT rule chuyển data đến S3

* Hoàn thành: Trigger Lambda từ IoT rule

* Hoàn thành: Kiểm tra toàn bộ luồng data ingestion

* **[Rookwork]** Thiết kế sơ đồ kiến trúc AWS tổng thể cho Rookwork

* **[Rookwork]** Xác định các dịch vụ cần dùng: EC2, RDS, S3, SES, CloudFront, WAF, Route 53

* **[Rookwork]** Khởi tạo Amazon VPC: cấu hình Public/Private Subnets, Internet Gateway

* **[Rookwork]** Thiết lập NAT Gateway cho Private Subnet outbound traffic

* **[Rookwork]** Cấu hình AWS IAM: tạo roles và policies cho EC2, RDS, S3

* **[Rookwork]** Thiết lập Security Groups cho từng tầng (ALB, EC2, RDS)

* **[Rookwork]** Cấu hình Amazon Route 53: đăng ký hosted zone, tạo DNS records

* **[Rookwork]** Thiết lập AWS Certificate Manager (ACM) cho SSL/TLS

* **[Rookwork]** Kiểm tra toàn bộ cấu hình VPC, subnet, routing table

* **[Rookwork]** Verify IAM permissions và Security Groups

* **[Rookwork]** Lập kế hoạch chi tiết cho Phase 2

