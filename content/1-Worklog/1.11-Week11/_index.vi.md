---
title: "Worklog Tuần 11"
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---



### Mục tiêu tuần 11:

* Phát triển tính năng lõi (Core Features): Tập trung xây dựng và hoàn thiện logic cho các **Lambda Functions** quan trọng liên quan đến AI **(RAG, Analyzer, Generator)**.
* Hoàn thiện cấu trúc (Architecture): Chốt cấu trúc source code Backend để đảm bảo tính tổ chức và khả năng mở rộng.
* Tối ưu hóa và Xử lý lỗi (Optimization): Giải quyết các vấn đề hiệu năng đặc thù của Serverless **(Timeout, Cold Start)** khi tích hợp với LLM.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Nghiên cứu, hỗ trợ chỉnh sửa Lambda Function (RAG SEARCH). <br> - Học cách phát triển Backend Project. | 10/11/2025   | 10/11/2025      | <https://www.youtube.com/watch?v=KAV8vo7hGAo>|
| 3   | - Nghiên cứu, hỗ trợ chỉnh sửa Lambda Function (LLM ANALYZER). <br> - Học cách phát triển Backend Project. <br> - Họp team để báo cáo tiến độ công việc. | 11/11/2025   | 11/11/2025      | <https://www.youtube.com/watch?v=KAV8vo7hGAo>|
| 4   | - Nghiên cứu, hỗ trợ chỉnh sửa Lambda Function (GENERATE CONTRACT). <br> - Học cách phát triển Backend Project. | 12/11/2025   | 12/11/2025      | <https://www.youtube.com/watch?v=KAV8vo7hGAo>|
| 5   | - Hoàn thành cơ bản cấu trúc, nội dung cơ bản folder Backend. <br> - Học cách phát triển Backend Project. | 13/11/2025   | 13/11/2025      | <https://www.youtube.com/watch?v=KAV8vo7hGAo>|
| 6   | - Họp team để báo cáo tiến độ công việc. <br> - Sửa những lỗi liên quan đến Lambda như Timeout, Coldstart, LLM,v.v. | 14/11/2025   | 14/11/2025      | <https://www.youtube.com/watch?v=KAV8vo7hGAo>|



### Kết quả đạt được tuần 11:

* Serverless AI Functions: Xây dựng và tinh chỉnh thành công 3 functions chủ chốt:
  * RAG Search: Tìm kiếm thông tin dựa trên ngữ cảnh văn bản.
  * LLM Analyzer: Phân tích và đánh giá nội dung hợp đồng.
  * Generate Contract: Tự động tạo thảo văn bản hợp đồng.
* Backend Maturity: Hoàn tất cấu trúc thư mục và nội dung nền tảng cho Backend, sẵn sàng cho các bước tích hợp tiếp theo.
* Performance Tuning:
  * Chưa khắc phục được lỗi Timeout khi xử lý tác vụ LLM tốn nhiều thời gian.
  * Giảm thiểu tác động của Cold Start lên trải nghiệm người dùng.
  * Xử lý các lỗi logic phát sinh trong quá trình tích hợp mô hình ngôn ngữ lớn (LLM).
