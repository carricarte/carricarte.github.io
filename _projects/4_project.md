---
layout: page
title: Steuerberater
description: Retrieval-Augmented Generation system for German income tax questions
importance: 4
category: past
---

**RAG Steuerberater** is a bilingual (German/English) question-answering system that helps users navigate German income tax returns (*Steuererklärung*) using only official primary sources. The system retrieves and cites directly from government publications, ensuring every answer is grounded in authoritative legal text rather than general LLM knowledge.

## Knowledge Base

The corpus (~24,000 chunks from ~1,380 documents) is built from four official sources:

- **BMF** (Bundesfinanzministerium) — ~17,000 chunks of ministry guidance
- **Gesetze im Internet** — ~6,000 chunks of statutory text
- **BZSt** (Bundeszentralamt für Steuern) — ~440 chunks
- **ELSTER** — ~260 chunks of e-filing documentation

Documents are chunked at 1,200 characters with 200-character overlap and embedded with **BGE-M3** multilingual embeddings into a persistent **Chroma** vector index.

## Retrieval Pipeline

1. Async scraping of official sources
2. Chunking + 1,024-d BGE-M3 embedding
3. Hybrid retrieval: dense vector search + BM25 keyword matching
4. Cross-encoder reranking with **BGE-reranker-v2-m3**
5. LCEL generation chain via Claude or OpenAI

## Interface

- CLI tools for index management and querying
- **FastAPI** HTTP server with OpenAPI documentation

> This tool is for informational purposes only and does not constitute legal or tax advice. Always consult a licensed *Steuerberater* for official guidance.

<a href="https://github.com/carricarte/rag_steuer_berater" target="_blank" class="btn btn-sm z-depth-0" role="button">GitHub Repository</a>
