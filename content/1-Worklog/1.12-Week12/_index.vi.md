---
title: "Worklog Tuần 12"
weight: 2
chapter: false
pre: " <b> 1.12 </b> "
---


### Mục tiêu tuần 12:

* Tích hợp hệ thống **(System Integration)**: Kết nối hoàn chỉnh Backend với các **AWS Lambda Functions** **(AI services)** và xử lý vấn đề tương thích.
* Hoàn thiện hạ tầng **(Infrastructure Setup)**: Cấu hình các dịch vụ bảo mật **(Cognito, Secrets Manager)** và giám sát **(CloudWatch)**.
* Triển khai Full-stack **(Deployment)**: Ghép nối **Frontend - Backend** và triển khai ứng dụng hoàn chỉnh lên **AWS Amplify**.
* Kiểm thử và Ổn định **(QA & Bug Fixing)**: Đảm bảo luồng hoạt động mượt mà, khắc phục các lỗi logic về **Authentication**, **Database** và **AI Editor**.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tích hợp các ARN LAMBDA vào code Backend. <br> - Fix các lỗi như code Backend không tương thích với Lambda. <br> - Học cách phát triển Backend Project. | 17/11/2025   | 17/11/2025      | <https://www.youtube.com/watch?v=KAV8vo7hGAo>|
| 3   | - Gắn đầy đủ các config. <br> - Chạy thử Backend và test các chức năng trên Postman (generate, upload contract, chatbot, rag,v.v.) <br> - Fix các lỗi tồn đọng liên quan đến logic trong code | 18/11/2025   | 18/11/2025      |
| 4   | - Setup các mục khác như Cognito, Secret Managers, CloudWatch. <br> - Chạy thử lại Backend và test các chức năng trên. <br> - Fix các lỗi tồn đọng liên quan đến logic trong code. | 19/11/2025   | 19/11/2025      |
| 5   | - Nối Backend với Frontend. <br> - Thiết lập các luồng với nhau, đẩy lên Amplify. <br> - Fix các lỗi tồn đọng liên quan đến logic trong code. | 20/11/2025   | 20/11/2025      |
| 6   | - Họp team để báo cáo kết quả cuối cùng. <br> - Fix các lỗi như không đổi được mật khẩu, template hợp đồng không lưu được, chưa dùng được AI trong cửa sổ editor. <br> - Fix các lỗi tồn đọng liên quan đến logic trong database và cognito. | 21/11/2025   | 21/11/2025      |


### Kết quả đạt được tuần 12:

* Backend & Serverless Integration:
  * Tích hợp thành công ARN của các Lambda Functions (RAG, Chatbot, Generator) vào Backend.
  * Khắc phục hoàn toàn lỗi không tương thích môi trường giữa Node.js Backend và AWS Lambda.
  * Xử lý các lỗi logic phát sinh trong quá trình tích hợp mô hình ngôn ngữ lớn (LLM).
* Security & Monitoring:
  * Thiết lập xong Amazon Cognito cho User Pool/Identity Pool.
  * Cấu hình Secrets Manager để quản lý biến môi trường an toàn và CloudWatch để ghi log hệ thống.
* Functional Testing:
  * Kiểm thử thành công qua Postman các tính năng lõi: Upload hợp đồng, RAG Search, Chatbot AI và Generate Contract.
* Deployment & Bug Fixing:
  * Kết nối thành công Frontend với Backend.
  * Triển khai (Deploy) ứng dụng lên AWS Amplify.
  * Fix xong các lỗi nghiệp vụ quan trọng: Chức năng đổi mật khẩu (Cognito), lưu Template hợp đồng (Database) và lỗi gọi AI trong trình soạn thảo (Editor).






