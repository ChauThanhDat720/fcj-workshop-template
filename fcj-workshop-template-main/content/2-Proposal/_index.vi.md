---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Rookwork - Phần mềm quản lý làm việc nhóm  
## Hệ thống quản lý làm việc nhóm hỗ trợ cộng tác thời gian thực trên nền tảng desktop  

### 1. Tổng quan dự án  
Trong bối cảnh cách mạng công nghiệp 4.0 và xu hướng làm việc từ xa (remote working) cũng như làm việc lai (hybrid) ngày càng phổ biến, việc quản lý làm việc nhóm hiệu quả là một yếu tố sống còn đối với các cá nhân, nhóm dự án và doanh nghiệp. **Rookwork** là phần mềm quản lý làm việc nhóm tích hợp, hiện đại, được thiết kế để hoạt động dưới dạng ứng dụng đa nền tảng (browser và desktop app). Hệ thống sử dụng kiến trúc Client-Server với frontend phát triển bằng **React 19**, có thể đóng gói thành ứng dụng desktop bằng **Electron** để tạo trải nghiệm mượt mà, cùng backend vững chắc xây dựng trên nền tảng **Spring Boot** kết hợp cùng các dịch vụ của AWS.

> **Lưu ý về trạng thái hiện tại:** Ở giai đoạn hiện tại, nền tảng chính đang được người dùng sử dụng là phiên bản **web browser** (chạy trực tiếp trên trình duyệt, không cần cài đặt). Phiên bản **desktop (đóng gói bằng Electron)** đã được phát triển nhưng **chưa được cập nhật đồng bộ** với bản web mới nhất, do đó có thể còn thiếu một số tính năng hoặc bản vá so với phiên bản web hiện hành. Mục tiêu dài hạn của dự án vẫn là hoàn thiện và đồng bộ ứng dụng desktop đa nền tảng như định hướng kiến trúc ban đầu.

### 2. Vấn đề cần giải quyết  
Hiện nay, nhiều đội ngũ vẫn đối mặt với các khó khăn lớn trong việc cộng tác và quản lý dự án:
- **Sử dụng công cụ rời rạc:** Nhiều nhóm vẫn đang quản lý công việc thủ công qua các kênh không đồng bộ như Excel, Google Sheets, Messenger/Zalo và email. Điều này dẫn đến việc khó theo dõi tiến độ, dễ xảy ra nhầm lẫn, thiếu tính minh bạch và tiêu tốn nhiều thời gian trao đổi thông tin không cần thiết.
- **Cách thức sử dụng phức tạp:** Các nền tảng quản lý dự án hiện có (như Trello, Jira, Asana, Monday.com) thường có giao diện và luồng thao tác phức tạp, nhiều tầng cấu hình, đòi hỏi người dùng mất thời gian tìm hiểu và làm quen trước khi có thể sử dụng hiệu quả. Điều này gây khó khăn đặc biệt cho các nhóm nhỏ, sinh viên hoặc người mới bắt đầu, những đối tượng cần một công cụ đơn giản trực quan, dễ tiếp cận ngay từ lần sử dụng đầu tiên.
### 3. Kiến trúc giải pháp (Workflow)
Hệ thống hoạt động dựa trên mô hình phân tán trong môi trường AWS Cloud. Luồng xử lý được chia làm các hướng chính như sau:

![Rookwork Architecture](/images/2-Proposal/rookwork_architecture.jpg)

**1. Luồng Mạng và Phân phối Nội dung (Networking & Content Delivery):**
- Mọi yêu cầu từ người dùng (Users) đều được phân giải tên miền qua **Amazon Route 53**.
- Giao diện Frontend tĩnh được lưu trữ hoàn toàn trên bucket **Amazon S3 (FE Static)**.
- Để tăng tốc độ tải trang và bảo mật, nội dung Frontend được phân phối qua **Amazon CloudFront** kết hợp với hệ thống tường lửa **AWS WAF** giúp ngăn chặn các cuộc tấn công web.

**2. Luồng Định tuyến và Tính toán Backend (Routing & Compute):**
- Các API traffic đi qua **Internet Gateway** vào mạng **Amazon VPC**, sau đó được phân tải bởi **Application Load Balancer (ALB)**.
- Backend xây dựng bằng Java Spring Boot được triển khai trên các máy ảo **Amazon EC2**. Các máy chủ này được đặt an toàn trong *Private Subnets*.
- Để EC2 trong mạng nội bộ có thể gọi các dịch vụ bên ngoài, hệ thống định tuyến Outbound Traffic thông qua **NAT Gateway**.

