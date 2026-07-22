# Document Processing

## Objective

Transform company documents into usable context for the LLM.

## Pipeline

Google Drive

↓

Metadata Validation

↓

File Filtering

↓

Deduplication

↓

Document Download

↓

Text Extraction

↓

Context Generation


## File Filtering

The workflow validates MIME types before processing.


Allowed:

- text/markdown
- text/plain
- application/pdf
- DOCX
- Google Docs


Rejected:

- folders
- spreadsheets
- unsupported files


## Deduplication

Duplicate documents are removed using the Google Drive file ID.


## Future Improvements

- OCR processing
- Document chunking
- Vector search
- Semantic ranking
