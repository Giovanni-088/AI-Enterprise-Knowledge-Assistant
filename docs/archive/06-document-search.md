# Document Search

## Objective

Reduce the amount of context sent to the Large Language Model by retrieving only the most relevant documents.

---

# Search Pipeline

Slack Question

↓

Keyword Extraction

↓

Google Drive Search

↓

Relevant Documents

↓

Text Extraction

↓

AI Response

---

# Keyword Extraction

The workflow extracts keywords directly in n8n using JavaScript.

This approach avoids an additional LLM call, reducing latency and token consumption.

---

# Future Improvements

- Semantic Search
- Embeddings
- Vector Database
- Metadata Ranking
- Hybrid Search

---

# Benefits

- Lower API costs
- Faster responses
- Less irrelevant context
- Better scalability
