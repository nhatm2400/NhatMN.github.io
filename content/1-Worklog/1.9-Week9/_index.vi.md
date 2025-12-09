---
title: "Worklog Tuần 9"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---



### Mục tiêu tuần 9:

* Thiết kế hệ thống (System Design): Xây dựng kiến trúc Backend và mô hình hóa luồng dữ liệu **(Data Flow)** của dự án.
* Triển khai tầng dữ liệu (Data Layer): Thiết lập hạ tầng lưu trữ và cơ sở dữ liệu trên AWS **(S3, DynamoDB)**.
* *ảo mật và Vận hành: Cấu hình **IAM** và các chính sách bảo mật cần thiết để chuẩn bị cho việc Deployment.
* Phát triển dự án: Phối hợp nhóm để thống nhất giải pháp kỹ thuật và tiến độ.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu về các hạ tầng cần thiết cho Backend Project. <br> - Học cách phát triển Backend Project.                                                                                             | 27/10/2025   | 27/10/2025      | <https://www.youtube.com/watch?v=KAV8vo7hGAo>|
| 3   | - Thiết kế hệ thống Backend. <br> - Vẽ luồng dữ liệu (Data Flow). <br> - Họp team để báo cáo tiến độ Project.                                                                                              | 28/10/2025   | 28/10/2025                                   
| 4   | - Tìm hiểu về Database.  <br> - Setup các Database cơ bản: S3 bucket và DynamoDB. <br> - Tạo IAM User cho việc Deploy. | 29/10/2025   | 29/10/2025  
| 5   | - Tìm hiểu về cách setup IAM & Security. <br> - Học cách phát triển Backend. | 30/10/2025   | 30/10/2025 | <https://www.youtube.com/watch?v=KAV8vo7hGAo>|
| 6   | - Họp team để báo cáo tiến độ Project.    | 31/10/2025   | 31/10/2025 


### Kết quả đạt được tuần 9:

* Architecture: Hoàn thiện bản vẽ thiết kế hệ thống Backend và sơ đồ luồng dữ liệu (Data Flow Diagram), thống nhất giải pháp với team.
* Database & Storage:
  * Khởi tạo thành công Amazon S3 Bucket để lưu trữ static assets/files.
  * Thiết lập các bảng Amazon DynamoDB cơ bản phục vụ cho ứng dụng.
* Security (IAM):
  * Tạo và cấu hình IAM User chuyên biệt cho việc Deployment.
  * Áp dụng các Policy bảo mật cơ bản để kiểm soát quyền truy cập tài nguyên.
* Backend Foundation: Nắm vững các thành phần hạ tầng cần thiết và quy trình phát triển Backend trên môi trường AWS.