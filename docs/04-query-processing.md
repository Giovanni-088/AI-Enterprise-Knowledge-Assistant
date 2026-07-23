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

↓

Download File

↓

Detect File Type

↓

Route to Parser

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

---

### DOCX Processing

If the retrieved document is a Microsoft Word file, n8n sends the binary file to the document parser service.

The parser extracts the text and returns normalized content for the AI Agent.

Google Drive

↓

Binary File

↓

HTTP Request

↓

docx-parser

↓

Extracted Text

↓

AI Agent

---
## Future Improvements

Possible improvements:

NLP classification
Embeddings
Semantic similarity
Intent detection

---

