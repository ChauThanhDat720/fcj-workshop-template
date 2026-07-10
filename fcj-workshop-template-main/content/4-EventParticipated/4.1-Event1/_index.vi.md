---
title: "Event 1"
date: 2026-04-17
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Báo cáo tham gia sự kiện: GenAI-powered App-DB Modernization workshop

### 1. Ý nghĩa và mục tiêu của sự kiện
Sự kiện mang đến góc nhìn thực tiễn về việc ứng dụng Trí tuệ Nhân tạo (AI) sao cho hiệu quả thông qua việc xây dựng đúng ngữ cảnh. Đồng thời, chương trình cũng giới thiệu các bộ công cụ AI giúp tối ưu quá trình phân tích dữ liệu và làm việc nhóm.

Người tham gia được tìm hiểu sâu về Amazon CloudFront – nền tảng mạng toàn diện giúp doanh nghiệp tiết kiệm chi phí mà vẫn đảm bảo hiệu năng và tính bảo mật. Đặc biệt, sự kiện còn chia sẻ những bài học thực tế từ dự án UTMorpho (giải đấu LotusHacks), cũng như cách xử lý sự thiếu ổn định của các mô hình ngôn ngữ lớn (LLM) và cách ứng dụng kiến trúc Multi-Agent trong việc chấm điểm tín dụng.

### 2. Tổng quan nội dung chương trình
Chương trình tập trung phân tích các công nghệ mũi nhọn thuộc hệ sinh thái AWS, bao gồm GenAI, Hệ thống đa tác nhân, bảo mật hạ tầng với CloudFront và các phương pháp vận hành tối ưu.

**Ứng dụng GenAI và Hệ thống Multi-Agent:**
- **Giải pháp đánh giá tín dụng (Vy Lam - VPBank):** Trình bày cách dùng mô hình Virtual Credit Committee (gồm nhiều Agent nhỏ chuyên biệt xử lý các khía cạnh tài chính, thị trường, rủi ro) để đánh giá các startup thiếu tài sản thế chấp. Kết quả là giảm được 95% thời gian và chi phí, đồng thời tăng gấp đôi tỷ lệ phê duyệt hồ sơ.
- **Tự động hóa quy trình (Phạm Ng Hải Anh):** Sử dụng Amazon Quick Suite để tạo ra các AI Agent đảm nhận các công việc lặp đi lặp lại như tóm tắt biên bản cuộc họp (MoM) hay tự động gửi email thông báo.

**Kỹ thuật triển khai AI:**
- **Vai trò của Context (Tinh Truong):** AI thường đưa ra kết quả sai lệch vì thiếu thông tin nền tảng, không phải do khả năng của mô hình. Việc cung cấp ngữ cảnh đúng trọng tâm sẽ mang lại hiệu quả cao hơn là nhồi nhét quá nhiều dữ liệu rác.
- **Tính không đồng nhất của LLM (Đức Đào):** Kể cả khi thiết lập Temperature = 0, kết quả đầu ra của LLM đôi khi vẫn có sự khác biệt. Do đó, nên cài đặt Temperature = 0.1, áp dụng cơ chế Majority Voting và định dạng đầu ra chuẩn (JSON) để hệ thống hoạt động ổn định nhất.

**Hạ tầng bảo mật cùng Amazon CloudFront:**
- AWS ra mắt các gói cước cố định cho CloudFront, giúp doanh nghiệp tránh được "cú sốc chi phí" khi bị tấn công DDoS hoặc bị quá tải truy cập. 
- CloudFront còn giúp giảm tải CPU cho các máy chủ EC2 nhờ đảm nhận việc nén dữ liệu và xử lý các giao thức bảo mật TLS, kết hợp với mạng lưới Edge toàn cầu để chặn đứng DDoS từ xa.

**Case Study thực chiến từ UTMorpho:**
- Một dự án AI giúp sinh ra giao diện UI từ đoạn văn bản mô tả và cho phép người dùng chỉnh sửa trực tiếp (WYSIWYG). Bài học đáng giá nhất từ đội ngũ là sự phối hợp ăn ý và thấu hiểu vấn đề thực tế sẽ quyết định thành công của một sản phẩm được làm ra trong thời gian ngắn (36 tiếng hackathon).