**3. Luồng Cơ sở dữ liệu và Lưu trữ (Database & Storage):**
- Mọi dữ liệu nghiệp vụ lõi được lưu trữ trên **Amazon RDS (PostgreSQL)**, triển khai theo mô hình **Multi-AZ (DB Replication)** trên nhiều Availability Zones để dự phòng thảm họa.
- Quá trình quản lý thay đổi cấu trúc DB được thực hiện bởi Flyway.
- Các file đính kèm được EC2 ghi vào S3 thông qua một đường dẫn nội bộ bảo mật (Internal Routing) bằng **VPC S3 Gateway Endpoint**. Người dùng sau đó có thể tải file thông qua Direct File Access hoặc CloudFront một cách an toàn.

**4. Luồng Thông báo và Quản lý dùng chung (Notifications & Shared Services):**
- Mọi sự kiện kích hoạt email (như mời tham gia nhóm) được EC2 gọi trực tiếp đến **Amazon SES** để gửi cho Users.
- Chứng chỉ SSL/TLS được quản lý bởi **AWS Certificate Manager (ACM)** kết hợp chặt chẽ việc phân quyền hệ thống qua **AWS IAM**.

### 4. Triển khai kỹ thuật
*Yêu cầu kỹ thuật*
- **Backend:** Java Spring Boot, Spring Security (JWT/OAuth2), Spring Data JPA.
- **Database:** PostgreSQL, Flyway (Database Migration).
- **Frontend:** ReactJS / TypeScript.
- **Các dịch vụ AWS sử dụng:** 
  - *Mạng & Bảo mật:* Amazon Route 53, Amazon CloudFront, AWS WAF, Amazon VPC (IGW, NAT Gateway, ALB, S3 Gateway Endpoint), AWS ACM, AWS IAM.
  - *Tính toán & Lưu trữ:* Amazon EC2, Amazon RDS (PostgreSQL Multi-AZ), Amazon S3 (FE Static & File Storage).
  - *Khác:* Amazon SES (Email Notification).

### 7. Quá trình triển khai thực tế (từ Tuần 7)

Từ tuần 7 trở đi, song song với việc phát triển dự án **Rookwork**, quá trình học tập và ứng dụng các dịch vụ AWS chuyên sâu được đẩy mạnh. Các tuần này tập trung chủ yếu vào việc tìm hiểu, thực hành các dịch vụ AWS, đồng thời áp dụng kiến thức vào triển khai hạ tầng thực tế cho dự án.

---

#### 📅 Tuần 7 — AWS IoT Core & Giao thức MQTT
**Mục tiêu:** Học AWS IoT Core, kết nối thiết bị, giao thức MQTT, topics và rules.

**Các công việc AWS trọng tâm:**

| Dịch vụ AWS | Nội dung thực hiện | Kết quả |
|---|---|---|
| **AWS IoT Core** | Tìm hiểu tổng quan: device registry, message broker, rules engine | Nắm vững kiến trúc IoT Core và vai trò từng thành phần |
| **AWS IoT Core** | Tạo IoT Thing với chứng chỉ **X.509**, cấu hình device policy để kết nối MQTT bảo mật | IoT Thing hoạt động, device xác thực thành công qua cert |
| **AWS IoT Core** | Thực hành: giả lập thiết bị gửi MQTT messages, subscribe topics trong MQTT test client | Luồng publish/subscribe hoạt động ổn định |
| **IoT Rules Engine + Amazon S3 + AWS Lambda** | Tạo IoT rule dùng câu query SQL để định tuyến messages đến **S3** và trigger **Lambda** | Data ingestion end-to-end từ thiết bị giả lập đến cloud storage thành công |

*Ngoài AWS:* Tìm hiểu lý thuyết giao thức MQTT (QoS levels, retain messages) để phục vụ kết nối thiết bị.

**Kết quả tuần 7:** Hiểu kiến trúc AWS IoT Core, tạo và xác thực IoT Thing, xây dựng IoT Rules tự động định tuyến data đến S3 và Lambda, hoàn thành luồng data ingestion end-to-end.

---

