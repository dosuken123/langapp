# This repo is still DRAFT

# 🦜️🖼️ LangFrame

LangFrame is an open-source web application framework for production-grade LLM applications.

Creating your first LLM application by forking an example project found on Internet is easy,
however, running it on production requires a lot more effort.
For example, you need proper authentications, authorizations, database migrations,
performance optimization, scalable architecture, secure codebase,
maintainable codebase, async workers, cron workers, observability, telemetry,
dependency management, A/B testing, feature flags, and so on.

LangFrame guides you to build such application as an extention to the [LangChain](https://github.com/langchain-ai/langchain).

## Key features and Concept

- Convention over Configuration (CoC) ... It provides sensible defaults and conventions for naming and structuring code and database tables.
- Don't Repeat Yourself (DRY) ... Aiming to minimize redundancy in code by promoting code reuse and modularity.
- RESTful Routing: It promotes the use of RESTful (Representational State Transfer) routes, which correspond to the standard HTTP methods (GET, POST, PUT, DELETE) and make it easier to interact with [chains](https://docs.langchain.com/docs/components/chains/) and [agents](https://docs.langchain.com/docs/components/agents/).
- Scaffolding: It provides a command called "scaffold" that generates boilerplate code for creating a basic [chain](https://docs.langchain.com/docs/components/agents/) or [agent](https://docs.langchain.com/docs/components/agents/) interface, helping developers get started quickly.
- Testing and evaluations: It encourages and makes it easy to write integration tests for your chains and agents, promoting test-driven development (TDD).
- Auto Scale: When a request volume increases, the chain/agent instances will automatically scale up.
- Cost efficient: When a request volume decreases, the chain/agent instances will automatically scale down.

## High-level components

### Chains and Agents interface

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

### Tasks and pipelines

Pipelines represent end-to-end LLM process chain.
A pipeline could consist of 

Example:

```
pipelines/
```

### Authentications/Authorizations


## Key Dependencies

- Python 3.7+
- [LangChain](https://github.com/langchain-ai/langchain): Building applications with LLMs through composability.
- [LangSmith](https://github.com/langchain-ai/langsmith-sdk): Observability for chains and agents.
- [FastAPI](https://github.com/tiangolo/fastapi): FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.7+ based on standard Python type hints.
- [Ragas](https://github.com/explodinggradients/ragas): Evaluate your Retrieval Augmented Generation (RAG) pipelines.
- (TBD) [Sqlalchemy](https://www.sqlalchemy.org/): The Python SQL toolkit and Object Relational Mapper that gives application developers the full power and flexibility of SQL.
- (TBD) [Alembic](https://alembic.sqlalchemy.org/en/latest/): Alembic is a lightweight database migration tool for usage with the SQLAlchemy Database Toolkit for Python.
- (TBD) [Celery](https://github.com/celery/celery): Distribute work across threads or machines, a.k.a. workers.
- (TBD) [Redis](https://github.com/redis/redis): Caching and manage job queues.