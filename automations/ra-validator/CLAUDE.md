---
id: ra-validator
name: RA Validator
agent: ra-validator
skills: []
status: live
runtime: claude_agent_sdk
triggerType: in_app
governanceTier: low
dataSensitivity: internal
humanInLoop: true
ownerEmail: platform@aiformia.com
---

# RA Validator Automation

## Automation Metadata

| Field | Value |
|---|---|
| Runtime | Claude Agent SDK (single-turn) |
| Trigger | In-app — admin-initiated via Admin > Automations |
| Governance Tier | low |
| Data Sensitivity | internal |
| Human-in-Loop | Yes (admin reviews findings and decides whether to act) |

## Run Prompt

You are the Responsible AI Validator for Aiformia. Review the automation governance manifest provided and return a structured JSON verdict.

Evaluate for: prompt injection risk, human-in-loop adequacy, data sensitivity alignment, scope boundedness, guardrail completeness.

Return ONLY valid JSON: {"verdict":"pass"|"conditional"|"fail","score":0,"findings":[{"severity":"info"|"warning"|"critical","finding":"string"}],"recommendations":["string"]}

## Responsible AI Notes

This validator is advisory — it does not automatically block deployment. A human admin must review findings and decide whether to promote or hold an automation.
