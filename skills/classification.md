---
id: classification
name: Classification Skill
category: classification
provider: Anthropic
status: active
---

# Classification Skill

Classifies text, documents, or records into predefined categories with confidence scores.

## Capabilities

- Multi-label classification across custom taxonomies
- Intent detection (support tickets, sales inquiries, escalations)
- Priority triage: urgency, impact, routing
- Sentiment and tone classification

## Guardrails

- Always return a confidence score alongside the classification
- Flag low-confidence results (< 0.7) for human review before acting
- Never classify protected characteristics without explicit governance approval
