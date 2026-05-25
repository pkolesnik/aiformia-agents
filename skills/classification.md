# Classification Skill

Classifies text, documents, or records into predefined categories with confidence scores.

## Metadata

- **Category**: classification
- **Provider**: Anthropic (claude-haiku-4-5 for volume; claude-sonnet-4-6 for nuance)
- **Status**: active

## Capabilities

- Multi-label classification across custom taxonomies
- Intent detection (support tickets, sales inquiries, escalations)
- Priority triage: urgency, impact, routing
- Sentiment and tone classification
- Binary and multi-class with confidence scoring

## Model Selection

| Scenario | Model |
|---|---|
| High-volume, low-latency (>100/min) | claude-haiku-4-5 |
| Nuanced categories requiring reasoning | claude-sonnet-4-6 |
| Sensitive classifications (HR, legal) | claude-sonnet-4-6 + human review |

## Guardrails

- Always return a confidence score alongside the classification
- Flag low-confidence results (< 0.7) for human review before acting
- Never classify protected characteristics (race, religion, gender, health status) unless legally required and approved by legal/compliance
