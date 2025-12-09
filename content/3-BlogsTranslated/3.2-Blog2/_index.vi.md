---
title: "Blog 2"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---



# **Các phiên bản Amazon EC2 M8i và M8i-flex đa năng mới hiện đã có sẵn**

bởi [Channy Yun (윤석찬)](https://aws.amazon.com/blogs/aws/author/channy-yun/) | 28 THÁNG 8 NĂM 2025 | trong [Amazon EC2](https://aws.amazon.com/blogs/aws/category/compute/amazon-ec2/) , [Tính toán](https://aws.amazon.com/blogs/aws/category/compute/) , [Ra mắt](https://aws.amazon.com/blogs/aws/category/news/launch/) , [Tin tức](https://aws.amazon.com/blogs/aws/category/news/)

[da4b9237bacccdf19c0760cab7aec4a8359010b0amazon\_polly\_98931.mp3](https://drive.google.com/file/d/18115-HfXp_o5AN4xQomBf775b8g_E7Q0/view?usp=sharing)

Hôm nay, chúng tôi xin công bố sự ra mắt rộng rãi của các phiên bản [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/pm/ec2/?trk=7c8639c6-87c6-47d6-9bd0-a5812eecb848&sc_channel=el) đa năng [M8i và M8i-flex,](https://aws.amazon.com/ec2/instance-types/m8i/) được trang bị bộ vi xử lý Intel Xeon 6 tùy chỉnh, chỉ có trên AWS với tần số turbo 3,9 GHz toàn nhân ổn định. Các phiên bản này mang lại hiệu suất cao nhất và băng thông bộ nhớ nhanh nhất trong số các bộ vi xử lý Intel tương đương trên nền tảng đám mây. Chúng cũng mang lại hiệu suất giá tốt hơn tới 15%, hiệu suất cao hơn tới 20% và băng thông bộ nhớ cao hơn 2,5 lần so với [các phiên bản M7i và M7i-flex](https://aws.amazon.com/blogs/aws/new-seventh-generation-general-purpose-amazon-ec2-instances-m7i-flex-and-m7i/) thế hệ trước .

Các phiên bản M8i và M8i-flex lý tưởng để chạy các khối lượng công việc đa năng như máy chủ ứng dụng web, máy tính để bàn ảo, xử lý hàng loạt, dịch vụ vi mô, cơ sở dữ liệu và ứng dụng doanh nghiệp. Về hiệu suất, các phiên bản này nhanh hơn tới 60% đối với ứng dụng web NGINX, nhanh hơn tới 30% đối với khối lượng công việc cơ sở dữ liệu PostgreSQL và nhanh hơn tới 40% đối với các mô hình đề xuất học sâu AI so với các phiên bản M7i và M7i-flex.

Tương tự như [các phiên bản R8i và R8i-flex](https://aws.amazon.com/blogs/aws/best-performance-and-fastest-memory-with-the-new-amazon-ec2-r8i-and-r8i-flex-instances/) , các phiên bản này sử dụng [AWS Nitro Cards](https://aws.amazon.com/ec2/nitro/) thế hệ thứ sáu mới , cung cấp băng thông mạng và [Amazon Elastic Block Storage (Amazon EBS)](https://aws.amazon.com/ebs/) gấp hai lần so với các phiên bản thế hệ trước. Điều này cải thiện đáng kể thông lượng mạng cho các khối lượng công việc xử lý các gói tin nhỏ như máy chủ web, ứng dụng và trò chơi. Chúng cũng hỗ trợ cấu hình băng thông với khả năng điều chỉnh phân bổ 25% giữa băng thông mạng và Amazon EBS, cho phép cải thiện hiệu suất cơ sở dữ liệu, xử lý truy vấn và tốc độ ghi nhật ký.

#### Phiên bản M8i  
Cung cấp tối đa 384 vCPU và 1,5 TB bộ nhớ, bao gồm cả phiên bản bare metal cung cấp quyền truy cập chuyên dụng vào phần cứng vật lý cơ bản. Các phiên bản được chứng nhận SAP này giúp bạn vận hành các máy chủ ứng dụng và cơ sở dữ liệu lớn, máy chủ trò chơi, suy luận dựa trên CPU và phát trực tuyến video cần kích thước phiên bản lớn nhất hoặc CPU cao liên tục.

Sau đây là thông số kỹ thuật của phiên bản M8i:

| Kích thước phiên bản | vCPU | Bộ nhớ (GiB) | Băng thông mạng (Gbps) | Băng thông EBS (Gbps) |
| :---: | :---: | :---: | :---: | :---: |
| m8i.lớn | 2 | 8 | Lên đến 12,5 | Lên đến 10 |
| m8i.xlarge | 4 | 16 | Lên đến 12,5 | Lên đến 10 |
| m8i.2xlớn | 8 | 32 | Lên đến 15 | Lên đến 10 |
| m8i.4xlớn | 16 | 64 | Lên đến 15 | Lên đến 10 |
| m8i.8xlớn | 32 | 128 | 15 | 10 |
| m8i.12xlớn | 48 | 192 | 22,5 | 15 |
| m8i.16xlớn | 64 | 256 | 30 | 20 |
| m8i.24xlớn | 96 | 384 | 40 | 30 |
| m8i.32xlớn | 128 | 512 | 50 | 40 |
| m8i.48xlớn | 192 | 768 | 75 | 60 |
| m8i.96xlớn | 384 | 1536 | 100 | 80 |
| m8i.metal-48xl | 192 | 768 | 75 | 60 |
| m8i.metal-96xl | 384 | 1536 | 100 | 80 |

#### Phiên bản M8i-flex  
là phiên bản giá rẻ hơn của phiên bản M8i, với hiệu năng cao hơn 5% và giá thấp hơn 5%. Chúng được thiết kế cho các khối lượng công việc được hưởng lợi từ hiệu năng thế hệ mới nhất nhưng không tận dụng hết toàn bộ tài nguyên tính toán. Các phiên bản này có thể đạt hiệu năng CPU tối đa 95% thời gian.

Sau đây là thông số kỹ thuật của phiên bản M8i-flex:

| Kích thước phiên bản | vCPU | Bộ nhớ (GiB) | Băng thông mạng (Gbps) | Băng thông EBS (Gbps) |
| :---: | :---: | :---: | :---: | :---: |
| m8i-flex.lớn | 2 | 8 | Lên đến 12,5 | Lên đến 10 |
| m8i-flex.xlarge | 4 | 16 | Lên đến 12,5 | Lên đến 10 |
| m8i-flex.2xlarge | 8 | 32 | Lên đến 15 | Lên đến 10 |
| m8i-flex.4xlarge | 16 | 64 | Lên đến 15 | Lên đến 10 |
| m8i-flex.8xlarge | 32 | 128 | Lên đến 15 | Lên đến 10 |
| m8i-flex.12xlarge | 48 | 192 | Lên đến 22,5 | Lên đến 15 |
| m8i-flex.16xlarge | 64 | 256 | Lên đến 30 | Lên đến 20 |

Nếu hiện tại bạn đang sử dụng các thế hệ phiên bản chung trước đó, bạn có thể áp dụng phiên bản M8i-flex mà không cần phải thay đổi ứng dụng hoặc khối lượng công việc của mình.

Phiên bản Amazon EC2 M8i và M8i-flex hiện đã [có sẵn tại các khu vực AWS](https://docs.aws.amazon.com/glossary/latest/reference/glos-chap.html#region) miền Đông Hoa Kỳ (Bắc Virginia), miền Đông Hoa Kỳ (Ohio), miền Tây Hoa Kỳ (Oregon) và châu Âu (Tây Ban Nha) . Phiên bản M8i và M8i-flex có thể được mua dưới dạng [phiên bản Theo yêu cầu](https://aws.amazon.com/ec2/pricing/on-demand/?trk=cf96f8ec-de40-4ee0-8b64-3f7cf7660da2&sc_channel=el) , [Gói tiết kiệm](https://aws.amazon.com/savingsplans/?trk=cc9e0036-98c5-4fa8-8df0-5281f75284ca&sc_channel=el) và [Phiên bản Spot](https://aws.amazon.com/ec2/spot/pricing/?trk=307341f6-3463-47d5-ba81-0957847a9b73&sc_channel=el) . Phiên bản M8i cũng có sẵn trong [Phiên bản Chuyên dụng](https://aws.amazon.com/ec2/pricing/dedicated-instances/) và [Máy chủ Chuyên dụng](https://aws.amazon.com/ec2/dedicated-hosts/pricing/) . Để tìm hiểu thêm, hãy truy cập [trang Giá Amazon EC2](https://aws.amazon.com/ec2/pricing) .

Hãy dùng thử phiên bản M8i và M8i-flex trong [bảng điều khiển Amazon EC2](https://console.aws.amazon.com/ec2/?trk=769a1a2b-8c19-4976-9c45-b6b1226c7d20&sc_channel=el) . Để tìm hiểu thêm, hãy truy cập [trang phiên bản M8i của Amazon EC2](https://aws.amazon.com/ec2/instance-types/m8i/) và gửi phản hồi đến [AWS re:Post cho EC2](https://repost.aws/tags/TAO-wqN9fYRoyrpdULLa5y7g/amazon-ec-2) hoặc thông qua các liên hệ Hỗ trợ AWS thường xuyên của bạn.

— [Channy](https://linkedin.com/in/channy/)

---

## Tác giả

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/channy.jpg"
         alt="Channy Yun"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Channy Yun (윤석찬)</h3>
    <p style="margin:0;">
      Channy là Blogger chính của AWS News Blog và là Người ủng hộ Nhà phát triển Chính
      cho AWS Cloud. Là một người đam mê web mở và là một blogger thực thụ, anh ấy yêu
      thích việc học tập và chia sẻ công nghệ dựa trên cộng đồng.
    </p>
  </div>

</div>
 