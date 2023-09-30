# This repo is still DRAFT

# 🦜️🖼️ LangApp

LangApp is an open-source web application framework for production-grade LLM applications.
You can get your idea into production seamlessly.

Creating your first LLM application by starting from an example project is easy.
However, running it on production requires a lot more effort,
for example, you need proper authentications, authorizations, database migrations,
performance optimization, scalable architecture, secure codebase,
maintainable codebase, async workers, cron workers, observability, telemetry,
dependency management, A/B testing, feature flags, and so on.

LangApp guides you to build such application with closely following [LangChain](https://github.com/langchain-ai/langchain) as the abstraction guideline.

## Key features

### Pipeline APIs

[Chains](https://docs.langchain.com/docs/components/chains/) is an incredibly generic concept which returns to a sequence of modular components (or other chains) combined in a particular way to accomplish a common use case.
Applications provide the interfaces for interacting with [chains](https://docs.langchain.com/docs/components/chains/) via HTTP requests.

Path formats:

```
POST /api/v1/pipelines/<name> ... Execute a chain
POST /api/v1/pipelines/<name>/feedback ... Post feedback for the chain
```

[“Agents”](https://docs.langchain.com/docs/components/agents/) are essentially subclasses of the chains, therefore it's provided by the same interface.

For more information, see [Developments](docs/developments.md).

### Versioning and composability

Pipelines, which is the definition of data flow, are versioned and immutable.
LangApp compiles the code into a docker image and tag it with a version number.
You can later strategies how these versions should be handled on production, such as,
deploying to the latest version, canary deployment, A/B testing, etc.

Pipelines are defined in the YAML file to make it composable and reusable.

### Kubernetes

LangApp is designed for Kubernetes as the production platform.

![langapp](docs/img/LangApp.png)

[source](https://docs.google.com/drawings/d/1ushZBAtNDY6EvABnaeKfAA0WWrCmXl_qMfTjGusjS3k/edit?usp=sharing)

## Getting Started

See [Getting Started](docs/getting_started.md).

## Principles

- Convention over Configuration (CoC) ... It provides sensible defaults and conventions for naming and structuring code and database tables.
- Don't Repeat Yourself (DRY) ... Aiming to minimize redundancy in code by promoting code reuse and modularity.
- RESTful Routing: It promotes the use of RESTful (Representational State Transfer) routes, which correspond to the standard HTTP methods (GET, POST, PUT, DELETE) and make it easier to interact with [chains](https://docs.langchain.com/docs/components/chains/) and [agents](https://docs.langchain.com/docs/components/agents/).
- Scaffolding: It provides a command called "scaffold" that generates boilerplate code for creating a basic [chain](https://docs.langchain.com/docs/components/agents/) or [agent](https://docs.langchain.com/docs/components/agents/) interface, helping developers get started quickly.
- Testing and evaluations: It encourages and makes it easy to write integration tests for your chains and agents, promoting test-driven development (TDD).
- Auto Scale: When a request volume increases, the chain/agent instances will automatically scale up.
- Cost efficient: When a request volume decreases, the chain/agent instances will automatically scale down.

## Further details

- [Developments](docs/developments.md)
- [Deployments](docs/deployments.md)
- [Dependencies](docs/dependencies.md)
- [Observability](docs/observability.md)
- [Evaluations](docs/evaluations.md)
- [Contributions](docs/contributing.md)
- [License](LICENSE)
