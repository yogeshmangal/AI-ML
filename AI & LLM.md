# AI & LLM Quick Reference

## Q1. What is LLM?  
**LLM** stands for **Large Language Model**.  
An AI model trained on huge amounts of text data to understand and generate human-like language.  
➡️ *Example: ChatGPT answering coding questions or writing emails.*

---

## Q2. Examples of Popular LLMs

### Large Language Models (LLMs)

| Name        | Company      | Description |
|------------|-------------|-------------|
| **ChatGPT** | OpenAI | One of the most popular LLMs, based on GPT-3.5 and GPT-4. |
| **Claude** | Anthropic | AI assistant focused on safety, helpfulness, and steerability. |
| **LLaMA** | Meta (Facebook) | Meta’s family of open-source LLMs for research and development. |
| **Gemini** | Google DeepMind | Google's next-gen LLM (formerly Bard), focused on reasoning and multi-modal capabilities. |
| **DeepSeek** | DeepSeek AI | AI model focused on efficiency and research-based reasoning. |
| **Grok** | xAI (Elon Musk) | LLM designed for X (formerly Twitter) with real-time data access. |

---

### Related AI Tools

- **Perplexity** → Not an LLM itself, but an **AI search engine**.  
  - Uses LLMs like GPT-4, Claude, etc.  
  - Combines real-time web search with LLM reasoning.  
  - Provides answers with sources, making it ideal for fact-checking and research.

---

## Q3. What is LangChain?  
**LangChain** is a framework to build applications with LLMs by connecting them to external data, memory, tools, and defining workflows (chains).  
➡️ *Example: Building a chatbot that can search documents before replying.*

---

## Q4. What is LangGraph?  
**LangGraph** is a framework built on LangChain for creating stateful, multi-step workflows structured as a graph of nodes and edges.  
➡️ *Example: Creating a chatbot that follows different paths based on user input.*

---

## Q5. What is RAG?  
**RAG** (Retrieval-Augmented Generation) is a technique that lets LLMs access external info (documents, databases) by retrieving relevant content before generating an answer.  
➡️ *Example: Answering a question by first searching your internal PDFs.*

---

## Q6. What are Agents?   
**Agents** are LLM-powered components that can **reason about a task**, **decide what actions to take**, use **external tools or APIs**, and **iterate until a goal is achieved** — instead of just generating a single response.

### Example

**Direct LLM Chat (No Agent):**  
You: *"What is the use of Computer?"*  
→ LLM simply generates a text explanation and replies.  

**Using Agents (via LangChain):**  
You: *"Find the cheapest laptop under ₹50,000 and email me a summary."*  
1. **Research Agent** → Searches online for laptops  
2. **Comparison Agent** → Filters and selects cheapest  
3. **Summarization Agent** → Creates a short summary  
4. **Email Agent** → Sends you the result  

✅ **Key Point:**  
Agents allow an LLM to **act**, not just answer — enabling multi-step, tool-using, goal-oriented workflows.

---

## Q7. What are Embeddings?  
**Embeddings** are vector (numeric) representations of text capturing meaning.  
Used to compare similarity, power search, and feed into RAG.  
➡️ *Example: Finding similar FAQs based on user query.*

---

## Q8. Vector Store / Vector Database?  
A **Vector Store** is a database optimized to store and search embeddings efficiently.  
➡️ *Example: Pinecone or FAISS used in document search systems.*

---

## Q9. Prompt Engineering  
The art of designing inputs (prompts) to LLMs to get the best outputs.  
Includes instructions, examples, constraints, and roleplay.  
➡️ *Example: “You are a helpful tutor. Explain Newton’s 2nd law to a 10-year-old.”*

---

## Q10. Fine-Tuning?  
The process of training a pre-trained LLM further on custom data to specialize it for particular tasks, domains, or styles.  
➡️ *Example: Fine-tuning GPT on legal documents for legal advice.*

---

## Q11. Inference  
The act of running a trained model on new input to generate predictions or outputs.  
➡️ *Example: Feeding a paragraph to an LLM to summarize it.*

---

## Q12. What is Token?  
A **token** is a small unit of text (word, part of word, or character) that LLMs process.  
Models have token limits impacting cost and speed.  
➡️ *Example: “ChatGPT” → [‘Chat’, ‘G’, ‘PT’] → 3 tokens (approx).*

---

## Q13. Ollama  
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
