---
title: "Worklog Tuần 11"
date: 2026-04-15
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Tích hợp toàn bộ các thành phần platform end-to-end: IoT Core → S3 → Glue → API Gateway → Amplify.
* Thực hiện kiểm thử toàn diện và xử lý các vấn đề tích hợp.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Review toàn bộ kiến trúc hệ thống và xác định các khoảng thiếu hụt <br> - Mapping luồng data: thiết bị → IoT Core → S3 → Glue → API → Dashboard | 24/06/2026 | 24/06/2026 |  |
| 3 | - Kiểm thử tích hợp end-to-end: giả lập dữ liệu cảm biến qua toàn bộ pipeline <br> - Sửa lỗi IoT rule routing và Lambda triggers | 25/06/2026 | 25/06/2026 |  |
| 4 | - **Thực hành:** <br>&emsp; + Chạy test luồng data đầy đủ với 5 thiết bị giả lập <br>&emsp; + Kiểm tra dữ liệu hiển thị đúng trên dashboard <br>&emsp; + Debug latency và vấn đề mất dữ liệu | 26/06/2026 | 26/06/2026 |  |
| 5 | - Kiểm thử hiệu năng và tải của API Gateway và Lambda <br> - Tối ưu thời gian chạy Glue ETL job | 27/06/2026 | 27/06/2026 |  |
| 6 | - **Thực hành:** <br>&emsp; + Sửa tất cả bug đã phát hiện <br>&emsp; + Test tích hợp cuối với tất cả component chạy đồng thời <br>&emsp; + Ghi chép các hạn chế đã biết | 28/06/2026 | 28/06/2026 |  |

---

**Dự án Rookwork — Phase 5: Tích hợp S3 File Storage (VPC Endpoint) & Amazon SES Email**

| Thứ | Công việc Rookwork | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Tạo Amazon S3 bucket riêng cho File Storage (attachments) <br> - Cấu hình VPC S3 Gateway Endpoint để EC2 ghi file lên S3 qua internal routing (không qua internet) | 24/06/2026 | 24/06/2026 | |
| 3 | - Implement upload/download file trong Spring Boot Backend (AWS SDK S3) <br> - Tạo pre-signed URLs cho người dùng download file an toàn qua CloudFront | 25/06/2026 | 25/06/2026 | |
| 4 | - Cấu hình Amazon SES: verify domain, tạo email identity <br> - Implement email notification service trong Spring Boot: gửi email mời tham gia Workspace | 26/06/2026 | 26/06/2026 | |
| 5 | - Test end-to-end tính năng upload file: Frontend → EC2 → S3 Endpoint → S3 <br> - Test email invitation: Backend → SES → người dùng | 27/06/2026 | 27/06/2026 | |
| 6 | - **Review & kiểm thử Phase 5:** <br>&emsp; + Kiểm tra toàn bộ tính năng file upload/download và email notification <br>&emsp; + Đánh giá bảo mật: S3 bucket policies, SES sending limits <br>&emsp; + Chuẩn bị cho Phase 6: Kiểm thử toàn hệ thống & bàn giao | 28/06/2026 | 28/06/2026 | |


### Kết quả đạt được tuần 11:

* Hoàn thành tích hợp end-to-end của toàn bộ IoT Weather Platform.

* Xác minh dữ liệu cảm biến chạy đúng từ thiết bị giả lập qua IoT Core, S3, Glue ETL, API Gateway và hiển thị trên Amplify dashboard.

* Sửa nhiều lỗi tích hợp bao gồm misconfiguration trong IoT rule và Lambda timeout.

* Tối ưu hiệu năng Glue ETL job bằng cách giảm data scan không cần thiết.

* Ghi chép tất cả hạn chế đã biết và lên kế hoạch cải thiện cho tuần cuối.

* **[Rookwork Phase 5]** Tích hợp thành công S3 File Storage qua VPC Gateway Endpoint (EC2 ghi file không qua internet), implement pre-signed URL download và hoàn thiện Amazon SES gửi email thông báo mời tham gia Workspace.

