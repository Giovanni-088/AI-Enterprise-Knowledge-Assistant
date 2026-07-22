# Query Normalization

## Objective

Improve document retrieval accuracy by transforming natural user questions into structured search queries.

Users may write:

- Incorrect spelling
- Informal language
- Different terminology
- Abbreviations

The normalizer improves retrieval before querying the knowledge base.

---

# Pipeline

User Question

↓

Text Cleaning

↓

Accent Normalization

↓

Stop Word Removal

↓

Typo Correction

↓

Keyword Extraction

↓

Synonym Expansion

↓

Search Query


---

# Implemented Features

## Text Cleaning

Removes:

- Slack bot mentions
- Special characters
- Unnecessary formatting


## Accent Normalization

Examples:


conexión → conexion
configuración → configuracion


---

## Typo Correction

Uses Levenshtein distance to identify similar words.

Examples:


vacasiones → vacaciones

dockerr → docker

workflwo → workflow


---

## Synonym Expansion

Examples:


vacaciones

↓

vacation
leave
hr

deploy

↓

deployment
release


---

# Example

Input:


@assistant como le ago para pedir vacasiones


Output:

```json
{
 "normalized_question":
 "como le hago para pedir vacaciones",

 "keywords":[
   "vacaciones",
   "vacation",
   "leave",
   "hr"
 ]
}
Future Improvements

Possible improvements:

NLP classification
Embeddings
Semantic similarity
Intent detection

---

# docs/00-roadmap.md

Actualiza:

```markdown
## Phase 02 — Google Drive Retrieval

Status: Completed

Tasks:

[x] Create enterprise knowledge base
[x] Configure Google Drive credentials
[x] Upload internal documentation
[x] Receive Slack questions
[x] Extract user queries
[x] Normalize queries
[x] Generate keywords
[x] Validate retrieval preparation
