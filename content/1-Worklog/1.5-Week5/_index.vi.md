---
title: "Worklog Tuần 5"
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---



### Mục tiêu tuần 5:

* Nắm vững quy trình **Migration**: Hiểu và thực hành chuyển đổi máy ảo giữa môi trường **On-premise** và **AWS Cloud**.
* Tối ưu hóa vận hành: Triển khai tự động hóa để tiết kiệm chi phí hạ tầng và quản lý tài nguyên hệ thống hiệu quả.
* Giám sát hệ thống: Làm chủ công cụ trực quan hóa dữ liệu Grafana kết hợp với **AWS CloudWatch**.
* Phát triển dự án: Hoàn thiện đề xuất (Proposal) và kiến trúc sơ bộ cho dự án nhóm.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Dịch 3 bài blogs <br> - Khảo sát Proposal, lên sườn kiến trúc                                                                                             | 06/10/2025   | 06/10/2025      |
| 3   | - Meeting team báo cáo hằng tuần: phân công thực hiện tính năng. <br> - Tìm hiểu tổng quan về dịch vụ AWS VM Import/Export. <br> - Tìm hiểu lý thuyết liên quan: định dạng hỗ trợ, yêu cầu IAM, S3, ACL. <br> **Thực hành:** <br>&emsp; + Import máy ảo từ on-premise lên AWS  <br>&emsp; + Tạo AMI và khởi chạy EC2 từ máy ảo đã import <br> &emsp; + Export AMI/EC2 instance từ AWS về định dạng máy ảo                                | 07/10/2025   | 07/10/2025      | <https://000014.awsstudygroup.com/vi/> |
| 4 | - Tìm hiểu giải pháp tối ưu chi phí EC2 bằng AWS Lambda. <br> - Nghiên cứu kiến trúc: Lambda, EventBridge, IAM Role, EC2 Tag. <br> **Thực hành:** <br>&emsp; + Cấu hình Lambda tự động Start/Stop EC2. <br>&emsp; + Tạo IAM Role cho Lambda. <br>&emsp; + Thiết lập EventBridge Rule. <br>&emsp; + Tích hợp Slack Webhook để nhận thông báo. | 08/10/2025 | 08/10/2025 | https://000022.awsstudygroup.com/vi/ |
| 5 |- Tìm hiểu tổng quan về Grafana trên AWS và cách giám sát hệ thống. <br> - Tìm hiểu lý thuyết: kiến trúc Grafana, CloudWatch, IAM Role/User, Security Group. <br> **Thực hành:** <br>&emsp; + Triển khai VPC, Subnet và Security Group cho Grafana. <br>&emsp; + Tạo EC2 instance và gán IAM Role truy cập CloudWatch. <br>&emsp; + Cài đặt Grafana trên EC2 và cấu hình dịch vụ. <br>&emsp; + Thêm CloudWatch Data Source và tạo Dashboard giám sát CPU EC2. | 09/10/2025 | 09/10/2025 | https://000029.awsstudygroup.com/vi/ |
| 6 | - Meeting team báo cáo hằng tuần. <br> - Tìm hiểu tổng quan về Tag và Resource Groups trong AWS. <br> - Nghiên cứu lý thuyết: khái niệm Tag, mục đích gán metadata, cơ chế hoạt động Resource Groups. <br> **Thực hành:** <br>&emsp; + Tạo EC2 instance kèm Tag và quản lý Tag trên Console. <br>&emsp; + Lọc và tìm kiếm tài nguyên theo Tag. <br>&emsp; + Thêm/Xóa Tag bằng AWS CLI. <br>&emsp; + Tạo Resource Group dựa trên Tag và quản lý nhóm tài nguyên. | 10/10/2025 | 10/10/2025 | https://000027.awsstudygroup.com/vi/ |



### Kết quả đạt được tuần 5:

* Dự án: Khảo sát và xây dựng Proposal, lên ý tưởng sườn kiến trúc hệ thống với team và hoàn tất việc dịch thuật 3 bài blog chuyên ngành theo kế hoạch.
* Migration: Nắm vững cơ chế và thực hành thành công quy trình Import/Export máy ảo (hỗ trợ các định dạng VMDK/OVA) giữa môi trường On-premise và AWS thông qua S3 và AMI.
* Automation: Triển khai giải pháp tối ưu chi phí hạ tầng bằng cách kết hợp AWS Lambda và EventBridge để tự động Start/Stop EC2 theo lịch trình, tích hợp Webhook gửi thông báo trạng thái về Slack.
* Monitoring: Xây dựng thành công hệ thống giám sát với Grafana trên EC2, cấu hình kết nối CloudWatch Data Source để trực quan hóa các chỉ số hiệu năng (CPU/Network) lên Dashboard.
* Management: Thành thạo kỹ năng quản lý tài nguyên quy mô lớn thông qua Tagging và Resource Groups, bao gồm việc thực hiện gán nhãn, lọc tìm kiếm và quản lý metadata bằng cả Console và AWS CLI.


