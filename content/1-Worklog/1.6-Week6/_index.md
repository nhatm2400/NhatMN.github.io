---
title: "Week 6 Worklog"
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Goals:

* Resource management and classification: Master tagging strategies (Tagging Strategy) to manage resources efficiently and organize Resource Groups.
* Advanced security: Understand and practice attribute-based access control (ABAC) using IAM Policies combined with Tags and Region restrictions.
* Infrastructure automation (IaC): Gain proficiency with AWS CloudFormation to deploy, manage, and replicate infrastructure through code (Templates, Stacks, StackSets).
* Project progress: Finalize the Proposal and begin designing the Backend architecture.

### Tasks to be completed this week:
| Day | Task                                                                                                                                                                                   | Start Date | Completion Date | References |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------------- | ---------- |
| 2   | - Continue refining the proposal | 13/10/2025 | 13/10/2025 | |
| 3 | - Learn the mechanism of Tag and Resource Groups in AWS. <br> - Study theory: Tag concepts, purpose of resource classification, how Resource Groups work. <br> **Practice:** <br>&emsp; + Create EC2 instance with Tag and manage Tags on Console. <br>&emsp; + Add/Remove Tags and filter resources by Tag. <br>&emsp; + Assign Tags using AWS CLI and search resources via filters. <br>&emsp; + Create Tag-based Resource Group and view grouped resources. | 14/10/2025 | 14/10/2025 | https://000027.awsstudygroup.com/vi/ |
| 4 | - Learn access control for EC2 using IAM and Resource Tags. <br> - Study theory: IAM Least Privilege, IAM Conditions, Region and Tag restrictions. <br> **Practice:** <br>&emsp; + Create 5 IAM Policies to control EC2 permissions by Tag and Region. <br>&emsp; + Create IAM Role `ec2-admin-team-alpha` and attach policies. <br>&emsp; + Switch Role and test: create EC2 with correct/incorrect Tag, access allowed/denied Regions, modify Tags, and manage Instances. <br>&emsp; + Delete Role and Policies after completion. | 15/10/2025 | 15/10/2025 | https://000028.awsstudygroup.com/vi/ |
| 5 | - Weekly team meeting: assign tasks. <br> - Learn the overview of AWS CloudFormation and Infrastructure as Code. <br> - Study theory: template structure, intrinsic functions, pseudo parameters, Cloud9, Custom Resources, Mappings, StackSets, and Drift Detection. <br> **Practice:** <br>&emsp; + Create IAM User/Role and set up the Cloud9 environment. <br>&emsp; + Write and lint a basic EC2 template, deploy the stack and check Outputs. <br>&emsp; + Create a Custom Resource using Lambda to generate SSH Key. <br>&emsp; + Create StackSets to deploy EC2 across multiple regions and perform Drift Detection. | 16/10/2025 | 16/10/2025 | https://000037.awsstudygroup.com/vi/ |
| 6   | - Weekly team meeting. <br> - Begin researching Backend architecture for the Project | 17/10/2025 | 17/10/2025 |

### Week 6 Achievements:

* Project: Developed the Proposal and researched foundational Backend architecture.
* Management: Gained solid understanding of large-scale resource classification through Tagging Strategy and Resource Groups.
* Security: Successfully implemented advanced access control using IAM Policies with conditions based on Tags and Region.
* CloudFormation: Achieved proficiency in the IaC workflow—writing Templates, creating Custom Resources with Lambda, multi-region deployment (StackSets), and performing Drift Detection.
