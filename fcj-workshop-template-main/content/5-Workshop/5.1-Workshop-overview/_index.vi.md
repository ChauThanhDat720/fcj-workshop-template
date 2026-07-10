---
title : "Giới thiệu"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

## Kiến trúc hệ thống

![Rookwork AWS Architecture](/images/5-Workshop/rookwork_aws_architecture.jpg)

Hệ thống hoạt động theo các luồng xử lý chính sau:

**① DNS Resolution & CDN:**
- **Route 53** phân giải tên miền, điều hướng người dùng đến hệ thống.
- **CloudFront** phân phối frontend tĩnh từ **FE Static S3**, kết hợp **AWS WAF** để bảo vệ khỏi các tấn công web.

**② Routing & Compute Backend:**
- API traffic đi qua **Internet Gateway** → **ALB (Application Load Balancer)** → cân bằng tải đến các **EC2 instances** đặt trong *Private Subnet*.
- EC2 truy cập internet outbound qua **NAT Gateway** (bước 6.1 — Route to Internet).

**③ Database & Storage:**
- Dữ liệu nghiệp vụ lưu trên **Amazon RDS PostgreSQL**, triển khai **Multi-AZ** (bước 7 — DB Replication) để dự phòng thảm họa.
- File đính kèm được EC2 ghi vào **Amazon S3** qua **S3 Gateway Endpoint** theo Internal Routing (bước 8 & 9) — không đi qua internet, giảm chi phí băng thông về 0.
- Người dùng tải file trực tiếp qua **Direct File Access** (bước 10).

**④ Shared Services:**
- **Amazon SES** gửi email thông báo (mời thành viên, v.v.) được trigger từ EC2 (bước 6.2 & 6.3).
- **AWS Certificate Manager (ACM)** quản lý SSL/TLS, **AWS IAM** quản lý phân quyền toàn hệ thống.
