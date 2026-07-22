# AI Enterprise Knowledge Assistant

Enterprise AI assistant that answers employee questions from Slack using official company documentation stored in Google Drive and GitHub.

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
└── GitHub Docs

↓

Document Processing

↓

Groq (Llama)

↓

Slack Response


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
- GitHub API

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
- GitHub documentation retrieval
- Google Drive document retrieval
- AI-generated answers
- Source references
- Protection against hallucinations

---

# Project Roadmap

- [x] Phase 00 - Project Initialization
- [x] Phase 01 - Slack Integration
- [ ] Phase 02 - Google Drive Retrieval
- [ ] Phase 03 - GitHub Documentation Retrieval
- [ ] Phase 04 - Document Search
- [ ] Phase 05 - AI Response Generation
- [ ] Phase 06 - Slack Response
- [ ] Phase 07 - Conversation Logging
- [ ] Phase 08 - Error Handling & Monitoring

---
# Current Progress

## ✅ Phase 00

- Project structure
- Documentation
- Docker environment
- GitHub repository

## ✅ Phase 01

- Slack App created
- OAuth configured
- Bot User created
- Event Subscriptions configured
- Secure webhook integration with n8n
- Cloudflare Tunnel connectivity

# Future Improvements

- Vector database integration
- Embeddings
- Semantic search
- RAG architecture
- User permissions
- Document versioning

---

# License

MIT License
