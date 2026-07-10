---
title: "Worklog Tuần 12"
date: 2026-04-15
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12:

* Deploy cuối cùng IoT Weather Platform lên môi trường production.
* Hoàn thiện tài liệu kỹ thuật và chuẩn bị báo cáo thực tập.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Review cuối cùng tất cả tài nguyên AWS và chi phí <br> - Xác minh cấu hình AWS budget alerts đúng | 01/07/2026 | 01/07/2026 |  |
| 3 | - Deploy production: CDK stack deploy cuối cùng <br> - Cấu hình CloudWatch alarms và dashboards để giám sát | 02/07/2026 | 02/07/2026 |  |
| 4 | - **Thực hành:** <br>&emsp; + Kiểm thử production end-to-end lần cuối <br>&emsp; + Xác minh tất cả Cognito user accounts đang active <br>&emsp; + Giám sát system health trong 24 giờ | 03/07/2026 | 03/07/2026 |  |
| 5 | - Viết tài liệu kỹ thuật: sơ đồ kiến trúc, API docs, deployment guide <br> - Chuẩn bị demo cho buổi trình bày cuối kỳ thực tập | 04/07/2026 | 04/07/2026 |  |
| 6 | - Hoàn thành báo cáo thực tập <br> - Nộp các deliverable cuối cùng <br> - Dọn dẹp tài nguyên không cần thiết | 15/07/2026 | 15/07/2026 |  |

---

**🛠️ Dự án Rookwork — Phase 6: Kiểm thử End-to-End, Bảo mật & Bàn giao hệ thống**

| Thứ | Công việc Rookwork | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Kiểm thử end-to-end toàn bộ hệ thống Rookwork: Đăng nhập → Tạo Workspace → Mời thành viên (SES) → Upload file (S3) → Quản lý Task <br> - Ghi lại tất cả kết quả kiểm thử | 01/07/2026 | 01/07/2026 | |
| 3 | - Security review: kiểm tra IAM least-privilege, Security Group rules, S3 bucket policies <br> - Xác minh JWT token expiry, CORS policy và WAF rule hoạt động đúng | 02/07/2026 | 02/07/2026 | |
| 4 | - Cấu hình Amazon CloudWatch: tạo alarms cho EC2 CPU, RDS connections, ALB 5xx errors <br> - Thiết lập AWS Budgets: cảnh báo chi phí vượt ngưỡng | 03/07/2026 | 03/07/2026 | |
| 5 | - Viết tài liệu kỹ thuật Rookwork: sơ đồ kiến trúc AWS, API reference, hướng dẫn deployment <br> - Chuẩn bị tài liệu bàn giao và demo system cho supervisor | 04/07/2026 | 04/07/2026 | |
| 6 | - **Hoàn thiện & Bàn giao Phase 6:** <br>&emsp; + Demo hệ thống Rookwork hoàn chỉnh <br>&emsp; + Dọn dẹp tài nguyên AWS không cần thiết (Multi-AZ dev, NAT Gateway test) <br>&emsp; + Xác minh chi phí AWS nằm trong ngân sách | 15/07/2026 | 15/07/2026 | |


### Kết quả đạt được tuần 12:

* Deploy thành công toàn bộ IoT Weather Platform lên production bằng AWS CDK.

* Cấu hình CloudWatch monitoring và alerts cho tất cả các component quan trọng.

* Tạo và xác minh 5 tài khoản thành viên lab trong Amazon Cognito.

* Hoàn thành đầy đủ tài liệu kỹ thuật bao gồm kiến trúc hệ thống, API reference và deployment guide.

* Demo thành công platform cho các giám sát viên thực tập.

* Dọn dẹp tài nguyên development và xác nhận chi phí AWS nằm trong ngân sách $0.70/tháng.

* Hoàn thành và nộp báo cáo thực tập đúng hạn.

* **[Rookwork Phase 6]** Hoàn thành kiểm thử end-to-end toàn hệ thống Rookwork, thực hiện security review đầy đủ, cấu hình CloudWatch monitoring, hoàn thiện tài liệu kỹ thuật và demo bàn giao thành công cho supervisor.

