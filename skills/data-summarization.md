# Data Summarization Skill

Transforms structured datasets, reports, and tabular data into executive-ready narrative.

## Metadata

- **Category**: generation
- **Provider**: Anthropic (claude-sonnet-4-6)
- **Status**: active

## Capabilities

- Table-to-narrative conversion
- Period-over-period and team-over-team comparative analysis
- Trend identification with plain-language commentary
- Dashboard narrative for non-technical audiences
- Multi-section executive briefing generation

## Agents That Use This Skill

- Weekly Digest Agent
- Workflow Advisor

## Tone Configuration

Pass a tone modifier in the system prompt:

- `executive` — direct, data-forward, no fluff
- `narrative` — story-driven, suitable for all-hands communications
- `analytical` — includes methodology notes, data caveats

## Guardrails

- Label AI-generated summaries as such when shared externally
- Include data currency date (as-of date) in any financial or operational summary
- Do not invent numbers — if a metric is missing, state it explicitly
