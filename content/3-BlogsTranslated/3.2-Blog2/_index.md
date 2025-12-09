---
title: "Blog 2"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# **New General-Purpose Amazon EC2 M8i and M8i-flex Instances Are Now Available**

by [Channy Yun (윤석찬)](https://aws.amazon.com/blogs/aws/author/channy-yun/) | AUGUST 28, 2025 | in [Amazon EC2](https://aws.amazon.com/blogs/aws/category/compute/amazon-ec2/), [Compute](https://aws.amazon.com/blogs/aws/category/compute/), [Launch](https://aws.amazon.com/blogs/aws/category/news/launch/), [News](https://aws.amazon.com/blogs/aws/category/news/)

[da4b9237bacccdf19c0760cab7aec4a8359010b0amazon_polly_98931.mp3](https://drive.google.com/file/d/18115-HfXp_o5AN4xQomBf775b8g_E7Q0/view?usp=sharing)

Today, we are excited to announce the general availability of the new general-purpose [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/pm/ec2/?trk=7c8639c6-87c6-47d6-9bd0-a5812eecb848&sc_channel=el) instances, [M8i and M8i-flex](https://aws.amazon.com/ec2/instance-types/m8i/), powered by custom-built Intel Xeon 6 processors available exclusively on AWS—with a consistent all-core turbo frequency of 3.9 GHz. These instances provide the highest performance and fastest memory bandwidth among comparable Intel processors on any cloud platform. They also deliver up to 15% better price performance, up to 20% higher compute performance, and 2.5× greater memory bandwidth than the previous-generation [M7i and M7i-flex](https://aws.amazon.com/blogs/aws/new-seventh-generation-general-purpose-amazon-ec2-instances-m7i-flex-and-m7i/) instances.

M8i and M8i-flex instances are ideal for general-purpose workloads such as web application servers, virtual desktops, batch processing, microservices, databases, and enterprise applications. In terms of performance, they are up to 60% faster for NGINX web applications, up to 30% faster for PostgreSQL database workloads, and up to 40% faster for deep learning recommendation models compared to M7i and M7i-flex.

Like the [R8i and R8i-flex](https://aws.amazon.com/blogs/aws/best-performance-and-fastest-memory-with-the-new-amazon-ec2-r8i-and-r8i-flex-instances/) instances, these new instances use the sixth-generation [AWS Nitro Cards](https://aws.amazon.com/ec2/nitro/), offering twice the network and [Amazon Elastic Block Store (Amazon EBS)](https://aws.amazon.com/ebs/) bandwidth of the previous generation. This significantly improves network throughput for workloads that process small packets such as web servers, applications, and gaming servers. They also support configurable bandwidth with a 25% reallocation capability between network and EBS bandwidth, enabling better database performance, improved query processing, and faster log write speeds.

### M8i Instances  
These instances offer up to 384 vCPUs and 1.5 TB of memory, including bare-metal options providing direct access to underlying physical hardware. SAP-certified, these instances allow you to run large application servers, databases, game servers, CPU-based inference, and video streaming workloads that require the largest instance sizes or consistently high CPU performance.

Below are the specifications for M8i instances:

| Instance Size | vCPU | Memory (GiB) | Network Bandwidth (Gbps) | EBS Bandwidth (Gbps) |
| :---: | :---: | :---: | :---: | :---: |
| m8i.large | 2 | 8 | Up to 12.5 | Up to 10 |
| m8i.xlarge | 4 | 16 | Up to 12.5 | Up to 10 |
| m8i.2xlarge | 8 | 32 | Up to 15 | Up to 10 |
| m8i.4xlarge | 16 | 64 | Up to 15 | Up to 10 |
| m8i.8xlarge | 32 | 128 | 15 | 10 |
| m8i.12xlarge | 48 | 192 | 22.5 | 15 |
| m8i.16xlarge | 64 | 256 | 30 | 20 |
| m8i.24xlarge | 96 | 384 | 40 | 30 |
| m8i.32xlarge | 128 | 512 | 50 | 40 |
| m8i.48xlarge | 192 | 768 | 75 | 60 |
| m8i.96xlarge | 384 | 1536 | 100 | 80 |
| m8i.metal-48xl | 192 | 768 | 75 | 60 |
| m8i.metal-96xl | 384 | 1536 | 100 | 80 |

### M8i-flex Instances  
These are lower-cost variants of the M8i instances, offering 5% higher performance and 5% lower prices. They are designed for workloads that benefit from next-generation performance but do not fully utilize the compute resources. These instances can achieve maximum CPU performance 95% of the time.

Below are the specifications for M8i-flex instances:

| Instance Size | vCPU | Memory (GiB) | Network Bandwidth (Gbps) | EBS Bandwidth (Gbps) |
| :---: | :---: | :---: | :---: | :---: |
| m8i-flex.large | 2 | 8 | Up to 12.5 | Up to 10 |
| m8i-flex.xlarge | 4 | 16 | Up to 12.5 | Up to 10 |
| m8i-flex.2xlarge | 8 | 32 | Up to 15 | Up to 10 |
| m8i-flex.4xlarge | 16 | 64 | Up to 15 | Up to 10 |
| m8i-flex.8xlarge | 32 | 128 | Up to 15 | Up to 10 |
| m8i-flex.12xlarge | 48 | 192 | Up to 22.5 | Up to 15 |
| m8i-flex.16xlarge | 64 | 256 | Up to 30 | Up to 20 |

If you currently use earlier generations of general-purpose instances, you can adopt M8i-flex without modifying your applications or workloads.

Amazon EC2 M8i and M8i-flex instances are now [available in the AWS Regions](https://docs.aws.amazon.com/glossary/latest/reference/glos-chap.html#region) US East (N. Virginia), US East (Ohio), US West (Oregon), and Europe (Spain). You can purchase M8i and M8i-flex as [On-Demand Instances](https://aws.amazon.com/ec2/pricing/on-demand/), [Savings Plans](https://aws.amazon.com/savingsplans/), or [Spot Instances](https://aws.amazon.com/ec2/spot/pricing/). M8i is also available as a [Dedicated Instance](https://aws.amazon.com/ec2/pricing/dedicated-instances/) and on [Dedicated Hosts](https://aws.amazon.com/ec2/dedicated-hosts/pricing/). For more information, visit the [Amazon EC2 Pricing page](https://aws.amazon.com/ec2/pricing).

Try the M8i and M8i-flex instances in the [Amazon EC2 Console](https://console.aws.amazon.com/ec2/). To learn more, visit the [Amazon EC2 M8i Instance page](https://aws.amazon.com/ec2/instance-types/m8i/) and send feedback through [AWS re:Post for EC2](https://repost.aws/tags/TAO-wqN9fYRoyrpdULLa5y7g/amazon-ec-2) or your usual AWS Support contacts.

— [Channy](https://linkedin.com/in/channy/)

---

## Author

<div style="display:flex; align-items:flex-start; gap:1.75rem; margin:2rem 0;">

  <div style="flex:0 0 220px;">
    <img src="/images/channy.jpg"
         alt="Channy Yun"
         style="max-width:100%; height:auto; display:block;">
  </div>

  <div>
    <h3 style="margin-top:0; margin-bottom:0.5rem;">Channy Yun (윤석찬)</h3>
    <p style="margin:0;">
      Channy is the Lead Blogger for the AWS News Blog and Principal Developer Advocate for AWS Cloud.  
      A passionate open-web enthusiast and long-time blogger, he loves learning and sharing community-driven technologies.
    </p>
  </div>

</div>
