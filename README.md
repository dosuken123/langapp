# This repo is still DRAFT

# 🦜️🖼️ LangFrame

LangFrame is an open-source web application framework for production-grade LLM applications.

Creating your first LLM application by copy-pasting examples you found on Internet is easy,
however, running it for production is a different story.
You need proper authentication/authorizations, database migrations,
performance optimization, scaling architecture, secure codebase,
maintenable code structure, async and cron workers, observability, telemetry,
dependency management, and so on.

LangFrame guides you to build such application like Ruby on Rails.

## Key features and Concept

- Convention over Configuration (CoC) ... It provides sensible defaults and conventions for naming and structuring code and database tables. Developers can save time by not needing to specify every detail, as It makes assumptions based on these conventions.
- Don't Repeat Yourself (DRY) ... It encourages the DRY principle, aiming to minimize redundancy in code by promoting code reuse and modularity.
---- ActiveRecord: Rails includes an Object-Relational Mapping (ORM) library called ActiveRecord. It simplifies database interaction by representing database tables as Ruby objects and allowing developers to manipulate records using Ruby methods.
- RESTful Routing: It promotes the use of RESTful (Representational State Transfer) routes, which correspond to the standard HTTP methods (GET, POST, PUT, DELETE) and make it easier to build RESTful web applications.
- Scaffolding: It provides a command called "scaffold" that generates boilerplate code for creating a basic [Chain](https://docs.langchain.com/docs/components/agents/) or [Agent](https://docs.langchain.com/docs/components/agents/) interface for a model, helping developers get started quickly.
- Active Support: Rails includes a comprehensive library called Active Support, which provides a wide range of utility classes and methods to simplify common programming tasks.
- Testing and evaluations: It encourages and makes it easy to write integration tests for your chains and agents, promoting test-driven development (TDD).

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