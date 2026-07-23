# AI Enterprise Knowledge Assistant

Enterprise AI assistant that answers employee questions directly from Slack using official company documentation stored in Google Drive.

The system combines workflow automation, document retrieval, AI-powered reasoning and document parsing to provide accurate responses grounded on internal company knowledge.

---

# Objective

Build an enterprise knowledge assistant that enables employees to ask questions in Slack and receive answers generated exclusively from approved company documentation.

The assistant retrieves relevant documents, extracts their content, generates contextual prompts and produces grounded AI responses.

---

# Architecture

Employee

↓

Slack

↓

n8n

↓

Query Processing

↓

Google Drive Retrieval

↓

Document Ranking

↓

Document Parser

(PDF / DOCX / TXT)

↓

Groq (Llama)

↓

Slack Response

---

# Knowledge Retrieval Pipeline

Instead of sending every document directly to the language model, the workflow performs several preprocessing steps.

Current pipeline:

- Slack event reception
- Question normalization
- Keyword extraction
- Synonym expansion
- Typo correction
- Google Drive search
- Metadata validation
- Document filtering
- Document ranking
- Document parsing
- Context generation
- AI answer generation

This approach reduces token usage while improving response accuracy.

---

# Document Processing

The project supports multiple document formats.

Current supported formats:

- PDF
- DOCX
- TXT
- Markdown
- CSV
- XLSX

To support Microsoft Word documents, a dedicated parsing microservice was developed.

Architecture:

n8n

↓

HTTP Request

↓

docx-parser

(FastAPI)

↓

Extracted Text

↓

AI Pipeline

The parser receives DOCX files through multipart/form-data, extracts the document text using **python-docx**, and returns normalized JSON ready for AI processing.

---

# Tech Stack

## Automation

- n8n

## Artificial Intelligence

- Groq API
- Llama Models

## Backend

- Python
- FastAPI
- Uvicorn
- python-docx

## Integrations

- Slack API
- Google Drive API

## Infrastructure

- Ubuntu Server
- Docker
- Docker Compose
- Docker Internal Network

## Documentation

- Markdown

---

# Features

- Slack AI Assistant
- Enterprise Knowledge Base
- Google Drive Retrieval
- Intelligent Document Ranking
- AI-generated Answers
- Source-grounded Responses
- Query Normalization
- Synonym Expansion
- Typo Correction
- DOCX Parsing Service
- Modular Architecture
- Docker-based Deployment

---

# Project Roadmap

- [x] Phase 00 — Project Initialization
- [x] Phase 01 — Slack Integration
- [x] Phase 02 — Google Drive Retrieval
- [x] Phase 03 — Query Processing
- [x] Phase 04 — Document Parsing
- [x] Phase 05 — AI Answer Generation
- [x] Phase 06 — Slack Response
- [x] Phase 07 — Monitoring & Future Improvements

---

# Current Architecture

Internet

↓

Cloudflare Tunnel

↓

n8n

↓

Docker Internal Network

↓

Google Drive

↓

docx-parser

↓

Groq (Llama)

↓

Slack Response

---

# Future Improvements

- Universal Document Parser
- PDF Extraction Service
- PPTX Support
- OCR Integration
- Embeddings
- Vector Database
- Semantic Search
- Full RAG Architecture
- Confluence Integration
- SharePoint Integration
- Notion Integration
- GitHub Knowledge Retrieval
- User Permissions
- Document Versioning
- Monitoring with Prometheus & Grafana

---

# License

MIT License
