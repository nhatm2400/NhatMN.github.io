---
title: "Event 4"
weight: 1
chapter: false
pre: " <b> 4.4. </b> "
---

### AWS Well-Architected Security Pillar

---


### I. General Information About the Event

* **Event Name:** AWS Well-Architected Security Pillar  
* **Time:** 08:30 – 12:00, November 29, 2025 (morning only)  
* **Location:** AWS Vietnam Office  
* **Main Objectives:**  
  * Clarify the role of the **Security Pillar** within the **AWS Well-Architected Framework** and the **Shared Responsibility Model**.  
  * Summarize the five core security pillars: **Identity & Access Management, Detection, Infrastructure Protection, Data Protection, Incident Response**.  
  * Analyze **best practices**, common mistakes, and real-world risks frequently encountered by organizations in Vietnam when using cloud services.  
  * Demonstrate hands-on examples including IAM policy simulation, detection-as-code, firewall configuration, and IR playbooks.  

---

### II. Detailed Timeline


#### 2.1. Opening & Security Foundation (08:30 – 08:50)

The opening session established the foundation for **security thinking on AWS**:

* **Importance of the Security Pillar within the Well-Architected Framework**

  * Security is not an “afterthought”; it must be built into the architecture from the design phase.
  * Systems lacking proper security often face issues such as:  
    * **Data leakage** or unauthorized access.  
    * **Service outages** caused by misconfigurations or cyberattacks.  
    * **Data loss or corruption** due to missing backup or encryption layers.  
    * **Traffic overload** without adequate protection mechanisms.

* **Core Security Principles:**

  * **Least Privilege:** only grant the minimal required permissions.  
  * **Zero Trust:** assume no component is trustworthy by default.  
  * **Defense in Depth:** protect across multiple layers from identity to network to data.

* **Shared Responsibility Model**

  * AWS is responsible for **security OF the cloud**.  
  * Customers are responsible for **security IN the cloud**, including IAM, resource configuration, data protection, logging, and incident response.

* **Common Risks in the Vietnamese Market**

  * Long-lived access keys that become leaked or misused.  
  * Public S3 buckets without operator awareness.  
  * Servers or endpoints exposed to the public Internet unnecessarily.  
  * Insufficient or incomplete logging, making incident investigation difficult.

---

#### 2.2. Pillar 1 – Identity & Access Management (08:50 – 09:30)

This section focused on designing modern IAM systems suitable for **multi-account architectures**:

* **IAM Users, Roles, Policies – eliminating long-lived credentials**

  * Avoid using IAM users with long-term access keys for workloads.  
  * Prefer **IAM Roles** with temporary tokens for improved security.  
  * Policies must follow **least privilege**, avoiding `Action:*` or `Resource:*`.

* **IAM Identity Center + AWS Organizations**

  * IAM Identity Center (SSO) is the core of modern IAM architectures.  
  * Combined with AWS Organizations, it enables centralized governance with clearly separated accounts (prod, dev, security, logging…).

* **SCP – Service Control Policies**

  * SCPs act as the “upper boundary” for permissions within an OU/account.  
  * IAM policies grant permissions; SCPs restrict the maximum possible scope.

* **Permission Boundaries**

  * Allow teams to create/manage their own IAM users/roles within defined organizational limits.

* **MFA, Credential Rotation, Access Analyzer**

  * Enforce MFA for the root user and privileged identities.  
  * Secrets Manager supports automatic credential rotation.  
  * IAM Access Analyzer helps detect unintended public or cross-account access.

* **Mini Demo: IAM policy validation & access simulation**

  * Demonstrated using validation tools and simulators to verify behavior before deploying policies in production.

---

#### 2.3. Pillar 2 – Detection & Continuous Monitoring (09:30 – 09:55)

This segment emphasized **observation – detection – alerting**:

* **AWS CloudTrail (Duc Anh)**  
  * Logs every API call in the system:  
    * Management events  
    * Data events (S3 object access, Lambda invoke)  
    * Network activity  
  * Supports **multi-account logging** when enabled at the Organization level.  
  * Integrated with EventBridge for **detection-as-code** automation workflows.

* **Amazon GuardDuty (Tuan Thinh)**  
  * Detects anomalies using ML and baselines using:  
    * VPC Flow Logs  
    * CloudTrail  
    * DNS logs  
  * Advanced protection packages include EKS, RDS, and Lambda runtime monitoring.  
  * Can isolate compromised resources automatically via EventBridge.

* **AWS Security Hub (Thanh Dat)**  
  * Aggregates security findings across services.  
  * Normalizes results into **ASFF** and evaluates against CIS & AWS best practices.  
  * Supports detection-as-code across multi-account environments.

