---
title: "Worklog Tuần 5"
date: 2026-04-15
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Học AWS Lambda: serverless function, event-driven computing và execution roles.
* Hiểu triggers, layers và giám sát Lambda với CloudWatch.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Lambda: function, handler, runtime, memory, timeout <br> - Tổng quan về kiến trúc event-driven | 13/05/2026 | 13/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Lambda triggers: S3, DynamoDB Streams, API Gateway, EventBridge <br> - Lambda execution roles và phân quyền | 14/05/2026 | 14/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Thực hành:** <br>&emsp; + Tạo Lambda function bằng Python <br>&emsp; + Trigger Lambda từ S3 upload event <br>&emsp; + Xem logs trong CloudWatch | 15/05/2026 | 15/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Lambda Layers cho shared dependencies <br> - Environment variables và tích hợp Secrets Manager <br> - Tối ưu cold start | 16/05/2026 | 16/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Thực hành:** <br>&emsp; + Lambda trigger từ DynamoDB Stream <br>&emsp; + Thêm Lambda Layer <br>&emsp; + Giám sát với CloudWatch metrics | 17/05/2026 | 17/05/2026 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 5:

* Hiểu mô hình serverless và cách Lambda hoạt động trong kiến trúc event-driven.

* Tạo Lambda function bằng Python và kết nối với nhiều trigger (S3, DynamoDB Streams).

* Cấu hình IAM execution role phù hợp cho Lambda.

* Sử dụng CloudWatch Logs để giám sát và debug Lambda.

* Triển khai Lambda Layers để chia sẻ dependencies chung giữa nhiều function.

* Tối ưu hiệu năng bằng cách điều chỉnh memory và timeout.
