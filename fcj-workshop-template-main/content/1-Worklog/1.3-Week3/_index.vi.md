---
title: "Worklog Tuần 3"
date: 2026-04-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Hiểu Amazon VPC: subnet, route table, internet gateway và NAT gateway.
* Học security groups và network ACL để kiểm soát lưu lượng mạng.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Tìm hiểu VPC: CIDR, subnet (public/private), availability zones | 29/04/2026 | 29/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Internet Gateway, NAT Gateway <br> - Cấu hình route table | 30/04/2026 | 30/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Thực hành:** <br>&emsp; + Tạo VPC với subnet public và private <br>&emsp; + Gắn Internet Gateway <br>&emsp; + Cấu hình route table | 01/05/2026 | 01/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Security Groups vs Network ACL <br> - VPC Peering cơ bản <br> - VPC Endpoints | 02/05/2026 | 02/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Thực hành:** <br>&emsp; + Launch EC2 trong private subnet <br>&emsp; + Truy cập qua Bastion Host <br>&emsp; + Cấu hình Security Groups | 03/05/2026 | 03/05/2026 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 3:

* Thiết kế và triển khai VPC tùy chỉnh với public và private subnet trên nhiều availability zone.

* Cấu hình Internet Gateway và NAT Gateway để định tuyến traffic đúng hướng.

* Thiết lập route table cho cả subnet public và private.

* Áp dụng Security Groups và Network ACL để kiểm soát traffic vào/ra.

* Truy cập thành công EC2 trong private subnet qua Bastion Host.

* Hiểu về VPC Peering và VPC Endpoints để giao tiếp nội bộ an toàn.
