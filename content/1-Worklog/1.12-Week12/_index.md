---
title: "Week 12 Worklog"
weight: 2
chapter: false
pre: " <b> 1.12 </b> "
---

### Week 12 Goals:

* **System Integration:** Fully connect the Backend with **AWS Lambda Functions** (AI services) and resolve compatibility issues.
* **Infrastructure Setup:** Configure essential security services (**Cognito, Secrets Manager**) and monitoring tools (**CloudWatch**).
* **Full-stack Deployment:** Integrate **Frontend – Backend** and deploy the complete application using **AWS Amplify**.
* **QA & Bug Fixing:** Ensure smooth end-to-end workflows and fix logic issues related to **Authentication**, **Database**, and **AI Editor**.

### Tasks to be completed this week:
| Day | Task                                                                                                                                                                 | Start Date | Completion Date | References |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------------- | ---------- |
| 2   | - Integrate Lambda ARNs into Backend code. <br> - Fix issues such as Backend–Lambda incompatibility. <br> - Learn Backend development.                               | 17/11/2025 | 17/11/2025 | <https://www.youtube.com/watch?v=KAV8vo7hGAo> |
| 3   | - Add complete configurations. <br> - Run and test Backend features using Postman (generate, upload contract, chatbot, rag, etc.). <br> - Fix remaining logic issues. | 18/11/2025 | 18/11/2025 |
| 4   | - Set up Cognito, Secrets Manager, CloudWatch, etc. <br> - Re-test Backend and validate all features. <br> - Fix remaining logic issues.                              | 19/11/2025 | 19/11/2025 |
| 5   | - Connect Backend with Frontend. <br> - Link workflows and deploy to Amplify. <br> - Fix remaining logic issues.                                                      | 20/11/2025 | 20/11/2025 |
| 6   | - Team meeting for final result reporting. <br> - Fix issues such as password change failures, contract template not saving, and AI not working in editor. <br> - Fix logic errors related to database and Cognito. | 21/11/2025 | 21/11/2025 |

### Week 12 Achievements:

* Backend & Serverless Integration:
  * Successfully integrated ARNs of Lambda Functions (RAG, Chatbot, Generator) into the Backend.
  * Fully resolved environment compatibility issues between Node.js Backend and AWS Lambda.
  * Fixed logic issues arising from integrating Large Language Models (LLM).

* Security & Monitoring:
  * Successfully configured Amazon Cognito for User Pool/Identity Pool.
  * Set up AWS Secrets Manager to securely manage environment variables and CloudWatch for system logging.

* Functional Testing:
  * Successfully validated all core features via Postman: contract upload, RAG search, AI chatbot, and contract generation.

* Deployment & Bug Fixing:
  * Successfully connected Frontend with Backend.
  * Deployed the full application to AWS Amplify.
  * Completed major business logic fixes: password reset (Cognito), contract template saving (Database), and AI execution in editor.
