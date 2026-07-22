# AI Enterprise Knowledge Assistant

Enterprise AI assistant that answers employee questions from Slack using official company documentation stored in Google Drive and subsequently GitHub.

The project uses automation workflows, document processing and Large Language Models to provide reliable answers based only on internal knowledge sources.

---

# Objective

Build an AI-powered enterprise knowledge assistant that allows employees to query internal documentation directly from Slack.

The assistant retrieves information from approved company sources, processes the documents, sends relevant context to an LLM and returns a grounded response with references.

---

# Architecture


Employee

↓

Slack

↓

n8n

↓

Document Retrieval

├── Google Drive

↓

Document Processing

↓

Groq (Llama)

↓

Slack Response

## Knowledge Retrieval Pipeline

The assistant does not send every document directly to the AI model.

The workflow performs:

1. User question analysis
2. Keyword extraction
3. Document search
4. Metadata validation
5. File filtering
6. Document ranking
7. Context generation
8. AI response generation


This reduces token usage and prevents hallucinations.

---

# Tech Stack

## Automation

- n8n

## Artificial Intelligence

- Groq API
- Llama models

## Integrations

- Slack API
- Google Drive API

## Infrastructure

- Ubuntu Server
- Docker
- Docker Compose

## Documentation

- Markdown
- PDF
- DOCX

---

# Features

- Slack-based AI assistant
- Internal documentation search
- Google Drive document retrieval
- AI-generated answers
- Source references
- Protection against hallucinations

---

# Project Roadmap

- [x] Phase 00 - Project Initialization
- [x] Phase 01 - Slack Integration
- [x] Phase 02 - Google Drive Retrieval
- [ ] Phase 03 - Document Search
- [ ] Phase 04 - AI Response Generation
- [ ] Phase 05 - Slack Response
- [ ] Phase 06 - Conversation Logging
- [ ] Phase 07 - Error Handling & Monitoring

---
# Current Progress

# Project Progress

## Phase 00 — Project Initialization

Completed:

- GitHub repository created
- Project structure defined
- Documentation initialized
- Environment configuration created


## Phase 01 — Slack Integration

Completed:

- Slack App created
- Bot User configured
- OAuth permissions configured
- Event Subscriptions enabled
- Slack webhook verification completed
- n8n integration through Cloudflare Tunnel


## Phase 02 — Knowledge Source & Query Processing 

Completed:

- Google Drive connected as knowledge source
- Enterprise Knowledge Base created
- Internal documentation uploaded
- Slack event extraction implemented
- Query Normalizer implemented
- Text normalization
- Accent removal
- Stop word filtering
- Keyword extraction
- Synonym expansion
- Levenshtein-based typo correction
- Query validation through Slack tests

# Future Improvements

- Vector database integration
- Embeddings
- Semantic search
- RAG architecture
- User permissions
- Document versioning
- GitHub Documentation Retrieval
- Confluence Integration
- SharePoint Integration
- Notion Integration
- Vector Database
- Semantic Search

```md
## Knowledge Retrieval

The assistant retrieves information from internal company documentation stored in Google Drive.

Current capabilities:

- Slack question processing
- Query normalization
- Technical keyword expansion
- Google Drive document search
- File validation
- Document ranking

Supported formats:

- Markdown
- PDF
- DOCX
- TXT

The retrieval engine currently uses keyword-based ranking and is designed to evolve into a full RAG architecture with embeddings and vector search.
---
## Current Features

- Slack Event API integration
- Secure Slack webhook verification
- AI-ready question normalization
- Technical keyword extraction
- Synonym expansion
- Google Drive Enterprise Knowledge Base
- Intelligent document ranking
- Multi-department document search
- Duplicate removal
- Flexible document type filtering

# License

MIT License
