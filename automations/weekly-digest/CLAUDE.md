# Weekly AI Insights Digest

## Automation Metadata

| Field | Value |
|---|---|
| Runtime | Claude Agent SDK (single-turn) |
| Trigger | Schedule — every Monday 9:00 AM UTC via GitHub Actions |
| Governance Tier | low |
| Data Sensitivity | internal |
| Human-in-Loop | No (fully automated) |
| Owner | Platform team |
| Repo Path | `automations/weekly-digest` |

## GitHub Actions Workflow

```yaml
# .github/workflows/weekly-digest.yml
name: Weekly AI Digest
on:
  schedule:
    - cron: '0 9 * * 1'  # 9am UTC every Monday
  workflow_dispatch:       # allow manual trigger

jobs:
  digest:
    runs-on: ubuntu-latest
    steps:
      - name: Trigger digest
        run: |
          curl -X POST https://aiformia.vercel.app/api/agents/weekly-digest \
            -H "Authorization: Bearer ${{ secrets.DIGEST_SECRET }}" \
            -H "Content-Type: application/json"
```

## Run Prompt

```
You are the Aiformia Weekly AI Insights Digest agent.

Every Monday you synthesize AI transformation data from across the organization into a concise, narrative digest that a CEO or transformation leader can read in 90 seconds.

Tone: Direct, executive-level. No fluff. Lead with wins. Flag risks without alarm. Use numbers.

Output — plain text, five sections, 2-4 sentences each:

MOMENTUM: [New live ideas, team stage advances, new automation adoptions this period]

PIPELINE: [Wave breakdown, in-flight ideas, upcoming approvals needed]

PEOPLE: [Training coverage, recent completions, coverage gaps by team]

AUTOMATIONS: [Live count, team adoption count, newly adopted automations]

NEEDS ATTENTION: [Lowest-stage teams, stalled ideas, governance gaps — name specific teams/items]

Keep total under 300 words.
```

## Responsible AI Notes

This automation sends email to a configured recipient. Ensure the recipient has consented. Content is AI-generated — review before using in board-level communications. Email address should be audited quarterly.
