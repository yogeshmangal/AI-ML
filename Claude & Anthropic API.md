# Claude & Anthropic API Notes

## 1. Claude
Claude is an **AI chatbot / Large Language Model (LLM)** created by **Anthropic**, similar to **ChatGPT** by OpenAI.

Like ChatGPT, Claude can:
- Answer questions
- Generate text
- Help with coding
- Summarize documents
- Assist in reasoning and workflows

---

## 2. Anthropic
Anthropic is the company behind Claude, focused on building safe, helpful, and steerable AI systems.

---

## 3. Anthropic API
The **Anthropic API** allows developers to integrate Claude into their own applications, websites, or products.

- Similar to how OpenAI provides an API for ChatGPT.
- Works over **HTTP requests** (JSON format):
  - Send a request with a prompt
  - Receive Claude’s response programmatically

### Example Use Cases
- Customer support chatbots  
- Writing assistants  
- Code helpers  
- Document summarizers  
- Knowledge management tools  

---

## 4. Claude Models

Claude offers multiple model options with different trade-offs:

| Model           | Intelligence | Latency       | Cost          | Best Use Case |
|----------------|-------------|--------------|--------------|---------------|
| **Claude Opus** | High        | Higher       | Expensive    | Complex reasoning, deep problem solving |
| **Claude Sonnet** | Moderate  | Moderate    | Moderate    | Everyday use, smart assistants |
| **Claude Haiku** | Moderate   | Low         | Low         | Fast responses, cost-effective |

### Claude 4 Family
- **Claude Opus 4**
- **Claude Sonnet 4** → designed for smart, efficient, everyday use (like ChatGPT)

---

## 5. MCP Servers (Model Context Protocol)

MCP = **Model Context Protocol** – a protocol developed by Anthropic that lets AI assistants like Claude securely connect to external data sources and tools.

### What MCP Server Does
- Acts as a **bridge** between Claude and external systems (databases, APIs, file systems, etc.)
- Provides a **standardized** way for Claude to access real-time data and perform actions
- Enables Claude to work with **local files**, **databases**, or **web services**

### Key Features
- **Security**: Runs locally on your machine, so sensitive data never leaves your environment  
- **Standardization**: Uses a common protocol that different tools can implement  
- **Flexibility**: Can connect to various data sources (Git repos, databases, file systems, web APIs)

### Common Use Cases
- Reading and analyzing local files & documents  
- Querying databases for up-to-date information  
- Integrating with dev tools & repositories  
- Connecting to business systems & APIs  
- Accessing real-time data sources  

### How It Works
1. You run an MCP server locally  
2. The server connects to your data sources (files, DBs, APIs)  
3. Claude requests data through MCP  
4. The server fetches and returns the data securely  

This allows Claude to work with your **specific data and tools** while maintaining **security and privacy**.

---

## 6. CData MCP + Claude Desktop (Salesforce Example)

**MCP (Model Context Protocol)** = Bridge between Claude and external systems (DBs, APIs, files)

**CData MCP Server** = Enterprise-ready MCP implementation with 350+ connectors (Salesforce, Jira, SharePoint, etc.)

### Workflow Example
1. You ask Claude:  
   > “Show me all opportunities in Salesforce this month.”
2. Claude uses MCP tools → sends the request to **CData MCP Server**  
3. **CData MCP Server** translates it into the correct Salesforce query (SOQL/SQL)  
4. Salesforce returns data → **CData MCP Server** passes it back to Claude  
5. Claude presents results in natural language (or a neat table)

### Benefits
- **No need to write SQL/SOQL manually**  
- Works across many data sources with the same interface  
- **Secure** – data stays local/in your infra  
- Turns Claude into a **natural language interface** for enterprise data  

---

## 7. Multi-Turn Conversations

By default, Anthropic API (and Claude) **does not store conversation history**.  
This means a follow-up question **does not have the context** of the previous question unless you provide it manually.

Example:

**You:** What is quantum computing? Give answer in one sentence  
**Claude:** [Answer about quantum computing]  
**You:** Now give another sentence  
**Claude:** [Random answer, not related to quantum computing]

### How to Enable Multi-Turn Conversation
To maintain context:
1. **Manually maintain a list of messages** in your code
2. **Provide the entire message list** (including previous Q&A) with every follow-up request

This creates a continuous chat experience.

---
