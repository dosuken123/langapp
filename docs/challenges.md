# Challenges

This page describes the challenges users could encounter in production.

## RAG pipeline

Challenges:

- How to split unstructred documents into chunks in a structured way?
  e.g. how to convert HTML into markdown properly? So that LLM can embed it more accurately.
- How to re-create an index when the unstructred document are updated?
- How to re-create an index when exracting additional metadata from unstructred documents?
- How to create multiple indexes for A/B testing?
- How to cleanup unused indexes for cutting the cost?
- How to auto-trigger index re-creation when the document is updated, so that we don't need to manually trigger?
- How to auto-adjust the parser for document loading/splitting, so that we don't need to recalibrate parser per ingestion.
- How to perform migration in zero-downtime manner.