#### 📅 Tuần 8 — AWS Glue & ETL Pipeline
**Mục tiêu:** Học AWS Glue, xây dựng pipeline xử lý và transform raw IoT data lưu trên S3.

**Các công việc AWS trọng tâm:**

| Dịch vụ AWS | Nội dung thực hiện | Kết quả |
|---|---|---|
| **AWS Glue Data Catalog** | Tìm hiểu tổng quan Glue: Data Catalog, crawlers, databases, tables | Hiểu vai trò Glue là kho metadata tập trung cho data lake |
| **AWS Glue Crawlers** | Tạo và chạy Glue Crawler trên S3 bucket chứa raw IoT data để tự động tạo schema | Schema được tạo tự động, catalog đúng cấu trúc dữ liệu |
| **AWS Glue ETL Jobs** | Viết ETL job bằng **PySpark** để transform, làm sạch và tổng hợp dữ liệu cảm biến IoT | Dữ liệu được làm sạch và ghi ra S3 output dưới định dạng **Parquet** |
| **Amazon Athena** | Truy vấn và xác minh dữ liệu đã transform bằng Athena | Kiểm tra kết quả ETL chính xác qua SQL query |

*Ngoài AWS:* Tìm hiểu cú pháp PySpark cơ bản để viết ETL script, so sánh Glue với các ETL tool truyền thống.

**Kết quả tuần 8:** Tạo và chạy Glue Crawler thành công, viết ETL job làm sạch data IoT, lưu kết quả Parquet lên S3, xác minh bằng Athena.

---

#### 📅 Tuần 9 — AWS Amplify & Triển khai Frontend
**Mục tiêu:** Học AWS Amplify, xây dựng và deploy ứng dụng Next.js với CI/CD tự động.

**Các công việc AWS trọng tâm:**

| Dịch vụ AWS | Nội dung thực hiện | Kết quả |
|---|---|---|
| **AWS Amplify Hosting** | Kết nối GitHub repo với Amplify, cấu hình build settings for Next.js | Deploy phiên bản đầu tiên của web app thành công |
| **AWS Amplify (CI/CD)** | Thiết lập pipeline tự động build và deploy khi push code lên GitHub | Mỗi commit tự động trigger build và deploy lên Amplify |
| **Amazon API Gateway** | Kết nối Next.js frontend với API Gateway endpoints để lấy dữ liệu IoT | Frontend fetch dữ liệu cảm biến thời gian thực từ API |
| **AWS Amplify (Environments)** | Cấu hình environment variables cho các môi trường dev/prod khác nhau | Quản lý config linh hoạt giữa các môi trường deployment |

*Ngoài AWS:* Thiết kế và implement dashboard hiển thị biểu đồ real-time nhiệt độ, độ ẩm bằng Next.js.

**Kết quả tuần 9:** Deploy thành công Next.js lên Amplify với CI/CD từ GitHub, xây dựng dashboard real-time hiển thị dữ liệu cảm biến từ API Gateway, hiểu vòng đời Amplify hosting và quản lý multi-environment.

---

#### 📅 Tuần 10 — Amazon Cognito & Xác thực người dùng
**Mục tiêu:** Học Amazon Cognito, tích hợp xác thực bảo mật vào ứng dụng Next.js.

**Các công việc AWS trọng tâm:**

| Dịch vụ AWS | Nội dung thực hiện | Kết quả |
|---|---|---|
| **Amazon Cognito User Pool** | Tạo User Pool với password policy tùy chỉnh, MFA, email verification | User Pool hoàn chỉnh, luồng đăng ký/đăng nhập hoạt động |
| **Amazon Cognito App Client** | Cấu hình OAuth 2.0 app client, scopes và Hosted UI cho Next.js | Frontend tích hợp đăng nhập qua Cognito Hosted UI |
| **Amazon API Gateway + Cognito Authorizer** | Thêm **Cognito JWT Authorizer** vào API Gateway để bảo vệ các endpoint | Chỉ user đã xác thực mới gọi được API, trả 401 với request không có token |
| **Amazon Cognito Identity Pools** | Tìm hiểu sự khác biệt giữa User Pools (authentication) và Identity Pools (authorization) | Hiểu mô hình phân quyền AWS cấp độ resource |

*Ngoài AWS:* Implement luồng login/logout và protected routes trong Next.js dùng Cognito JWT tokens.

