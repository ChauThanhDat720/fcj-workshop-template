---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Hiểu về AWS Identity and Access Management (IAM): users, groups, roles và policies.
* Học Amazon S3: bucket, object, phân quyền và các lớp lưu trữ.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu IAM: users, groups, roles, policies <br> - Tạo IAM user và gán quyền | 18/08/2025 | 18/08/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - **Thực hành:** <br>&emsp; + Tạo IAM user với quyền tối thiểu <br>&emsp; + Tạo custom IAM policy <br>&emsp; + Gán role cho EC2 instance | 19/08/2025 | 19/08/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu Amazon S3: bucket, object, versioning <br> - Các loại storage class (Standard, IA, Glacier) <br> - Lifecycle policies | 20/08/2025 | 20/08/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - **Thực hành:** <br>&emsp; + Tạo S3 bucket và upload object <br>&emsp; + Cấu hình bucket policy và ACL <br>&emsp; + Bật versioning và lifecycle rules | 21/08/2025 | 21/08/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Host static website trên S3 <br> - Cross-region replication <br> - Ôn tập và tổng kết tuần 2 | 22/08/2025 | 22/08/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 2:

* Nắm vững các khái niệm IAM và cấu hình users, groups, roles theo nguyên tắc least privilege.

* Tạo custom IAM policy và gán cho đúng đối tượng.

* Gán IAM role cho EC2 instance để truy cập dịch vụ an toàn mà không cần hardcode credentials.

* Tạo và cấu hình S3 bucket bao gồm:
  * Versioning
  * Lifecycle rules
  * Bucket policy và ACL

* Host thành công một static website trên S3.

* Hiểu các loại storage class của S3 và biết khi nào nên dùng loại nào.
