# This repo is still DRAFT

# 🦜️🖼️ LangApp

LangApp is an open-source web application framework for production-grade LLM applications.

Creating your first LLM application by forking an example project found on Internet is easy,
however, running it on production requires a lot more effort.
For example, you need proper authentications, authorizations, database migrations,
performance optimization, scalable architecture, secure codebase,
maintainable codebase, async workers, cron workers, observability, telemetry,
dependency management, A/B testing, feature flags, and so on.

LangApp guides you to build such application with the harness of [LangChain](https://github.com/langchain-ai/langchain) and [LangSmith](https://docs.smith.langchain.com/).

## High-level components

### Chain Interface

Chains are [chains](https://docs.langchain.com/docs/components/chains/)

>>>
Chains is an incredibly generic concept which returns to a sequence of modular components (or other chains) combined in a particular way to accomplish a common use case.

The most commonly used type of chain is an LLMChain, which combines a PromptTemplate, a Model, and Guardrails to take user input, format it accordingly, pass it to the model and get a response, and then validate and fix (if necessary) the model output.
>>>

### Agents interface

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

### Tasks and pipelines

Pipelines represent end-to-end LLM process chain.
A pipeline could consist of 

Example:

```
pipelines/
```

### Authentications and Authorizations

### Testing

Test data should be collected in the system, and it should be used to test the system.

## Principles

- Convention over Configuration (CoC) ... It provides sensible defaults and conventions for naming and structuring code and database tables.
- Don't Repeat Yourself (DRY) ... Aiming to minimize redundancy in code by promoting code reuse and modularity.
- RESTful Routing: It promotes the use of RESTful (Representational State Transfer) routes, which correspond to the standard HTTP methods (GET, POST, PUT, DELETE) and make it easier to interact with [chains](https://docs.langchain.com/docs/components/chains/) and [agents](https://docs.langchain.com/docs/components/agents/).
- Scaffolding: It provides a command called "scaffold" that generates boilerplate code for creating a basic [chain](https://docs.langchain.com/docs/components/agents/) or [agent](https://docs.langchain.com/docs/components/agents/) interface, helping developers get started quickly.
- Testing and evaluations: It encourages and makes it easy to write integration tests for your chains and agents, promoting test-driven development (TDD).
- Auto Scale: When a request volume increases, the chain/agent instances will automatically scale up.
- Cost efficient: When a request volume decreases, the chain/agent instances will automatically scale down.

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