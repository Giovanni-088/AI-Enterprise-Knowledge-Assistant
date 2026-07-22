# Google Drive Integration

## Objective

Integrate Google Drive as the primary enterprise knowledge source for the AI assistant.

---

# Knowledge Base Structure

Enterprise Knowledge Base

├── HR

├── IT

├── Operations

└── Development

Each department stores documentation that can be queried by employees through Slack.

---

# Supported Formats

- PDF
- DOCX
- Markdown
- TXT

---

# Workflow

Slack Question

↓

Keyword Extraction

↓

Google Drive Search

↓

Download Documents

↓

Extract Text

↓

Send Context to AI

---

# Authentication

Google Drive is accessed using OAuth2 credentials configured in n8n.

The workflow only requires read permissions.

---

# Design Goals

- Reduce token usage
- Download only relevant documents
- Keep documentation centralized
- Support future semantic search

---

# Current Status

In Progress
