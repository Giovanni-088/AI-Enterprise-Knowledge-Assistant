# Google Drive Knowledge Source

## Objective

Integrate Google Drive as the centralized repository for internal enterprise documentation.

The assistant uses Google Drive as a knowledge source before generating responses with the AI model.

---

# Knowledge Base Structure

The documentation is organized by business area:


Enterprise Knowledge Base/

├── HR/

├── IT/

├── Operations/

└── Development/


This structure allows future filtering and categorization.

---

# Supported Documents

Current supported formats:

- PDF
- DOCX
- Markdown

---

# Authentication

Google Drive access is configured through n8n OAuth2 credentials.

Permissions:

- Read files
- Access knowledge base documents

The assistant does not modify documents.

---

# Retrieval Strategy

The system does not send all company documentation to the AI model.

Instead:

1. Receive user question.
2. Normalize query.
3. Generate keywords.
4. Search relevant documentation.
5. Retrieve only necessary context.

---

# Benefits

- Reduced token consumption
- Faster responses
- Less irrelevant context
- Better scalability

---

# Future Improvements

Possible production improvements:

- Semantic search
- Document embeddings
- Vector database
- Metadata filtering
