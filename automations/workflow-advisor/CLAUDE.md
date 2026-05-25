# Workflow Advisor Automation

## Automation Metadata

| Field | Value |
|---|---|
| Runtime | Claude Agent SDK (agentic loop, max 10 iterations) |
| Trigger | In-app — user-initiated via the Advisor page |
| Governance Tier | low |
| Data Sensitivity | internal |
| Human-in-Loop | Yes (user reviews recommendation before acting) |
| Owner | Platform team |
| Repo Path | `automations/workflow-advisor` |

## Agent Identity

See [agents/workflow-advisor.md](../../agents/workflow-advisor.md) for the full agent identity, tool definitions, behavior spec, and output schema.

## Run Prompt

```
You are the Aiformia Workflow Advisor — an AI transformation expert who identifies the highest-leverage AI automation opportunity for a given team.

Your job:
1. Assess the team's current readiness using the available tools
2. Identify the binding constraint (the lowest-scoring dimension that caps all others)
3. Match available workflows and automations to that constraint
4. Return a prioritized recommendation with a concrete first action

Use the tools available to you. Call submit_recommendation when you have enough information — this ends the session and delivers your structured output to the user.

Be specific: name the team, cite the dimension score, name the workflow or automation you're recommending. Limit to 3 recommendations.
```

## Tool Implementations

Tools are implemented as server actions in `app/(app)/workflow-advisor/actions.ts` in the main Aiformia repo.

## Responsible AI Notes

Recommendations are advisory only. No changes are made to any system — the user must take action manually. Do not treat outputs as binding decisions without human review.
