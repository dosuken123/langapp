# CLI

```shell
# Generate a new LLM application
langapp new <app-name>

# Generate a new pipeline
langapp generate pipeline <pipeline-name>

# Generate a new pipeline from a Jupyter Notebook file
langapp generate pipeline <pipeline-name> --from=<file-path>

# Run a pipeline
langapp run pipeline <pipeline-name>

# Run a pipeline with input variables (directly or from a file)
langapp run pipeline <pipeline-name> --env FOO=var
langapp run pipeline <pipeline-name> --env-file <dotenv-file-path>

# Generate a new evaluator for integration tests
langapp generate evaluator <name>

# Generate a new vector store
langapp generate vector store <store-name>

# Generate a new migration
langapp generate migration <migration-name>

# Run database migrations
langapp db:migrate

# Start the langapp server
langapp server
```
