# System Architecture

## Overview

The AI Enterprise Knowledge Assistant follows an automated workflow architecture where Slack acts as the user interface and n8n coordinates communication between external services and the AI model.


# Architecture Diagram


Employee

↓

Slack

↓

n8n

↓

Question Processing

↓

Documentation Sources

├── Google Drive

↓

Document Processing

Google Drive
      │
      ▼
Download File
      │
      ▼
Detect File Type
      │
      ├──────── PDF
      │
      ├──────── TXT
      │
      ├──────── XLSX
      │
      └──────── DOCX
                   │
                   ▼
         docx-parser (FastAPI)
                   │
                   ▼
          Normalized Text
                   │
                   ▼
              AI / RAG

↓

Context Generation

↓

Groq Llama

↓

Response

↓

Slack



# Components


## Slack

Purpose:

Provides the interface where employees interact with the assistant.

Responsibilities:

- Receive questions
- Display responses
- Provide user interaction


---

## n8n

Purpose:

Automation engine responsible for orchestrating the workflow.

Responsibilities:

- Receive Slack events
- Retrieve documents
- Process information
- Call AI services
- Return responses


---

### DOCX Parser Service

A dedicated FastAPI microservice is responsible for extracting text from Microsoft Word (.docx) documents.

Responsibilities:

- Receive binary DOCX files.
- Extract paragraphs using python-docx.
- Return normalized text in JSON.
- Communicate only through the internal Docker network.

---

## Docker Architecture

Cloudflare
     │
     ▼
   n8n
     │
Docker Internal Network
     │
     ▼
docx-parser
     │
     ▼
Extracted Text
     │
     ▼
AI Processing

---

## Google Drive

Purpose:

Store enterprise documentation.

Examples:

- HR manuals
- Policies
- Procedures
- Internal guides


---

## GitHub Documentation (future improvement)

Purpose:

Store technical documentation.

Examples:

- Deployment guides
- Infrastructure documentation
- Development standards


---

## Groq + Llama

Purpose:

Generate responses using retrieved documentation.

Requirements:

- Follow provided context
- Avoid generating unsupported information
- Return useful answers


---

# Design Principles

## Grounded Responses

The assistant must answer using available documentation only.


## No Hallucinations

If information is unavailable:

"No encontré esa información dentro de la documentación interna."


## Scalability

The architecture can evolve into a full RAG system using:

- Embeddings
- Vector databases
- Semantic search
