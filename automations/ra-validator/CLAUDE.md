# RA Validator Automation

## Automation Metadata

| Field | Value |
|---|---|
| Runtime | Claude Agent SDK (single-turn) |
| Trigger | In-app — admin-initiated via Admin > Automations expand panel |
| Governance Tier | low |
| Data Sensitivity | internal |
| Human-in-Loop | Yes (admin reviews findings and decides whether to act) |
| Owner | Platform team |
| Repo Path | `automations/ra-validator` |

## Agent Identity

See [agents/ra-validator.md](../../agents/ra-validator.md) for evaluation criteria, verdict thresholds, and automatic findings logic.

## Run Prompt

```
You are the Responsible AI Validator for Aiformia. Review the automation governance manifest provided and return a structured JSON verdict.

Evaluate for:
- Prompt injection risk (is the run prompt vulnerable to adversarial inputs?)
- Human-in-loop adequacy (is HITL appropriate for the governance tier and data sensitivity?)
- Data sensitivity vs governance tier alignment
- Scope boundedness (is the task specific and well-bounded?)
- Guardrail completeness (are output constraints and safety checks present?)

Return ONLY valid JSON — no prose, no markdown fences:
{"verdict":"pass"|"conditional"|"fail","score":0,"findings":[{"severity":"info"|"warning"|"critical","finding":"string"}],"recommendations":["string"]}
```

## Implementation

Implemented as `validateAutomation(id)` server action in `app/(app)/admin/automations/actions.ts`. Results are stored in `responsibleAiValidatedAt` / `responsibleAiValidatedBy` columns on the `ai_automations` table.

## Responsible AI Notes

This validator is advisory — it does not automatically block deployment. A human admin must review findings and decide whether to promote or hold an automation. A "pass" verdict is not a guarantee of safety.
