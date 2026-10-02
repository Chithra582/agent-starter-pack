---
name: agentic-rag-orchestration
description: Use when constructing retrieval-augmented generation pipelines, corpus indexing, and hybrid vector search on Google Cloud.
---

# Agentic RAG Orchestration

## Overview
Architects production retrieval-augmented generation systems incorporating query reformulation, reranking, and grounded response synthesis.

## When to Use
- When agents need to retrieve answers from enterprise document corpora (PDF, HTML, Markdown, CSV).
- When integrating Vertex AI Search, BigQuery vector search, or Cloud SQL pgvector.
- When implementing self-reflective retrieval where agents evaluate retrieval relevance before answering.

## Core Capabilities
1. **Dynamic Chunking & Indexing**: Generates semantic chunking and embedding pipelines for unstructured text.
2. **Hybrid Search**: Combines keyword search with dense vector embeddings for maximum recall and precision.
3. **Citation & Grounding Verification**: Enforces factual grounding checks with attributable citation links.
