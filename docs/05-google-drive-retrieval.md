# Google Drive Retrieval

## Objective

Retrieve the most relevant documents from Google Drive to answer user questions accurately.

The retrieval pipeline is optimized to reduce unnecessary API calls while maximizing document relevance.

---

## Retrieval Pipeline

User Question

↓

Extract Event

↓

Query Normalizer

↓

Technical Terms Filter

↓

Split Keywords

↓

Google Drive Search

↓

Document Metadata Validator

↓

File Type Filter

↓

Document Deduplicator

↓

Document Ranking

↓

Download Document

↓

AI Context

---

## Query Normalization

Natural language questions are transformed into normalized search terms.

Example:

Question:

How do I deploy a workflow?

Normalized keywords:

- workflow
- deployment
- docker

This increases retrieval accuracy without requiring exact filename matches.

---

## Technical Terms Filter

Only technical keywords are kept.

Example

Input

- how
- deploy
- workflow
- docker
- please

Output

- workflow
- docker

This avoids unnecessary Google Drive searches.

---

## Google Drive Search

Each keyword generates a filename search.

Example

workflow

↓

Deployment.md

Workflow Errors.md

Docker.md

The workflow executes multiple searches and merges the results.

---

## Metadata Validation

Every result is validated before processing.

Collected metadata

- File ID
- File Name
- MIME Type

Example

Deployment.md

text/markdown

---

## Supported File Types

Current supported MIME types

- text/markdown
- text/plain
- application/pdf
- application/vnd.openxmlformats-officedocument.wordprocessingml.document
- application/vnd.google-apps.document

Unsupported types are ignored automatically.

Examples

- Google Sheets
- Images
- Videos
- Folders

---

## Document Deduplication

Multiple searches may return the same document.

Example

workflow

↓

Deployment.md

deployment

↓

Deployment.md

Only one instance is kept.

---

## Document Ranking

Documents receive a relevance score.

Current algorithm

+1 point for every keyword match.

Example

Question

Deploy workflow

Results

Deployment.md → 2

Docker.md → 1

Workflow Errors.md → 1

The highest ranked documents are downloaded first.

---

## Document Download

Only validated documents are downloaded.

The workflow automatically handles:

- Markdown
- TXT
- PDF
- DOCX
- Google Docs

Downloaded documents are combined into the context sent to the LLM.

---

## Current Limitations

Current retrieval uses filename matching.

Future versions may include

- BM25
- Metadata weighting
- Semantic Search
- Embeddings
- Hybrid RAG
- Vector Database support

---

## Benefits

- Low Google Drive API usage
- Fast retrieval
- Department-independent
- Easy to maintain
- No Vector Database required

---

## Supported File Types

Current supported document types include:

- PDF
- TXT
- CSV
- XLSX
- DOCX

---
