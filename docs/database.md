# Database

Problem to solve:

- Easy to define ingestion pipelines.
- Easy to trace ingestion pipelines.
- When the original documents are outdated, the system can perform ingestions without downtime.
- The system repetedly check the 
- Support realtime ingestions.

## Ingestion

https://docs.langchain.com/docs/use-cases/qa-docs#ingestion

>>>
In order use a language model to interact with your data, you first have to get in a suitable format. That format would be an Index. By putting data into an Index, you make it easy for any downstream steps to interact with it.

There are several types of indexes, but by far the most common one is a Vectorstore. Ingesting documents into a vectorstore can be done with the following steps:

Load documents (using a Document Loader)
Split documents (using a Text Splitter)
Create embeddings for documents (using a Text Embedding Model)
Store documents and embeddings in a vectorstore
>>>

## Ingestion pipelines

```
ingestions/
  ingest_documents.py   # => `index_documents_0_0_1`
```

Index conventions: `index_<feature>_<major>_<minor>_<build>`

## Migration version tracking

This can happen in PostgreSQL.

```
migrations:
  name: index_documents_0_0_1
  version: 0.0.1
```

## Zero-downtime re-ingestions

Often, original documents get outdated and you have to re-ingest them.
To do so, you need to create a new index and migrate the traffic from the old index to the new index.

Example:

- Day 1: Chain A depends on index_documents_0_0_1.
- Day 2: The system creates a new index from the up-to-date documents. This will be index_documents_0_0_2.
- Day 3: Chain A switches to index_documents_0_0_2.
- Day 4: The system cleans up index_documents_0_0_1.

NOTE: The versioning follows [Semantic Versioning](../docs/glossary.md#semantic-versioning).

## Refresh index at the fixed interval

To ensure that you have an up-to-date index from specific documents, you have to run the ingestion pipeline at the fixed interval.

To do so, you can use cron jobs with the harness of [zero-downtime re-ingestions](#zero-downtime-re-ingestions).
