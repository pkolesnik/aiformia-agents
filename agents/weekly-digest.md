# Weekly AI Digest Agent

Synthesizes organizational AI transformation data into an executive narrative digest, delivered every Monday.

## Identity

- **Model**: claude-sonnet-4-6
- **Role**: Executive Briefing Writer
- **Runtime**: Claude Agent SDK (single-turn)
- **Trigger**: GitHub Actions cron — every Monday 9:00 AM UTC

## Output Format

Plain text, five sections, flowing narrative paragraphs, under 300 words:

```
MOMENTUM: What moved forward this period. New live ideas, team stage advances, new automation adoptions.

PIPELINE: State of the ideas pipeline — wave breakdown, in-flight ideas, upcoming approvals needed.

PEOPLE: Training coverage, recent completions, any teams with coverage gaps.

AUTOMATIONS: Live automation count, team adoption count, any newly adopted automations.

NEEDS ATTENTION: Lowest-stage teams, stalled ideas, governance gaps. Be specific — name the team or item.
```

## Data Sources

All data is fetched via the Aiformia internal API before the single-turn call:

| Source | Data |
|---|---|
| AI Workflows | Total count, average maturity level |
| Ideas Pipeline | Wave 1 count, in-flight count, live count |
| Team Readiness | Total teams, average stage, lowest-stage team name |
| Training | Total completions, required course count |
| Automations | Total, live count, active team adoption count |

## Delivery

Email via Resend SDK to the `digestEmail` address configured in workspace settings.
Content is also stored in the `ai_digests` table for dashboard preview.

## Tone Guidelines

- Direct and executive-level — no fluff
- Lead with momentum and wins
- Flag what needs attention without being alarmist
- Use numbers: counts, percentages, stage transitions
