---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Tích hợp toàn bộ các thành phần platform end-to-end: IoT Core → S3 → Glue → API Gateway → Amplify.
* Thực hiện kiểm thử toàn diện và xử lý các vấn đề tích hợp.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Review toàn bộ kiến trúc hệ thống và xác định các khoảng thiếu hụt <br> - Mapping luồng data: thiết bị → IoT Core → S3 → Glue → API → Dashboard | 20/10/2025 | 20/10/2025 | |
| 3   | - Kiểm thử tích hợp end-to-end: giả lập dữ liệu cảm biến qua toàn bộ pipeline <br> - Sửa lỗi IoT rule routing và Lambda triggers | 21/10/2025 | 21/10/2025 | |
| 4   | - **Thực hành:** <br>&emsp; + Chạy test luồng data đầy đủ với 5 thiết bị giả lập <br>&emsp; + Kiểm tra dữ liệu hiển thị đúng trên dashboard <br>&emsp; + Debug latency và vấn đề mất dữ liệu | 22/10/2025 | 22/10/2025 | |
| 5   | - Kiểm thử hiệu năng và tải của API Gateway và Lambda <br> - Tối ưu thời gian chạy Glue ETL job | 23/10/2025 | 23/10/2025 | |
| 6   | - **Thực hành:** <br>&emsp; + Sửa tất cả bug đã phát hiện <br>&emsp; + Test tích hợp cuối với tất cả component chạy đồng thời <br>&emsp; + Ghi chép các hạn chế đã biết | 24/10/2025 | 24/10/2025 | |


### Kết quả đạt được tuần 11:

* Hoàn thành tích hợp end-to-end của toàn bộ IoT Weather Platform.

* Xác minh dữ liệu cảm biến chạy đúng từ thiết bị giả lập qua IoT Core, S3, Glue ETL, API Gateway và hiển thị trên Amplify dashboard.

* Sửa nhiều lỗi tích hợp bao gồm misconfiguration trong IoT rule và Lambda timeout.

* Tối ưu hiệu năng Glue ETL job bằng cách giảm data scan không cần thiết.

* Ghi chép tất cả hạn chế đã biết và lên kế hoạch cải thiện cho tuần cuối.
