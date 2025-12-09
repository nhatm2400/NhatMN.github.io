---
title: "Week 5 Worklog"
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Goals:

* Master the **Migration** process: Understand and practice transferring virtual machines between **On-premise** environments and **AWS Cloud**.
* Optimize operations: Implement automation to reduce infrastructure costs and manage system resources efficiently.
* System monitoring: Gain proficiency with Grafana for data visualization combined with **AWS CloudWatch**.
* Project development: Finalize the proposal and initial architecture for the team project.

### Tasks to be completed this week:
| Day | Task                                                                                                                                                                                   | Start Date | Completion Date | References |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------------- | ---------- |
| 2   | - Translate 3 blog posts <br> - Review the Proposal and draft the architectural outline                                                            | 06/10/2025 | 06/10/2025 | |
| 3   | - Weekly team meeting: assign features for implementation. <br> - Learn the overview of AWS VM Import/Export. <br> - Study theoretical concepts: supported formats, IAM requirements, S3, ACL. <br> **Practice:** <br>&emsp; + Import a virtual machine from on-premise to AWS <br>&emsp; + Create AMI and launch EC2 from the imported VM <br>&emsp; + Export AMI/EC2 instance from AWS back to VM format | 07/10/2025 | 07/10/2025 | <https://000014.awsstudygroup.com/vi/> |
| 4 | - Learn cost-optimization solutions for EC2 using AWS Lambda. <br> - Study architecture: Lambda, EventBridge, IAM Role, EC2 Tag. <br> **Practice:** <br>&emsp; + Configure Lambda to automatically Start/Stop EC2. <br>&emsp; + Create IAM Role for Lambda. <br>&emsp; + Configure EventBridge Rule. <br>&emsp; + Integrate Slack Webhook for notifications. | 08/10/2025 | 08/10/2025 | https://000022.awsstudygroup.com/vi/ |
| 5 |- Learn the overview of Grafana on AWS and system monitoring. <br> - Study theory: Grafana architecture, CloudWatch, IAM Role/User, Security Group. <br> **Practice:** <br>&emsp; + Deploy VPC, Subnet, and Security Group for Grafana. <br>&emsp; + Create EC2 instance and attach IAM Role for CloudWatch access. <br>&emsp; + Install Grafana on EC2 and configure the service. <br>&emsp; + Add CloudWatch Data Source and create a CPU monitoring Dashboard. | 09/10/2025 | 09/10/2025 | https://000029.awsstudygroup.com/vi/ |
| 6 | - Weekly team meeting. <br> - Learn the overview of Tag and Resource Groups in AWS. <br> - Study theory: Tag definitions, metadata usage, Resource Groups mechanism. <br> **Practice:** <br>&emsp; + Create EC2 instance with Tag and manage Tags on Console. <br>&emsp; + Filter and search resources via Tag. <br>&emsp; + Add/Remove Tags using AWS CLI. <br>&emsp; + Create a Tag-based Resource Group and manage grouped resources. | 10/10/2025 | 10/10/2025 | https://000027.awsstudygroup.com/vi/ |

### Week 5 Achievements:

* **Project:** Reviewed and built the Proposal, collaborated with the team to design the initial architecture, and completed translation of three technical blog posts as planned.
* **Migration:** Mastered and successfully practiced Import/Export of virtual machines (VMDK/OVA formats) between On-premise and AWS environments using S3 and AMI.
* **Automation:** Implemented a cost-optimization solution using AWS Lambda and EventBridge to automatically Start/Stop EC2 on schedule, with Slack Webhook notifications.
* **Monitoring:** Successfully built a monitoring system with Grafana on EC2, configured CloudWatch Data Source, and visualized performance metrics (CPU/Network) on Dashboards.
* **Management:** Gained proficiency in large-scale resource management through Tagging and Resource Groups, including tagging, searching, and managing metadata via both Console and AWS CLI.
