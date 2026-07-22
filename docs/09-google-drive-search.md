# Phase 03 - Enterprise Document Retrieval

## Objective

Retrieve the most relevant internal documents from Google Drive before sending context to the LLM.

## Pipeline

Slack Question

↓

Question Normalizer

↓

Technical Terms Expansion

↓

Split Keywords

↓

Google Drive Search

↓

Metadata Validation

↓

Supported File Filter

↓

Document Deduplication

↓

Document Ranking

↓

Download Documents

## Supported document types

- Google Docs
- Markdown (.md)
- PDF
- DOCX
- TXT

Folders and spreadsheets are ignored.

## Ranking

Each document receives points according to keyword matches.

Example

Question

How do I deploy a workflow?

Expanded keywords

workflow
deployment
deploy
release
n8n

Retrieved

Deployment.md (score 2)

Docker.md (score 1)

The highest scored documents are downloaded first.

## Benefits

- Reduced LLM context
- Better document relevance
- Faster searches
- Easily scalable to thousands of files
