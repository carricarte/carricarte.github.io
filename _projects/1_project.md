---
layout: page
title: DementIA
description: Multi-agent AI clinical decision support system for dementia care
importance: 1
category: healthcare
---

**DementIA** is an AI-powered clinical decision support system designed to assist clinicians in the diagnosis, staging, and management of dementia. The system uses a multi-agent architecture built with **LangGraph**, where a coordinator agent classifies incoming clinical queries by dementia stage and routes them to specialist sub-agents covering screening, diagnosis, prevention, treatment, and patient care.

An **Analyzer Agent** processes patient-specific data and generates structured clinical summaries without persisting any patient information, ensuring privacy by design.

## Architecture

- **Multi-agent orchestration**: LangGraph-based coordinator + specialist agents
- **Knowledge base**: LanceDB vector store with ~6,900 chunks from AWMF dementia guidelines and PubMed literature, embedded with PubMedBERT
- **LLM backbone**: Claude Opus 4.8 (Anthropic)
- **Backend**: FastAPI (Python ≥ 3.11)
- **Frontend**: React + Vite + Tailwind CSS
- **Streaming**: Server-Sent Events with inline citations and personalization metadata

## Scope

Covers **20 dementia subtypes** including Alzheimer's disease, vascular dementia, Lewy body dementia, frontotemporal dementia variants, CTE, and Creutzfeldt-Jakob disease.

<a href="https://github.com/carricarte/DementIA" target="_blank" class="btn btn-sm z-depth-0" role="button">GitHub Repository</a>
