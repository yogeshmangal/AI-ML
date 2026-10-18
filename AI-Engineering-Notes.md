# AI Engineering Notes: MCP & Claude

## 1. What is MCP?

**MCP (Model Context Protocol)** is a standard that allows AI applications to connect with external tools, APIs, and data sources.

Think of MCP as a common language that AI applications use to communicate with external systems.

### Example: Jira MCP

Suppose you want Claude to search Jira tickets.

- **Jira API:** Provides access to Jira tickets.
- **Java service:** Contains normal Java code that calls Jira APIs.
- **MCP tool:** An operation exposed to AI, such as `searchTickets()`.
- **MCP server:** The running application that exposes tools through the MCP protocol.
- **AI application:** Claude Desktop or another MCP-compatible application.

A Spring Boot project might look like this:

```text
jira-mcp/
├── JiraMcpApplication.java
├── JiraService.java
├── JiraTools.java
└── application.properties
```

Example tool declaration (illustrative Spring AI style):

```java
@Tool(description = "Search Jira tickets using a JQL query")
public String searchTickets(String jql) {
    return jiraService.search(jql);
}
```

**Important:** An annotation alone does not create an MCP server. You also need the appropriate MCP dependencies, server configuration, and transport. The framework handles MCP communication.

### Is `skill.md` part of MCP?

No. A skill file is optional and separate from MCP.

- **Tool:** A function the AI can invoke.
- **MCP server:** Exposes tools through a standardized protocol.
- **Skill file:** Provides reusable instructions explaining how and when to perform a workflow.

---

## 2. MCP Client vs MCP Server

| Component       | Responsibility                             | Example                          |
| --------------- | ------------------------------------------ | -------------------------------- |
| MCP host        | AI application that manages the experience | Claude Desktop                   |
| MCP client      | Communicates with an MCP server            | Client managed by Claude Desktop |
| MCP server      | Exposes tools and other capabilities       | Your Jira MCP application        |
| External system | Stores data or performs operations         | Jira REST API                    |

### Request flow

```text
User: "Find my open Jira tickets"
              |
              v
      Claude / MCP Host
              |
          MCP Client
              |
              v
          MCP Server
              |
          Jira Service
              |
              v
          Jira REST API
```

The server advertises available tools and their input schemas. The AI can use their descriptions to decide which tool is relevant.

The client sends the tool request to the server. The server executes the code and returns the result, which the AI uses to prepare its answer.

**Note:** The host application often provides the MCP client, so you may only need to develop the server.

---

## 3. What Happens Behind the Scenes When You Prompt Claude?

Example prompt:

**"Find my open Jira tickets and summarize them."**

1. **Context assembly:** Claude receives the user's prompt, applicable instructions, conversation context, and other supplied information.
2. **Tool discovery:** The application discovers available tools from the connected MCP server.
3. **Tool selection:** Claude decides whether a tool such as `searchTickets()` is needed.
4. **Tool request:** The MCP client sends the request to the MCP server.
5. **Execution:** The server calls the Jira API and retrieves matching tickets.
6. **Tool result:** The result is returned to Claude through the application.
7. **Final response:** Claude summarizes the retrieved tickets for the user.

```text
User prompt
    |
    v
Claude + available tool definitions
    |
    v
Claude requests a tool call
    |
    v
MCP Client -> MCP Server -> Jira API
    |
    v
Tool result returned to Claude
    |
    v
Final response
```

Claude does not automatically have access to Jira. Access requires a configured integration, available tools, and appropriate permissions.

Claude may also answer without calling a tool if it determines that one is unnecessary.

---

## 4. Why Are There Different Claude Models?

Different models balance **capability, speed, and cost**.

| Model      | General purpose                                                 | Example use cases                                                                          |
| ---------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **Haiku**  | Fast and economical                                             | Classification, extraction, simple summaries, high-volume tasks                            |
| **Sonnet** | Balanced capability and speed                                   | Coding, debugging, analysis, everyday AI applications                                      |
| **Opus**   | Designed for demanding tasks                                    | Complex reasoning, difficult architecture decisions, deep investigations                   |
| **Fable**  | Verify current status and positioning in official documentation | Model names and availability can change; don't assume capabilities based on the name alone |

These are general guidelines, not guarantees. Always check the latest documentation and test models on your own workload.

### Which model should you choose?

- **Haiku:** When speed and low cost matter most for straightforward tasks.
- **Sonnet:** A good starting point for general software engineering and AI applications.
- **Opus:** When a difficult task benefits from stronger reasoning and the extra cost or latency is justified.

For production applications, compare models using correctness, latency, and cost per request.

---

## 5. Quick Revision

- **MCP:** Standard protocol for connecting AI applications to tools and data.
- **MCP server:** A running program that exposes capabilities through MCP.
- **MCP client:** Communicates with the MCP server.
- **MCP host:** The AI application that manages the interaction and client.
- **Spring Boot application:** Can contain business logic and expose selected Java methods as MCP tools.
- **`skill.md`:** Optional workflow instructions, not the MCP server itself.
- **Claude tool use:** Model requests a tool → server executes it → result returns → model responds.
- **Model selection:** Balance capability, speed, and cost.

## Official References

- [Anthropic MCP Documentation](https://docs.anthropic.com/en/docs/mcp)
- [Anthropic Documentation](https://docs.anthropic.com/)
- [Spring AI Documentation](https://docs.spring.io/spring-ai/reference/)
