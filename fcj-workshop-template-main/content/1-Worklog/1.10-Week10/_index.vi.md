---
title: "Worklog Tuần 10"
date: 2026-04-15
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Học Amazon Cognito: user pools, identity pools và authentication flows.
* Tích hợp Cognito với ứng dụng Next.js để kiểm soát truy cập bảo mật.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Tổng quan Amazon Cognito: User Pools vs Identity Pools <br> - Authentication flows: SRP, custom auth, hosted UI | 17/06/2026 | 17/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Cấu hình Cognito User Pool: password policy, MFA, email verification <br> - App clients và OAuth 2.0 scopes | 18/06/2026 | 18/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Thực hành:** <br>&emsp; + Tạo Cognito User Pool <br>&emsp; + Cấu hình app client với OAuth settings <br>&emsp; + Kiểm tra luồng đăng ký và đăng nhập | 19/06/2026 | 19/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Tích hợp Cognito với API Gateway authorizer <br> - Protected routes trong Next.js dùng Cognito JWT tokens | 20/06/2026 | 20/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Thực hành:** <br>&emsp; + Thêm Cognito JWT authorizer vào API Gateway <br>&emsp; + Implement login/logout trong Next.js <br>&emsp; + Chặn truy cập dashboard với người dùng chưa xác thực | 21/06/2026 | 21/06/2026 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 10:

* Cài đặt Amazon Cognito User Pool với password policy tùy chỉnh và email verification.

* Cấu hình OAuth 2.0 app client cho Next.js frontend.

* Implement luồng đăng ký, đăng nhập và đăng xuất trong web app.

* Bảo mật API Gateway endpoints bằng Cognito JWT authorizer.

* Giới hạn quyền truy cập dashboard chỉ cho các thành viên lab đã xác thực.

* Hiểu sự khác biệt giữa User Pools (authentication) và Identity Pools (authorization).
