# RAG Chat Assistant

A production-ready **Retrieval-Augmented Generation (RAG) Chat Assistant** that enables organizations to query internal knowledge accurately and securely by combining **vector search** with **local Large Language Models (LLMs)**.

This project demonstrates how to build a **private, enterprise-grade AI assistant** using open-source technologies—without sending sensitive data to third-party APIs.

## Problem Statement

Organizations accumulate large volumes of unstructured data (documentation, conversations, support tickets, policies). Traditional LLM-based chatbots often hallucinate, lack business-specific context, and require external API calls that introduce privacy and cost concerns. As a result, trust and adoption remain low.

## Solution Overview

This system applies Retrieval-Augmented Generation (RAG) to ground LLM responses in company-specific knowledge. User queries are embedded, matched against stored vectors using semantic similarity search, and relevant context is injected into the LLM prompt before response generation. All components run locally for privacy and control.

## Business Value

* Improved answer accuracy through grounded responses
* Reduced hallucinations and increased trust
* Full data privacy with no external API dependency
* Lower operational costs via self-hosted infrastructure
* Faster access to organizational knowledge

### Example Use Cases

* Internal knowledge assistant for employees
* Context-aware customer support tooling
* Engineering documentation and onboarding assistant
* HR, compliance, and policy Q&A systems

## High-Level Architecture

```text
Frontend (Chat UI)
        |
        v
Node.js / Express API
        |
        |-- Embeddings --> Ollama (nomic-embed-text)
        |-- Chat LLM ----> Ollama (gemma3:1b)
        |
        v
PostgreSQL + pgvector (IVFFlat Index)
```

## Tech Stack

| Layer          | Technology                           |
| -------------- | ------------------------------------ |
| Backend        | Node.js, Express                     |
| AI / LLM       | Ollama (gemma3:1b, nomic-embed-text) |
| Vector Store   | PostgreSQL with pgvector             |
| Frontend       | Vanilla JS, HTML, CSS                |
| Infrastructure | Docker, Docker Compose               |
| Configuration  | dotenv                               |

## Core Features

* Retrieval-Augmented chat with semantic context injection
* Vector embeddings for similarity-based retrieval
* Persistent conversation storage and reuse
* High-performance vector search using IVFFlat indexing
* Markdown rendering, code blocks, and enhanced chat UX
* Docker-ready for local or cloud deployment

## Enterprise Usage Scenarios

**Internal Knowledge Assistant:** Employees query policies, incidents, or procedures using natural language, receiving context-backed answers.

**Customer Support Enablement:** Support teams retrieve similar historical tickets and resolutions to improve response quality and speed.

**Engineering Productivity:** Developers query system documentation, architectural decisions, and past discussions to reduce onboarding time.

## Privacy and Security

* Fully local execution using Ollama
* No third-party data sharing
* Database-level access control via PostgreSQL roles
* Suitable for private networks and internal deployments

## Future Enhancements

* Authentication and role-based access control
* Multi-tenant support
* React or Next.js frontend
* Real-time streaming via WebSockets
* Document ingestion (PDFs, Confluence, Notion)
* Conversation summarization and ranking
* Multi-language embedding support

## Project Significance

This project demonstrates practical, production-oriented AI system design, showcasing applied RAG architecture, scalable backend development, and business-aligned AI solutions suitable for enterprise environments or startup MVPs.

Contributions and feedback are welcome.
