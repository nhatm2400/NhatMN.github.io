---
title: "Event 3"
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---



### DevOps on AWS

### I. Thông tin chung về sự kiện

* **Tên sự kiện:** AWS Cloud Mastery Series #2 – DevOps on AWS  
* **Thời gian:** Thứ Hai, ngày 17/11/2025, từ 8h30 đến 17h00  
* **Địa điểm:** Văn phòng AWS Việt Nam  
* **Đối tượng tham dự:** Sinh viên, thực tập sinh và kỹ sư trẻ quan tâm đến DevOps, vận hành hệ thống và tự động hóa hạ tầng trên AWS.  
* **Mục tiêu chính của buổi học:**  
  * Hiểu rõ **DevOps mindset**, lý do DevOps/Platform Engineering trở thành vai trò trọng yếu trong tổ chức hiện đại.  
  * Nắm được hệ sinh thái **AWS DevOps Services** (CodeCommit, CodeBuild, CodeDeploy, CodePipeline) và quy trình xây dựng CI/CD pipeline hoàn chỉnh.  
  * Làm quen với tư duy **Infrastructure as Code (IaC)** thông qua CloudFormation và AWS CDK; hiểu vì sao việc quản lý bằng giao diện console không hiệu quả khi hệ thống phát triển lớn.  
  * Hệ thống hóa các lựa chọn **dịch vụ container** trên AWS gồm ECR, ECS, EKS và App Runner cùng chiến lược triển khai phù hợp.  
  * Hiểu các khái niệm và công cụ **Monitoring & Observability** (CloudWatch, X-Ray, Grafana, Prometheus) để vận hành hệ thống chủ động và đáng tin cậy.  

---

### II. Nội dung chi tiết chương trình trong ngày


#### 2.1. Phiên sáng – DevOps Mindset & CI/CD & IaC

---

**2.1.1. 8:30 – 9:00 | Welcome & DevOps Mindset (Quang Tịnh – Platform Engineer)**

* Mở đầu, diễn giả **Quang Tịnh** kết nối nội dung với buổi AI/ML trước và đặt nền tảng cho ngày học: DevOps sinh ra để giải quyết khoảng cách giữa **Development** và **Operations**.  
* DevOps không phải tên một vị trí cụ thể mà là **tư duy làm việc hướng hợp tác và tự động hóa**.  

* Những yếu tố cốt lõi của **DevOps culture** được nhấn mạnh:  
  * **Collaboration:** Dev–Ops vận hành như một nhóm thống nhất, cùng chịu trách nhiệm với sản phẩm.  
  * **Automation-first:** ưu tiên tự động hóa mọi bước build, test, deploy.  
  * **Measurement & Feedback:** ra quyết định dựa trên số liệu quan sát được.  

* Các nhóm chỉ số đánh giá DevOps theo chuẩn **DORA metrics**:  
  * **Deployment Frequency** – mức độ triển khai.  
  * **Lead Time for Changes** – thời gian thay đổi đi vào production.  
  * **MTTR** – thời gian khôi phục sau sự cố.  
  * **Change Failure Rate** – tỷ lệ lỗi khi triển khai.  

* Vai trò của **Platform Engineer** được mô tả như người xây dựng nền tảng triển khai chung, giúp các team có môi trường phát triển – kiểm thử – vận hành đồng nhất và hiệu quả.

---

**2.1.2. 9:00 – 10:30 | AWS DevOps Services – CI/CD Pipeline (Kha – CI/CD Workflow)**

* Diễn giả **Kha** trình bày về cách xây dựng pipeline CI/CD trên AWS.  
* Pipeline cơ bản được mô tả theo 4 thành phần chính:

1. **Source Control – AWS CodeCommit & Git strategies**  
   * CodeCommit là dịch vụ Git managed của AWS, tích hợp IAM và phù hợp môi trường nội bộ.  
   * Hai chiến lược Git được phân tích:  
     * **GitFlow** – phù hợp mô hình release lớn, nhiều nhánh.  
     * **Trunk-based Development** – tối ưu cho CI/CD liên tục, commit nhỏ, triển khai nhanh.

2. **Build & Test – AWS CodeBuild**  
   * CodeBuild thực hiện build và chạy test; workflow được định nghĩa trong `buildspec.yml`.  
   * Output là **artifact** dùng cho giai đoạn deploy.

3. **Deployment – AWS CodeDeploy**  
   * Ba chiến lược triển khai quan trọng:  
     * **Blue/Green** – an toàn nhất.  
     * **Canary** – chuyển giao traffic theo từng phần nhỏ.  
     * **Rolling update** – cập nhật dần theo nhóm instance.  

4. **Orchestration – AWS CodePipeline**  
   * Chịu trách nhiệm điều phối toàn bộ pipeline từ source → build → deploy.  
   * Hỗ trợ tích hợp thêm approval steps, test stages, manual gates.  

* Tinh thần DevOps được nhấn mạnh: mọi thao tác từ commit đến production **phải tự động hóa, có thể theo dõi, có thể kiểm chứng**.

---

**2.1.3. 10:45 – 12:00 | Infrastructure as Code (IaC) – Thịnh Nguyễn & Hoàng Anh)**

