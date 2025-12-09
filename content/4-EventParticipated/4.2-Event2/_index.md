---
title: "Event 2"
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

### AI/ML/GenAI on AWS

---

### I. General Event Information

* **Event Name:** AI/ML/GenAI on AWS  
* **Time:** 8:30 AM – 12:00 PM, November 15, 2025  
* **Location:** AWS Vietnam Office  
* **Objectives:**  
  * Provide foundational insights into AI/ML and Generative AI on AWS.  
  * Clarify the characteristics of *foundation models* and typical use cases.  
  * Introduce the AWS AI/ML service ecosystem—from ready-made services to customizable model-building platforms.  
  * Demonstrate how to build GenAI applications using Amazon Bedrock, RAG, and AgentCore.  

---

### II. Agenda and Session Details

### 1. Opening Session – Introduction to GenAI and Foundation Models (8:30 – 9:00)

Speaker **Lam Tuan Kiet** presented an overview of **Generative AI** and the role of foundation models:

* **What is GenAI?**  
  * Unlike traditional ML models centered on classification or prediction, GenAI can *generate new content*: text, images, audio, code, etc.  
  * Foundation models are trained on massive, multi-domain datasets and can later be *fine-tuned* or *steered* for specific applications.

* **Foundation Models & Amazon Bedrock:**  
  * Bedrock is introduced as a **centralized access platform for multiple foundation models** (Claude, Llama, Titan…).  
  * AWS provides a unified API that enables experimentation and evaluation across models—allowing teams to choose the right one for tasks like chatbots, summarization, classification, or RAG.

* **Prompt Engineering:**  
  * Described as the most critical skill when working with GenAI—designing, testing, and refining prompts to guide model behavior.  
  * Three primary techniques:  
    * **Zero-shot:** instruct the model without examples.  
    * **Few-shot:** provide sample inputs/outputs so the model imitates the pattern.  
    * **Chain-of-Thought:** guide the model to express step-by-step reasoning for more logical outcomes.

* **RAG (Retrieval-Augmented Generation):**  
  * An architecture that combines generative abilities with **retrieval from enterprise knowledge bases**.  
  * Key advantages: reduced hallucination, simple knowledge updates without retraining the model.

---

### 2. “AWS AI/ML Services Overview” & Embeddings/RAG in Action (9:00 – 10:30)

This section highlights how AWS structures its AI/ML services and how they are applied to GenAI/RAG workloads.

#### 2.1. Embeddings and Titan Embeddings

* Embeddings are described as **vector representations of text or images**, enabling similarity search, clustering, and semantic retrieval.  
* They form the backbone of RAG, semantic search, and recommendation systems.  
* **Titan Embeddings** were introduced as AWS’s optimized model for:  
  * Semantic search  
  * RAG  
  * Deep integration with Amazon Bedrock  

* The demo illustrated a full RAG pipeline:  
  * Data preprocessing → chunking → embedding generation → vector storage → querying → LLM response generation with contextual grounding.

#### 2.2. Managed AI Services (Ready-made AI APIs)

Speaker **Hoang Anh** introduced AWS’s fully managed AI services:

* **Amazon Rekognition** – Image/Video Recognition  
  * Use cases: object detection, facial recognition, text extraction  
  * Pricing: *0.0013 USD/image*  

* **Amazon Translate** – Neural Machine Translation  
  * Pricing: *15 USD per 1M characters*  

* **Amazon Textract** – OCR and Structured Document Extraction  
  * Preserves tables, forms, key fields  
  * Pricing: *0.05 USD/page*  

* **Amazon Transcribe** – Speech-to-Text  
  * Pricing: *0.024 USD/minute*  

* **Amazon Polly** – Text-to-Speech  
  * Pricing: *4 USD per 1M characters*  

* **Amazon Comprehend** – NLP (sentiment, key phrase, entity recognition…)  
  * Pricing: *0.0001 USD per 100 characters* or *3 USD/hour*  

* **Amazon Kendra** – Semantic Search / RAG Support  
  * Pricing: *30 USD/index/month + 0.35 USD/hour*  

* **Amazon Personalize** – Recommendation Service  
  * Pricing includes training, data processing, and recommendation volume  

---

### 3. “Generative AI with Amazon Bedrock” – AgentCore & Pipecat (10:45 – 12:00)

This session dives into **real-world GenAI architecture** including voice agents and agentic systems.

#### 3.1. Pipecat – Framework for Voice/Multimodal Agents

* **Pipecat** is presented as a framework optimized for low-latency voice and multimodal assistants:  
  * It unifies STT, LLM reasoning, TTS, and third-party tools into a single coordinated pipeline.  
  * Designed for real-time interaction—ideal for callbots and voice agents.

#### 3.2. Amazon Bedrock AgentCore and the Agentic AI Ecosystem

Speaker **Hieu Nghi** explained AWS’s approach to multi-step AI agents:

* **Agentic Systems Overview:**  
  * LLMs respond; agents plan, call tools, retrieve data, and execute multi-step workflows.  

* **AgentCore capabilities:**  
  * Workflow orchestration  
  * Tool invocation (Lambda, internal APIs…)  
  * RAG integration with Bedrock Knowledge Bases  
  * Guardrails for content and access control  
  * Observability and monitoring for production workloads  

* Supported agent frameworks include:  
  * crew.ai, ADK, LlamaIndex, LangChain, LangGraph, Strands Agents SDK, etc.

---

### III. Key Insights and Learnings

1. **GenAI is only one component of a larger system**  
   * You still need RAG, data pipelines, search engines, and monitoring.

2. **Choosing between AWS managed AI and custom GenAI with Bedrock**  
   * Services like Rekognition/Textract/Comprehend suit standardized use cases.  
   * For domain-specific data, **Bedrock + Embeddings + RAG** provides flexibility.

3. **Cost considerations must begin at the design phase**  
   * Pricing examples highlight the need to estimate usage volume early.

4. **Agentic thinking is the next evolution of GenAI**  
   * Beyond Q&A—agents automate workflows, execute tasks, analyze data, and make operational decisions.

---

### IV. Application Plans

1. **Build a RAG pipeline on AWS**  
   * Textract → Titan Embeddings → Vector Store → Kendra/Custom Search → Bedrock (Claude/Llama).  

2. **Experiment with a small Bedrock AgentCore agent**  
   * Phase 1: Retrieve + summarize documents.  
   * Phase 2: Call Lambda to automate actions.

3. **Improve prompt engineering skills**  
   * Practice zero-shot, few-shot, CoT prompts for AI/ML, DevOps, and Security use cases.  
   * Build a reusable personal prompt library.

---

### V. Event Photos

![Foundation Model](/images/4-Event/4.4-AWS/1.jpeg)  
![What are Embedding?](/images/4-Event/4.4-AWS/2.jpeg)  
![Amazon Titan Embedding](/images/4-Event/4.4-AWS/3.jpeg)  
![RAG in action](/images/4-Event/4.4-AWS/4.jpeg)  
![Data ingestion workflow](/images/4-Event/4.4-AWS/5.jpeg)  
![AWS AI Service](/images/4-Event/4.4-AWS/6.jpeg)  
![Lookout Family](/images/4-Event/4.4-AWS/7.jpeg)  
![Pipecat](/images/4-Event/4.4-AWS/8.jpeg)
