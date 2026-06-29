---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Học AWS Glue: crawlers, ETL jobs và data catalog.
* Xây dựng pipeline xử lý dữ liệu để transform raw IoT data lưu trong S3.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tổng quan AWS Glue: Data Catalog, crawlers, databases, tables <br> - So sánh Glue với các ETL tool truyền thống | 29/09/2025 | 29/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Glue Crawlers: quét S3 để tự động tạo schema <br> - Glue Data Catalog là kho metadata tập trung | 30/09/2025 | 30/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - **Thực hành:** <br>&emsp; + Tạo Glue Crawler trên S3 bucket chứa raw IoT data <br>&emsp; + Chạy crawler và kiểm tra schema được tạo | 01/10/2025 | 01/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Glue ETL Jobs: PySpark script để transform dữ liệu <br> - Job triggers và scheduling | 02/10/2025 | 02/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành:** <br>&emsp; + Tạo Glue ETL job để transform và làm sạch IoT data <br>&emsp; + Ghi dữ liệu đã xử lý vào S3 output bucket <br>&emsp; + Xác minh kết quả bằng Athena | 03/10/2025 | 03/10/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 8:

* Hiểu hệ sinh thái AWS Glue và vai trò của nó trong kiến trúc data lake.

* Tạo và chạy Glue Crawlers để tự động catalog raw IoT data từ S3.

* Viết ETL job bằng PySpark để làm sạch, transform và tổng hợp dữ liệu cảm biến IoT.

* Lưu dữ liệu đã xử lý vào S3 output bucket dưới định dạng Parquet.

* Truy vấn và kiểm tra dữ liệu đã transform bằng Amazon Athena.