**Kết quả tuần 10:** Cài đặt Cognito User Pool, bảo mật API Gateway bằng JWT Authorizer, giới hạn truy cập dashboard chỉ cho thành viên đã xác thực.

---

#### 📅 Tuần 11 — Kiểm thử tích hợp End-to-End toàn hệ thống
**Mục tiêu:** Tích hợp và kiểm thử toàn bộ pipeline: IoT Core → S3 → Glue → API Gateway → Amplify.

**Các công việc AWS trọng tâm:**

| Dịch vụ AWS | Nội dung thực hiện | Kết quả |
|---|---|---|
| **AWS IoT Core + S3 + Glue + API Gateway + Amplify** | Chạy test luồng data đầy đủ với 5 thiết bị giả lập đồng thời | Dữ liệu chạy xuyên suốt pipeline, hiển thị đúng trên dashboard |
| **AWS IoT Core (Rules)** | Sửa lỗi misconfiguration trong IoT rule routing làm data không đến đúng đích | IoT rule hoạt động ổn định, data routing chính xác |
| **AWS Lambda** | Debug và fix Lambda timeout trong bước xử lý trigger từ IoT rule | Lambda xử lý trong giới hạn timeout, không còn lỗi |
| **AWS Glue ETL** | Tối ưu Glue ETL job bằng cách giảm data scan không cần thiết | Thời gian chạy ETL job giảm đáng kể |
| **Amazon API Gateway + Amplify** | Kiểm thử hiệu năng và tải của API Gateway và Lambda dưới tải đồng thời | Xác định bottleneck và điều chỉnh concurrency limit |

*Ngoài AWS:* Mapping lại luồng data toàn hệ thống, ghi chép các hạn chế đã biết.

**Kết quả tuần 11:** Hoàn thành tích hợp end-to-end toàn bộ platform, sửa nhiều lỗi tích hợp, tối ưu hiệu năng Glue ETL, xác minh data chạy đúng từ thiết bị giả lập đến dashboard.

---

#### 📅 Tuần 12 — Deploy Production & Hoàn thiện tài liệu
**Mục tiêu:** Deploy cuối cùng lên môi trường production, hoàn thiện tài liệu và chuẩn bị báo cáo thực tập.

**Các công việc AWS trọng tâm:**

| Dịch vụ AWS | Nội dung thực hiện | Kết quả |
|---|---|---|
| **AWS CDK** | Deploy toàn bộ stack lên production bằng CDK (Infrastructure as Code) | Hạ tầng production được khởi tạo nhất quán, có thể tái tạo |
| **Amazon CloudWatch** | Cấu hình CloudWatch alarms và dashboards để giám sát tất cả component quan trọng | Hệ thống có monitoring và alerting tự động |
| **Amazon Cognito** | Tạo và xác minh 5 tài khoản thành viên lab trong Cognito User Pool | Tất cả thành viên truy cập hệ thống thành công |
| **AWS Budgets + Cost Management** | Review toàn bộ tài nguyên AWS và chi phí, xác minh budget alerts | Chi phí nằm trong ngân sách **$0.70/tháng**, tài nguyên dev đã dọn dẹp |

*Ngoài AWS:* Viết tài liệu kỹ thuật (sơ đồ kiến trúc, API docs, deployment guide), hoàn thành và nộp báo cáo thực tập, demo platform cho giám sát viên.

**Kết quả tuần 12:** Deploy thành công toàn bộ platform lên production, CloudWatch monitoring đầy đủ, hoàn thành tài liệu kỹ thuật, demo thành công, dọn dẹp tài nguyên, chi phí AWS $0.70/tháng.

### 6. Đánh giá rủi ro
*Ma trận rủi ro*
- Lỗi thiết lập định tuyến (Routing) trong VPC khiến EC2 không kết nối được Internet hoặc DB: Ảnh hưởng cao, xác suất trung bình.
- Ngân sách AWS vượt quá mức do thiết lập NAT Gateway hoặc cấu hình Multi-AZ: Ảnh hưởng trung bình, xác suất cao (với tài khoản học tập).

*Chiến lược giảm thiểu*
- Cấu hình hạ tầng dưới dạng Code (IaC) để dễ bề kiểm soát.
- Đặt giới hạn chi phí (AWS Budgets) và cấu hình CloudWatch theo dõi lưu lượng mạng chặt chẽ. Đóng bớt DB Replication (Multi-AZ) trên môi trường Dev để tiết kiệm chi phí.