---

#### 2.4. Pillar 3 – Infrastructure Protection (10:10 – 10:40)

Focused on **network security** and **traffic control**:

* **Common network attack vectors**  
  * Inbound, outbound, and east–west traffic between workloads.

* **Security Groups**  
  * Stateful; return traffic is automatically allowed.  
  * Only support allow rules (no deny).  
  * Allow SG sharing and referencing across VPCs.

* **Network ACLs**  
  * Stateless, applied at subnet level.  
  * Support allow + deny, suitable for coarse-grained rules.

* **DNS & Perimeter Protection – Route 53**  
  * Private DNS, DNS filtering, rule management.  
  * Applicable to cloud-only and hybrid deployments.

* **AWS Network Firewall**  
  * Controls traffic across multi-VPC environments.  
  * Supports stateless + stateful rules.  
  * Works well with Transit Gateway.

* **Edge Protection: AWS WAF + AWS Shield**  
  * Provides DDoS protection and malicious request filtering.

---

#### 2.5. Pillar 4 – Data Protection (10:40 – 11:10)

Covered best practices for protecting data at rest and in transit:

* **AWS KMS**  
  * Explained master key vs data key encryption workflow.  
  * Key policies strictly control access—even admins cannot use a key unless granted.  
  * Difference between AWS-managed keys and CMKs with custom policies and rotation.

* **Data Classification & Guardrails**  
  * Amazon Macie automatically identifies sensitive data (PII) in S3.  
  * Guardrails can deny operations when objects are not encrypted.

* **Encryption in Transit**  
  * TLS/SSL for S3, DynamoDB, RDS.  
  * EBS/Nitro secure transport encryption.  
  * ACM for certificate management.

* **Secrets Manager**  
  * Secure storage for credentials, tokens, connection strings.  
  * Automated rotation via Lambda integration.

---

#### 2.6. Pillar 5 – Incident Response (11:10 – 11:40)

Focused on structured and automated IR workflows:

* **Modern context**  
  * Multi-account + hybrid architectures → manual operations are insufficient.  
  * Common incidents: credential leaks, S3 public exposure, malware, service outages…

* **Security Responsibilities are Shared**  
  * Baseline services recommended:  
    * AWS Organizations + SCP  
    * CloudTrail  
    * AWS Config  
    * GuardDuty  
    * Security Hub  

* **Prevention Guidelines**  
  * Remove long-lived access keys.  
  * Avoid exposing S3 unless strictly required.  
  * Minimize public Internet exposure for workloads.  
  * Apply all infrastructure changes via IaC.  
  * Add approval layers for high-risk changes.

* **AWS Incident Response Framework**  
  1. **Prepare**  
  2. **Detect & Analyze**  
  3. **Contain**  
  4. **Eradicate & Recover**  
  5. **Post-Incident Review**  

* **Playbook examples**  
  * Compromised IAM key  
  * Public S3 bucket  
  * Malware-infected EC2 instance  
  * Workflows include: isolation → snapshot → revoke → automation with Lambda/Step Functions.

---

#### 2.7. Wrap-Up & Q&A (11:40 – 12:00)

* Recap of the five security pillars.  
* Highlighted common mistakes by Vietnamese organizations:  
  * Poorly designed IAM.  
  * Missing or incomplete CloudTrail/GuardDuty/Security Hub setup.  
  * Accidental S3 public exposure.  
* Recommended learning path: aim for **AWS Security Specialty**.

---

### III. Key Takeaways

1. **Security must be a design principle, not an afterthought.**  
2. **Modern IAM requires multi-account structure + SSO + SCP + rotation + MFA.**  
3. **Detection-as-code is essential for complex cloud environments.**  
4. **Infrastructure Protection requires layered network design—not just firewalls.**  
5. **Data Protection and IR complete the full security posture.**

---

### IV. Action Plan for Learning & Personal Projects

1. Standardize IAM with multi-account design following AWS best practices.  
2. Enable CloudTrail, GuardDuty, and Security Hub as baseline detection layers.  
3. Redesign network architectures using segmentation to minimize public exposure.  
4. Apply KMS + Secrets Manager + Macie for sensitive data workflows.  
5. Strengthen Security Pillar knowledge to pursue AWS Security Specialty.  

---

### V. Event Photos

![1](/images/4-Event/4.6-AWS/1.jpeg)  
![2](/images/4-Event/4.6-AWS/2.jpeg)  
![3](/images/4-Event/4.6-AWS/3.jpeg)  
![4](/images/4-Event/4.6-AWS/4.jpeg)  
![5](/images/4-Event/4.6-AWS/5.jpeg)
