---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---


# Rookwork — Hệ thống quản lý làm việc nhóm trên nền tảng AWS Cloud

## Tổng quan dự án

**Rookwork** là phần mềm quản lý làm việc nhóm tích hợp, được thiết kế để vận hành trên nền tảng đa môi trường (browser và desktop app). Hệ thống sử dụng kiến trúc **Client-Server** với frontend xây dựng bằng **React 19**, backend trên **Spring Boot**, và toàn bộ hạ tầng được triển khai trên **AWS Cloud** theo tiêu chuẩn **High Availability (HA)** với bảo mật nhiều lớp.

Workshop này hướng dẫn cách triển khai và vận hành hạ tầng AWS thực tế cho dự án Rookwork, bao gồm cấu hình mạng VPC, phân phối nội dung qua CloudFront, bảo mật với WAF, cùng tích hợp các dịch vụ lưu trữ S3 và gửi email SES.

## Nội dung workshop

1. [Tổng quan về workshop](5.1-Workshop-overview/)
2. [Chuẩn bị](5.2-Prerequiste/)
3. [Truy cập đến S3 từ VPC](5.3-S3-vpc/)
4. [Truy cập đến S3 từ TTDL On-premises](5.4-S3-onprem/)
5. [VPC Endpoint Policies (làm thêm)](5.5-Policy/)
6. [Dọn dẹp tài nguyên](5.6-Cleanup/)
