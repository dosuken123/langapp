# 🦜️🖼️ LangFrame

LangFrame is a framework for building LLM-powered web applications.
It guides you to build a production-ready LLM apps 

## Concept

- Convention over Configuration
- DRY
- Web server provides APIs ... FastAPI.
- Worker
- Fast API for backend webserver.
- Celery for workers.
- Web Framework for developing LLM applications

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