* Hai diễn giả bắt đầu bằng câu hỏi:  
  > “Vì sao ClickOps không phù hợp khi hệ thống mở rộng?”

* Các lý do chính:  
  * **Automation:** không tự động hóa được.  
  * **Scalability:** khó mở rộng khi số lượng tài nguyên tăng.  
  * **Reproducibility:** khó đảm bảo môi trường đồng nhất giữa nhiều stages.  
  * **Collaboration:** không có nguồn kiểm soát chung (source of truth).  

* **AWS CloudFormation** – IaC native của AWS:  
  * Các khái niệm: **template**, **stack**, **stack update**, **drift detection**.  
  * Ưu điểm lớn: version control, rollback tự động, triển khai nhiều môi trường nhất quán.

* **AWS CDK (Cloud Development Kit)**:  
  * Định nghĩa hạ tầng bằng ngôn ngữ lập trình (TS, Python, Java…).  
  * Trừu tượng hóa thành **constructs** dễ tái sử dụng.  
  * CDK sinh ra CloudFormation giúp kết hợp linh hoạt “code + hạ tầng”.  

* Kết luận lựa chọn IaC:  
  * CloudFormation → khi cần mô hình chuẩn, kiểm soát thấp tầng.  
  * CDK → khi dự án lớn, cần tái sử dụng và trừu tượng hóa.

---

#### 2.2. Phiên chiều – Container Services & Monitoring/Observability

---

**2.2.1. 13:00 – 14:30 | Container Services on AWS (Trần Vĩ)**

* Mở đầu với khái niệm container và sự khác biệt giữa **container** và **virtual machine**.  
* Giới thiệu chu trình Docker: Dockerfile → build image → push registry → run container.

* **Amazon ECR:**  
  * Registry container của AWS; hỗ trợ scanning, immutable tags, lifecycle policies.  

* **Amazon ECS:**  
  * Service orchestrator của AWS – đơn giản, native AWS.  
  * Hai chế độ chạy: **EC2 mode** và **Fargate mode** (serverless).  
  * Thành phần: cluster, task, task definition, service.

* **Amazon EKS:**  
  * Managed Kubernetes – dùng khi cần tính linh hoạt, portability.  

* **App Runner:**  
  * Triển khai service từ source/image cực nhanh; không cần quản lý cơ sở hạ tầng.

---

**2.2.2. 14:45 – 16:00 | Monitoring & Observability (Anh Nghiêm, Anh Long, Anh Quý)**

* **Monitoring vs Observability** – phân biệt theo góc nhìn hệ thống vận hành.  
* Dịch vụ chính: **CloudWatch**, **X-Ray**, **Amazon Managed Grafana**, **Prometheus**.

* **CloudWatch:**  
  * Thu thập metrics & logs, thiết lập alarms, tạo dashboards.  

* **AWS X-Ray:**  
  * Phân tích trace end-to-end, hỗ trợ debug microservices, tìm bottlenecks.  

* **Observability best practices:**  
  * Chuẩn hóa log–metric–trace, thiết lập cảnh báo hợp lý, tránh “alert fatigue”.  

---

**2.2.3. 16:00 – 17:00 | DevOps Best Practices, Career & Q&A**

* Tổng kết toàn bộ nội dung trong ngày: mindset → IaC → CI/CD → Containers → Observability.  
* Nhấn mạnh các nguyên tắc DevOps: test tự động, deploy an toàn, rollback nhanh, postmortem minh bạch.  
* Trao đổi về lộ trình nghề nghiệp và chứng chỉ AWS cho DevOps/Platform Engineer.

---

### III. Kiến thức và bài học rút ra

1. **DevOps là một tư duy thống nhất chứ không chỉ là bộ công cụ.**  
2. **CI/CD pipeline chuẩn giúp quy trình từ code đến production trở nên tin cậy và nhất quán.**  
3. **IaC là nền tảng bắt buộc để mở rộng hệ thống và tránh ClickOps.**  
4. **Containers trên AWS có nhiều lớp lựa chọn phù hợp từng mức phức tạp.**  
5. **Observability là điều kiện tiên quyết để hệ thống hoạt động ổn định lâu dài.**

---

### IV. Định hướng áp dụng vào học tập và dự án cá nhân

1. Chuẩn hóa quy trình DevOps và triển khai CI/CD mẫu.  
2. Chuyển các thao tác thủ công sang IaC bằng CloudFormation/CDK.  
3. Đóng gói ứng dụng vào Docker và thử nghiệm triển khai ECS/App Runner.  
4. Thiết lập monitoring tối thiểu với CloudWatch + X-Ray.  
5. Xác định lộ trình học chứng chỉ DevOps/SRE trên AWS.

---

### V. Một số hình ảnh trong sự kiện

![Why does DevOps Role exist?](/images/4-Event/4.5-AWS/1.jpeg)  
![DevOps culture elements](/images/4-Event/4.5-AWS/2.jpeg)  
![Next-generation DevOps](/images/4-Event/4.5-AWS/3.jpeg)  
![4](/images/4-Event/4.5-AWS/4.jpeg)  
![Why ClickOps isn't ideal](/images/4-Event/4.5-AWS/5.jpeg)
