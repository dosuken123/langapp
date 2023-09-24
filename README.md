# 🦜️🖼️ LangFrame

LangFrame is a framework for developing production-grade LLM applications.

Creating your first LLM application by copy-pasting examples you found on Internet is easy,
however, running it for production is a different story.
You need proper authentication/authorizations, database migrations,
performance optimization, scaling architecture, secure codebase,
maintenable code structure, async and cron workers, observability, telemetry,
dependency management, and so on.

LangFrame guides you to build such application like Ruby on Rails.

## Concept

- Build a web application that provides APIs for LLM features.
- Build both [chains](https://docs.langchain.com/docs/components/agents/) and [agents](https://docs.langchain.com/docs/components/agents/).
- Convention over Configuration
- DRY
- Upgrade your application as the dependencies grow.

## High-level components

### Agents and Controllers

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

### Database and Vector Stores

Database for 

```
# Vector stores
vectors/      ... Vector stores
```

### Tasks, Pipelines and Chains

Pipelines represent end-to-end LLM process chain.
A pipeline could consist of 

Example:

```
pipelines/
```

### Authentications/Authorizations


## Dependencies

- FastAPI for web server
- Celery for async and cron job 
- Redis for caching and async jobs
- LangChain for all-in-one LLM framework.
- You can add any additional dependencies.
- Sqlalchemy for Database integrations.
