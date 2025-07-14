# AI & LLM Quick Reference

## Q1. What is LLM?  
**LLM** stands for **Large Language Model**.  
An AI model trained on huge amounts of text data to understand and generate human-like language.  
➡️ *Example: ChatGPT answering coding questions or writing emails.*

---

## Q2. What is LangChain?  
**LangChain** is a framework to build applications with LLMs by connecting them to external data, memory, tools, and defining workflows (chains).  
➡️ *Example: Building a chatbot that can search documents before replying.*

---

## Q3. What is LangGraph?  
**LangGraph** is a framework built on LangChain for creating stateful, multi-step workflows structured as a graph of nodes and edges.  
➡️ *Example: Creating a chatbot that follows different paths based on user input.*

---

## Q4. What is RAG?  
**RAG** (Retrieval-Augmented Generation) lets LLMs access external info (documents, databases) by retrieving relevant content before generating an answer.  
➡️ *Example: Answering a question by first searching your internal PDFs.*

---

## Q5. What are Agents?  
**Agents** are LLM-powered systems that decide which tools to use, perform multi-step reasoning, and take actions to solve tasks.  
➡️ *Example: An agent using a calculator API to answer "What’s 273 * 59?"*

---

## Q6. What are Embeddings?  
**Embeddings** are vector (numeric) representations of text capturing meaning.  
Used to compare similarity, power search, and feed into RAG.  
➡️ *Example: Finding similar FAQs based on user query.*

---

## Q7. Vector Store / Vector Database?  
A **Vector Store** is a database optimized to store and search embeddings efficiently.  
➡️ *Example: Pinecone or FAISS used in document search systems.*

---

## Q8. Prompt Engineering  
The art of designing inputs (prompts) to LLMs to get the best outputs.  
Includes instructions, examples, constraints, and roleplay.  
➡️ *Example: “You are a helpful tutor. Explain Newton’s 2nd law to a 10-year-old.”*

---

## Q9. Fine-Tuning?  
The process of training a pre-trained LLM further on custom data to specialize it for particular tasks, domains, or styles.  
➡️ *Example: Fine-tuning GPT on legal documents for legal advice.*

---

## Q10. Inference  
The act of running a trained model on new input to generate predictions or outputs.  
➡️ *Example: Feeding a paragraph to an LLM to summarize it.*

---

## Q11. What is Token?  
A **token** is a small unit of text (word, part of word, or character) that LLMs process.  
Models have token limits impacting cost and speed.  
➡️ *Example: “ChatGPT” → [‘Chat’, ‘G’, ‘PT’] → 3 tokens (approx).*

---

## Q12. Ollama  
**Ollama** is a platform for running and managing LLMs locally on your machine, providing privacy, low latency, and offline access.  
➡️ *Example: Running LLaMA model on your own laptop using Ollama.*

---

# Additional Concepts to Explore  
- Transformer Architecture  
- Attention Mechanism  
- Zero-shot / Few-shot Learning  
- Chatbots & Conversational AI  
- Ethics & Bias in AI  
- Model Distillation  
- Federated Learning  
- Multimodal Models  
- Evaluation Metrics  
- Data Annotation & Labeling  
- Transfer Learning  
- Prompt Tuning / Prefix Tuning  
- API Integration  
- Cost & Latency Optimization  
- Explainability & Interpretability  

---

*This file is for quick reference of AI and LLM-related concepts.*