### 3. Bài học kinh nghiệm

**Góc độ AI & Hạ tầng:**
- Việc sử dụng AI hiệu quả không chỉ dựa vào câu lệnh (prompt) mà phụ thuộc rất lớn vào ngữ cảnh. Khái niệm "Second AI Brain" đang mở ra xu hướng xây dựng bộ nhớ dài hạn cá nhân hóa cho AI.
- Các mô hình LLM không bao giờ ổn định tuyệt đối, do đó cần có chiến lược kiểm thử, giám sát và quản trị rủi ro chặt chẽ trước khi triển khai thực tế.
- CDN (CloudFront) không chỉ là công cụ phân phối nội dung tĩnh mà còn là tấm khiên bảo vệ hệ thống khỏi các nguy cơ bảo mật, đồng thời tối ưu hóa chi phí hạ tầng.

**Góc độ xây dựng sản phẩm:**
- Trong phát triển sản phẩm, việc định hình rõ ràng bài toán cần giải quyết quan trọng hơn việc cắm cúi viết code ngay lập tức. Tại các môi trường áp lực (như hackathon), cần biết cách ưu tiên hoàn thiện các tính năng cốt lõi.

### 4. Kế hoạch áp dụng vào thực tế
- Tối ưu hóa cách sử dụng AI trong học tập: tập trung cung cấp ngữ cảnh rõ ràng và mục tiêu cụ thể hơn thay vì chỉ gõ prompt đơn giản.
- Tự xây dựng các workflow tự động bằng AI phục vụ việc tổng hợp tài liệu và ghi chú cá nhân.
- Tìm hiểu sâu về cách cấu hình Amazon CloudFront cho các dự án Web cá nhân nhằm cải thiện tốc độ và tính bảo mật.
- Chấp nhận thiết kế cơ chế kiểm tra chéo (validation) mỗi khi tích hợp LLM vào ứng dụng thực tế.

### 5. Cảm nhận tổng quan
Sự kiện đã giúp tôi thay đổi hoàn toàn tư duy về cách sử dụng AI. Trước đây tôi nghĩ chỉ cần có câu lệnh hay là đủ, nhưng thông điệp "Context is everything" thực sự đã làm tôi thức tỉnh về vai trò của ngữ cảnh và dữ liệu đầu vào. 

Bên cạnh đó, những kiến thức thực tiễn về hạ tầng CloudFront cũng như câu chuyện truyền cảm hứng từ team phát triển UTMorpho trong 36 giờ đã tiếp thêm động lực để tôi theo đuổi và tìm hiểu sâu hơn về kiến trúc Cloud, Multi-Agent System và phát triển sản phẩm trong tương lai.

#### Hình ảnh thực tế từ chương trình
![Virtual credit committee architecture](/images/4.1-Event1/virtual-credit-committee.png)
_Sơ đồ kiến trúc hệ thống Multi-Agent trong việc đánh giá tín dụng_

![Proposed Deployment Approach](/images/4.1-Event1/deployment-approach.png)
_Mô hình triển khai nền tảng AgentCore trên AWS_

![Why CloudFront is better equipped for volumetric attack](/images/4.1-Event1/cloudfront-ddos.png)
_Cơ chế chống tấn công DDoS hiệu quả của CloudFront_

![Architecture](/images/4.1-Event1/utmorpho-architecture.png)
_Cấu trúc hạ tầng của dự án UTMorpho_

![The role of Temperature, Top-P, and Top-K](/images/4.1-Event1/llm-temperature.png)
_Sự ảnh hưởng của tham số Temperature đối với kết quả của LLM_

{{% notice info %}}
Tổng kết lại, đây là một trải nghiệm học hỏi vô cùng giá trị, cung cấp cho tôi bức tranh toàn cảnh về cách kết hợp giữa công nghệ AI, hạ tầng Cloud và tư duy kinh doanh để giải quyết các bài toán khó trong thực tế.
{{% /notice %}}
