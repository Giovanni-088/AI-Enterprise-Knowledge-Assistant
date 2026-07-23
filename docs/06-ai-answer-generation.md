# AI Answer Generation

## Overview

Once relevant documents have been retrieved from Google Drive and converted into plain text, the AI Agent generates a contextual response using Retrieval-Augmented Generation (RAG).

The objective is to answer user questions using only the organization's internal documentation rather than relying solely on the language model's general knowledge.

---

## Processing Flow

Slack User

↓

Question

↓

n8n Workflow

↓

Google Drive Retrieval

↓

Document Parser

↓

AI Agent

↓

Slack Response

---

## Context Preparation

The workflow collects the extracted text from one or multiple documents and prepares a prompt containing:

- User question
- Relevant document content
- System instructions

The AI model receives only the information required to answer the user's request.

---

## Supported Input Sources

Current supported document types include:

- PDF
- DOCX
- TXT
- CSV
- XLSX

Additional document formats can be integrated by adding new parser services without modifying the AI workflow.

---

## AI Responsibilities

The AI model is responsible for:

- Understanding the user's question
- Reading the retrieved context
- Producing concise and relevant answers
- Avoiding hallucinations whenever possible
- Using only the retrieved documentation as context

---

## Output

The generated answer is returned to Slack, allowing users to interact with the company's knowledge base using natural language.

Example:

User:
How many vacation days do employees receive?

AI:
Employees receive 15 vacation days after completing their first year of employment according to the Employee Handbook.
