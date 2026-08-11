---
name: pdf
description: Process and analyze PDF files, extract text, images, and metadata
tags: document, file-processing
---

# PDF Processing Skill

This skill provides comprehensive guidance for working with PDF files.

## When to Use This Skill

- User asks to read or extract content from a PDF file
- User needs to analyze PDF structure or metadata
- User wants to convert PDF to other formats
- User needs to search within PDF documents

## Step-by-Step Process

### 1. Check File Existence
Before processing, verify the PDF file exists:
```bash
ls -la path/to/file.pdf
```

### 2. Extract Text Content
Use appropriate tools to extract text:
- For simple text extraction: `pdftotext`
- For structured data: `pdfplumber` (Python)
- For OCR on scanned PDFs: `tesseract` + `pdf2image`

### 3. Analyze Structure
Identify:
- Page count
- Tables and their structure
- Images and embedded objects
- Metadata (author, creation date, etc.)

### 4. Handle Special Cases
- **Encrypted PDFs**: Ask user for password
- **Scanned PDFs**: Use OCR tools
- **Large PDFs**: Process in chunks to avoid memory issues
- **Complex layouts**: Use specialized parsers

## Best Practices

1. **Always validate** that the file is actually a PDF before processing
2. **Handle errors gracefully** - PDFs can be corrupted or malformed
3. **Preserve formatting** when extracting text from structured documents
4. **Respect privacy** - don't store or log sensitive content
5. **Provide summaries** for large documents instead of dumping all content

## Common Tools

- `pdftotext`: Simple text extraction
- `pdfinfo`: Get PDF metadata
- `qpdf`: PDF manipulation and repair
- `ghostscript`: Advanced PDF processing
- Python libraries: PyPDF2, pdfplumber, PyMuPDF

## Example Workflow

```
User: "Read the PDF at docs/report.pdf"

1. Verify file exists
2. Check if it's a valid PDF
3. Extract text content
4. Summarize or present the content based on user's needs
5. If the PDF is large, ask if they want specific sections
```

## Error Handling

- If PDF is encrypted: "This PDF requires a password. Please provide it."
- If file is not a PDF: "The file doesn't appear to be a valid PDF."
- If extraction fails: "Unable to extract content. The PDF might be scanned or corrupted."
