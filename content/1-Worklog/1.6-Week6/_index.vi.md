---
title: "Worklog Tuần 6"
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---



### Mục tiêu tuần 6:

* Quản trị và Phân loại tài nguyên: Nắm vững chiến lược gán nhãn (Tagging Strategy) để quản lý tài nguyên hiệu quả và tổ chức Resource Groups.
* Bảo mật nâng cao: Hiểu và thực hành cơ chế kiểm soát truy cập dựa trên thuộc tính (Attribute-Based Access Control) sử dụng IAM Policies kết hợp với Tags và Region.
* Tự động hóa hạ tầng (IaC): Làm chủ AWS CloudFormation để triển khai, quản lý và nhân bản hạ tầng dưới dạng code (Templates, Stacks, StackSets).
* Tiến độ dự án: Chốt phương án Proposal và bắt đầu xây dựng kiến trúc Backend.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tiếp tục sửa proposal                                                                                             | 13/10/2025   | 13/10/2025      |
| 3 | - Tìm hiểu cơ chế Tag và Resource Groups trong AWS. <br> - Nghiên cứu lý thuyết: khái niệm Tag, mục đích phân loại tài nguyên, cách hoạt động của Resource Groups. <br> **Thực hành:** <br>&emsp; + Tạo EC2 instance kèm Tag và quản lý Tag trên Console. <br>&emsp; + Thêm/Xóa Tag và lọc tài nguyên theo Tag. <br>&emsp; + Gán Tag bằng AWS CLI và tìm kiếm tài nguyên bằng filters. <br>&emsp; + Tạo Resource Group dựa trên Tag và xem danh sách tài nguyên. | 14/10/2025 | 14/10/2025 | https://000027.awsstudygroup.com/vi/ |
| 4 | - Tìm hiểu cơ chế kiểm soát truy cập EC2 bằng IAM và Resource Tags. <br> - Nghiên cứu lý thuyết: IAM Least Privilege, IAM Conditions, giới hạn truy cập theo Region và Tag. <br> **Thực hành:** <br>&emsp; + Tạo 5 IAM Policies kiểm soát quyền EC2 theo Tag và Region. <br>&emsp; + Tạo IAM Role `ec2-admin-team-alpha` và gán các policy. <br>&emsp; + Switch Role và kiểm thử: tạo EC2 đúng/sai Tag, truy cập Region cho phép/không cho phép, sửa Tag và quản lý Instance. <br>&emsp; + Xóa Role và Policies sau khi hoàn thành. | 15/10/2025 | 15/10/2025 | https://000028.awsstudygroup.com/vi/ |
| 5 | - Meeting team báo cáo hằng tuần: phân công thực hiện tính năng. <br> - Tìm hiểu tổng quan về AWS CloudFormation và cơ chế Infrastructure as Code. <br> - Nghiên cứu lý thuyết: cấu trúc template, intrinsic functions, pseudo parameters, Cloud9, Custom Resources, Mappings, StackSets và Drift Detection. <br> **Thực hành:** <br>&emsp; + Tạo IAM User/Role và thiết lập môi trường Cloud9. <br>&emsp; + Viết và lint template EC2 cơ bản, deploy stack và kiểm tra Outputs. <br>&emsp; + Tạo Custom Resource bằng Lambda để sinh SSH Key. <br>&emsp; + Tạo StackSets deploy EC2 đa vùng và thực hiện Drift Detection. | 16/10/2025 | 16/10/2025 | https://000037.awsstudygroup.com/vi/ |
| 6   | - Họp team báo cáo hằng tuần. <br> - Bắt đầu tìm hiểu cấu trúc Backend cho Project                                                                                         | 17/10/2025   | 17/10/2025      


### Kết quả đạt được tuần 6:

* Dự án: Phát triển Proposal và tìm hiểu cấu trúc Backend cơ bản.
* Management: Hiểu biết cơ bản về phân loại tài nguyên quy mô lớn bằng Tagging Strategy và Resource Groups.
* Security: Triển khai thành công cơ chế phân quyền nâng cao sử dụng IAM Policies kết hợp điều kiện về Tag và Region.
* CloudFormation: Làm chủ quy trình "Infrastructure as Code": viết Template, tạo Custom Resource bằng Lambda, deploy đa vùng (StackSets) và kiểm tra đồng bộ (Drift Detection).

