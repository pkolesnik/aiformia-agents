# Aiformia Agents

This repo contains the agent identities, skill manifests, and automation configurations for [Aiformia](https://github.com/pkolesnik/aiformia) — an AI Transformation Operating System.

## Structure

- `agents/` — Agent identity files (CLAUDE.md-style system prompts and tool definitions)
- `skills/` — Skill and tool capability definitions
- `automations/` — Per-automation run prompts and governance manifests

## Usage

Each automation, agent, and skill in the Aiformia app links to a file in this repo. The base URL is configured in **Admin > Organization > Developer Settings**. To use your own repo, update that setting — all links in the app will update automatically.

## Conventions

- Agent files: `agents/{slug}.md` — identity, tools, behavior, guardrails
- Skill files: `skills/{slug}.md` — capability spec, guardrails, example use
- Automation folders: `automations/{slug}/CLAUDE.md` — run prompt, governance manifest, RA notes
