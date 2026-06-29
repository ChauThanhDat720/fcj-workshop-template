---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Học AWS IoT Core: kết nối thiết bị, giao thức MQTT, topics và rules.
* Hiểu cách đưa dữ liệu cảm biến từ edge device lên AWS cloud.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tổng quan AWS IoT Core: device registry, message broker, rules engine <br> - Giao thức MQTT: topics, QoS levels, retain messages | 22/09/2025 | 22/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tạo IoT Thing và certificates <br> - Device policies để kết nối MQTT bảo mật | 23/09/2025 | 23/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - **Thực hành:** <br>&emsp; + Tạo IoT Thing với certificate <br>&emsp; + Giả lập thiết bị gửi MQTT messages <br>&emsp; + Subscribe topics trong MQTT test client | 24/09/2025 | 24/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - IoT Rules Engine: câu query kiểu SQL <br> - Định tuyến messages đến S3, Lambda, DynamoDB | 25/09/2025 | 25/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành:** <br>&emsp; + Tạo IoT rule chuyển data đến S3 <br>&emsp; + Trigger Lambda từ IoT rule <br>&emsp; + Kiểm tra toàn bộ luồng data ingestion | 26/09/2025 | 26/09/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 7:

* Hiểu kiến trúc AWS IoT Core và cách edge device giao tiếp bảo mật với cloud qua MQTT.

* Tạo IoT Thing với chứng chỉ X.509 và cấu hình device policy.

* Giả lập gửi dữ liệu cảm biến lên IoT topics qua MQTT test client.

* Xây dựng IoT Rules tự động định tuyến messages đến S3 và Lambda.

* Hoàn thành luồng data ingestion end-to-end từ thiết bị giả lập đến cloud storage.
