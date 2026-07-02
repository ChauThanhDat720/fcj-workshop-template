---
title: "Worklog Tuần 4"
date: 2026-04-15
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Học Amazon RDS: managed relational database, Multi-AZ và read replicas.
* Tìm hiểu Amazon ElastiCache và DynamoDB cơ bản.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Tìm hiểu RDS: các engine được hỗ trợ (MySQL, PostgreSQL, Aurora) <br> - Multi-AZ deployment và automatic failover | 06/05/2026 | 06/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - RDS Read Replicas để phân tải đọc <br> - Backup và restore: automated backups, snapshots | 07/05/2026 | 07/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Thực hành:** <br>&emsp; + Launch RDS MySQL trong private subnet <br>&emsp; + Kết nối từ EC2 <br>&emsp; + Tạo snapshot và restore | 08/05/2026 | 08/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Amazon DynamoDB: table, item, attribute, partition key <br> - DynamoDB streams và global tables | 09/05/2026 | 09/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Thực hành:** <br>&emsp; + Tạo bảng DynamoDB <br>&emsp; + Thao tác CRUD qua Console và CLI <br>&emsp; + Ôn tập tuần 4 | 10/05/2026 | 10/05/2026 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 4:

* Hiểu lợi ích của RDS managed service so với tự quản lý database.

* Triển khai RDS MySQL trong private subnet với Multi-AZ để đảm bảo tính sẵn sàng cao.

* Cấu hình Read Replicas để phân phối tải đọc.

* Thực hiện backup và restore bằng snapshot.

* Tạo và vận hành bảng DynamoDB với các thao tác CRUD qua Console và CLI.

* Hiểu sự khác biệt giữa relational (RDS) và NoSQL (DynamoDB) trên AWS.
