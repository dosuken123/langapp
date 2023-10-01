# Dependencies

- Python 3.7+
- [LangChain](https://github.com/langchain-ai/langchain): Building applications with LLMs through composability.
- [LangSmith](https://github.com/langchain-ai/langsmith-sdk): Observability for chains and agents.
- [FastAPI](https://github.com/tiangolo/fastapi): FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.7+ based on standard Python type hints.
- (TBD) [Sqlalchemy](https://www.sqlalchemy.org/): The Python SQL toolkit and Object Relational Mapper that gives application developers the full power and flexibility of SQL.
- (TBD) [Alembic](https://alembic.sqlalchemy.org/en/latest/): Alembic is a lightweight database migration tool for usage with the SQLAlchemy Database Toolkit for Python.
- (TBD) [Celery](https://github.com/celery/celery): Distribute work across threads or machines, a.k.a. workers.
- (TBD) [Redis](https://github.com/redis/redis): Caching and manage job queues.

## asdf

https://asdf-vm.com

See `.tool-versions` file for the local dependencies:

```
# Search available package
asdf plugin list all | grep python

# Add a new plugin
asdf plugin add python https://github.com/danhper/asdf-python.git

# See available versions
asdf list all python

# Install a specific version
asdf install python 3.10.13

# Set it to the local project
asdf local python 3.10.13
```
