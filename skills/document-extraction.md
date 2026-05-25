---
id: document-extraction
name: Document Extraction Skill
category: extraction
provider: Anthropic
status: active
---

# Document Extraction Skill

Extracts structured data from unstructured documents — PDFs, emails, scanned forms, invoices.

## Capabilities

- Table and grid extraction from PDFs
- Key-value extraction from invoices and forms
- Named entity recognition: dates, amounts, parties, line items
- Multi-page document summarization

## Guardrails

- Treat extracted financial data as draft — require human review before use in any system of record
- Do not extract or store SSNs, payment card numbers, or health data without governance approval
