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

## Overview

Here is the scope of the LangApp framework:

![langapp](docs/img/LangApp.png)

[source](https://docs.google.com/drawings/d/1ushZBAtNDY6EvABnaeKfAA0WWrCmXl_qMfTjGusjS3k/edit?usp=sharing)

While it's covering broad areas, LangApp depends on the third-party tools, frameworks and libraries,
including [LangChain](https://github.com/langchain-ai/langchain) as the comprehensive LLM development kit.
This allows us to focus on the core features, such as providing [Convention over Configuration](https://en.wikipedia.org/wiki/Convention_over_configuration) to developers.
If you already have a working demo on Google Colab, you can easily deploy it to production with minimal effort.

## How to get started

See [Getting Started](docs/getting_started.md).

## Principles

- Convention over Configuration (CoC) ... It provides sensible defaults and conventions for naming and structuring code and database tables.
- Don't Repeat Yourself (DRY) ... Aiming to minimize redundancy in code by promoting code reuse and modularity.
- RESTful Routing: It promotes the use of RESTful (Representational State Transfer) routes, which correspond to the standard HTTP methods (GET, POST, PUT, DELETE) and make it easier to interact with [pipelines](docs/pipelines.md).
- Scaffolding: It provides a command called "scaffold" that generates boilerplate code for creating a basic [pipeline](docs/pipelines.md) interface, helping developers get started quickly.
- Testing and evaluations: It encourages and makes it easy to write integration tests for your [pipeliness](docs/pipelines.md), promoting test-driven development (TDD).
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
