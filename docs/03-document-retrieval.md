# Document Retrieval System

## Overview

The document retrieval module is responsible for finding the most relevant internal company documents based on employee questions received through Slack.

The system uses Google Drive as the only knowledge source.

---

# Retrieval Pipeline

The retrieval process consists of:

1. Query normalization
2. Keyword extraction
3. Technical term expansion
4. Google Drive search
5. Metadata validation
6. File type filtering
7. Document deduplication
8. Document ranking
9. Document extraction

---

# Query Normalizer

The incoming Slack message is cleaned before searching.

Responsibilities:

- Remove Slack mentions
- Normalize lowercase text
- Remove unnecessary characters
- Detect empty queries

Example:

Input:


<@BOT> donde veo la configuracion de docker?


Output:

```json
{
"normalized_question":
"donde veo la configuracion de docker"
}
Technical Terms Filter

The system expands user vocabulary using internal synonyms.

Example:

Input:

reiniciar docker

Expansion:

[
"docker",
"container",
"contenedor",
"restart",
"compose"
]

This improves results when employees use different terminology.

Google Drive Search

Google Drive acts as the company knowledge repository.

Supported documents:

Markdown
PDF
DOCX
TXT

Unsupported files are ignored automatically.

Metadata Validation

Before processing documents, the system validates:

File ID
File name
MIME type

Example:

{
"name":"Docker.md",
"mimeType":"text/markdown"
}
File Type Filter

Only supported documents continue.

Allowed:

text/markdown
text/plain
application/pdf
application/vnd.openxmlformats-officedocument.wordprocessingml.document
Document Deduplication

Removes duplicated search results.

Example:

Before:

Deployment.md
Deployment.md
Docker.md

After:

Deployment.md
Docker.md
Document Ranking

Each document receives a relevance score.

Factors:

Keyword matches
Document type
Technical term matches

Example:

Question:

¿Cómo reinicio un contenedor docker?

Result:

[
{
"name":"Docker.md",
"score":8
}
]

The highest ranked documents are sent to the extraction stage.

Current Limitations

Current retrieval does not use embeddings or vector databases.

The system currently uses:

Keyword expansion
Text matching
Scoring algorithm

Future improvements:

Vector database
Semantic search
Document chunking
RAG with embeddings

---
