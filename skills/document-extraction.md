# Document Extraction Skill

Extracts structured data from unstructured documents — PDFs, emails, scanned forms, invoices.

## Metadata

- **Category**: extraction
- **Provider**: Anthropic (claude-sonnet-4-6)
- **Status**: active

## Capabilities

- Table and grid extraction from PDFs
- Key-value extraction from invoices and forms
- Named entity recognition: dates, amounts, parties, line items
- Multi-page document summarization
- Handwritten form interpretation (via vision)

## Output Format

Returns structured JSON matching a caller-provided schema. Example:

```json
{
  "invoice_number": "INV-2024-0042",
  "vendor": "Acme Corp",
  "total_amount": 14750.00,
  "line_items": [
    { "description": "Consulting services", "amount": 12500.00 }
  ]
}
```

## Guardrails

- Treat extracted financial data as draft — require human review before use in any system of record
- Do not extract or store Social Security Numbers, payment card numbers, or health data without explicit governance approval
- Flag low-confidence extractions (ambiguous handwriting, poor scan quality) for human review
