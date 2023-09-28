# Developmnets

### Agent Interfaces

Some applications will require not just a predetermined chain of calls to LLMs/other tools, but potentially an unknown chain that depends on the user's input. In these types of chains, there is a [“agent”](https://docs.langchain.com/docs/components/agents/) which has access to a suite of tools. Depending on the user input, the agent can then decide which, if any, of these tools to call.

```
POST /api/v1/agents/<name> ... Execute an agent
POST /api/v1/agents/<name>/feedback ... Post feedback for the agent
```

Agents running on your server. It accepts requests from clients and autonomous agents.

- Agent runs on a process.
- Agent can receive a request to perform certain tasks, such as executing a [LLM pipeline](#pipelines-and-chains).
- Agent can perform a task 

To clarify, this framework refers the chains as agents too. As technically an agent is just executing a LLM chain and return a result (like RAG app).
As a future proof approach, we generalize the 

Agents are exposed via APIs.

Example:

```
agents/
    question-answering.py
    pr-reviewer.py
```

### Data-aware: Database and Vector Stores

Database for 

```
# Vector stores
db/      ... Vector stores
```

### Authentications and Authorizations

### Feedback

Path formats:

```
POST /api/v1/feedback ... Feedback to the trace ID
```
