---
title: "Worklog Tuần 9"
date: 2026-04-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Học AWS Amplify: hosting, CI/CD và quản lý environment.
* Xây dựng và deploy ứng dụng Next.js trên Amplify.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Tổng quan AWS Amplify: hosting, backend và CI/CD pipeline <br> - So sánh Amplify với CloudFront + S3 static hosting | 10/06/2026 | 10/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Cài đặt project Next.js để deploy lên Amplify <br> - Environment variables và build settings trong Amplify | 11/06/2026 | 11/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Thực hành:** <br>&emsp; + Kết nối GitHub repo với Amplify <br>&emsp; + Cấu hình build settings cho Next.js <br>&emsp; + Deploy phiên bản đầu tiên của web app | 12/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Thiết kế real-time dashboard: hiển thị dữ liệu cảm biến IoT <br> - Kết nối Next.js frontend với API Gateway endpoints | 13/06/2026 | 13/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Thực hành:** <br>&emsp; + Implement data fetching từ API Gateway <br>&emsp; + Xây dựng biểu đồ real-time cho dữ liệu thời tiết <br>&emsp; + Deploy và kiểm tra trên Amplify | 14/06/2026 | 14/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

---

**🛠️ Dự án Rookwork — Phase 3: Deploy Backend lên EC2 + ALB + NAT Gateway**

| Thứ | Công việc Rookwork | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2 | - Khởi tạo Amazon EC2 instance (t3.medium) trong Private Subnet <br> - Cấu hình Application Load Balancer (ALB): target groups, health checks, listener rules | 10/06/2026 | 10/06/2026 | |
| 3 | - Đóng gói Spring Boot application thành Docker image <br> - Push image lên Amazon ECR, cấu hình EC2 pull và chạy container | 11/06/2026 | 11/06/2026 | |
| 4 | - Cấu hình NAT Gateway cho EC2 Private Subnet outbound traffic <br> - Kiểm tra kết nối EC2 → RDS trong Private Network | 12/06/2026 | 12/06/2026 | |
| 5 | - Cấu hình ALB Listener HTTPS với ACM certificate <br> - Thiết lập Auto Scaling Group cho EC2 (min: 1, desired: 1) | 13/06/2026 | 13/06/2026 | |
| 6 | - **Review & kiểm thử Phase 3:** <br>&emsp; + Test API calls qua ALB endpoint <br>&emsp; + Xác minh EC2 kết nối được RDS và gọi ngoài qua NAT <br>&emsp; + Lập kế hoạch phát triển Frontend (Phase 4) | 14/06/2026 | 14/06/2026 | |


### Kết quả đạt được tuần 9:

* Deploy thành công ứng dụng Next.js lên AWS Amplify với CI/CD tự động từ GitHub.

* Cấu hình Amplify build settings và environment variables cho các môi trường deployment khác nhau.

* Xây dựng giao diện dashboard real-time để hiển thị dữ liệu cảm biến thời tiết lấy từ API Gateway.

* Implement biểu đồ động để trực quan hóa nhiệt độ, độ ẩm và các chỉ số cảm biến khác.

* Hiểu vòng đời Amplify hosting và cách quản lý nhiều environment (dev/prod).

* **[Rookwork Phase 3]** Deploy Spring Boot Backend lên Amazon EC2 qua Docker container, cấu hình ALB HTTPS, NAT Gateway và xác minh kết nối nội bộ EC2 ↔ RDS thành công.

