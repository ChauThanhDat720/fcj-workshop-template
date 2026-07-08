---
title: "Blog 2"
date: 2026-07-02
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Giới thiệu Dashboard Tổng quan Traffic của AWS WAF

Hôm nay mình muốn chia sẻ về một bản cập nhật cực kỳ hữu ích giúp mọi người vận hành hệ thống nhàn hơn rất nhiều: Dashboard tổng quan traffic của AWS WAF.

Đối với anh em làm bảo mật mạng, việc bảo vệ uptime cho ứng dụng đòi hỏi phải liên tục theo dõi baseline traffic và điều tra các IP đáng ngờ. Bài toán đặt ra là làm sao mở rộng quy mô ứng dụng mà không cần phải "phình to" đội ngũ SOC (Security Operations Center). Để giải quyết "nỗi đau" này, AWS WAF đã ra mắt dashboard tổng quan về traffic, giúp anh em đưa ra quyết định nhanh chóng và chính xác.

## Dashboard này có gì đặc biệt?

Điểm đáng giá nhất là nó hoàn toàn miễn phí và có sẵn mặc định, anh em không cần tốn công setup.

Dashboard cung cấp cái nhìn gần như realtime về các metric từ CloudWatch mà WAF thu thập được. Anh em có thể xem tổng request, request bị chặn/được phép, so sánh traffic bot và non-bot, hay top 10 rule đang hoạt động mạnh nhất. Đặc biệt, công cụ Sampled requests giờ đã được tách thành một tab riêng, cho phép xem chi tiết 100 request khớp rule và 100 request áp dụng action mặc định trong 3 giờ gần nhất.

Nó phân loại request với bảng phân tích chi tiết (loại tấn công, loại thiết bị, quốc gia). Ví dụ, nếu ứng dụng của anh em chỉ dành cho Desktop ở Việt Nam, nhưng lại thấy traffic từ Mobile ở Pháp tăng vọt, anh em có thể quyết định chặn ngay lập tức.

## Use Case 1: Phân tích Pattern và "Bắt bệnh" hệ thống

Không chỉ để xem cho đẹp, anh em hãy dùng dashboard để săn lùng các đợt tăng vọt (spike) bất thường. Giả sử bình thường hệ thống nhận 2.000 request/phút, nay bỗng nhảy lên 10.000 request/phút kèm theo loại thiết bị không mong muốn, đó là tín hiệu để điều tra ngay.

Nếu dashboard hiển thị một rule đang phải chặn một lượng lớn traffic, nó sẽ chỉ ra rõ hệ thống đang bị nhắm mục tiêu bằng một vector tấn công cụ thể.

**Hành động tiếp theo sau khi phân tích:**
- **Tinh chỉnh rule WAF:** Chỉnh sửa regex để giảm nhận diện nhầm (false positives) hoặc bỏ lọt (false negatives).
- **Chặn IP tự động:** Sử dụng danh sách Amazon IP reputation list để auto-chặn các IP độc hại.
- **Xử lý DDoS:** Monitor IP nguồn và dùng rate-based rules để cắt đuôi các đợt tăng vọt request.

## Use Case 2: Theo dõi và Tối ưu Bot Control

Nếu anh em đang dùng AWS WAF Bot Control, dashboard này sẽ cho thấy rõ bao nhiêu % traffic đến từ Bot (scraper, scanner, crawler...).

- **Giai đoạn đầu (onboarding):** Anh em nên bật các rule group Bot Control ở chế độ Count và dùng dashboard để xem có traffic hợp lệ nào bị gán nhãn nhầm không (từ đó thêm rule exception).
- **Xử lý bot tinh vi:** AWS WAF sẽ dùng kỹ thuật browser fingerprinting, thử thách ngầm hoặc CAPTCHA và gán Token. Bảng Token status trên dashboard sẽ giúp anh em theo dõi lượng request thiếu Token hoặc Token không hợp lệ. Từ đó, anh em có thể viết rule chạy ngay sau nhóm managed rule để chặn đứng hoặc giới hạn tốc độ (rate limit) các request không vượt qua được bài kiểm tra bot này.

## So sánh nhanh: WAF Dashboard vs CloudFront Security Dashboard

Nhiều anh em thắc mắc dùng cái nào thì tốt hơn:
- **AWS WAF Traffic Overview Dashboard:** Dành cho anh em cần phân tích sâu (investigate), tìm hiểu pattern traffic để tinh chỉnh rule bảo mật chi tiết.
- **CloudFront Security Dashboard:** Dành cho anh em muốn quản lý chung cả phân phối ứng dụng và bảo mật cơ bản trên một màn hình duy nhất mà không cần chuyển console.

## Tổng kết

Dashboard mới này thực sự giúp anh em bớt đi việc phải "đoán mò" khi phân tích traffic. Về chi phí, dashboard được cung cấp miễn phí, anh em chỉ trả phí lưu trữ log cho CloudWatch nếu bật full logging.

*Nguồn: Introducing the AWS WAF traffic overview dashboard | AWS Security Blog*

*Link bài đăng Facebook: [AWS Study Group VN](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2202070817224545/?rdid=BDhnVySASHqbx6an#)*

![Image 1](/images/blog2/image1.png)

![Image 2](/images/blog2/image2.png)