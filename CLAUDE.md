# Fimiliar Engagement OS

This is the operational system for Fimiliar's LinkedIn engagement and outreach function. It covers strategy, outreach, prospect tracking, and AI workflows for all active clients.

@context/work.md
@context/team.md
@context/current-priorities.md

## Structure
| Path | Purpose |
|------|---------|
| `projects/engagement/clients/` | One folder per client — strategy, outreach, prospects, lists |
| `references/` | SOPs and style guides |
| `context/` | Company and team context |
| `.claude/skills/` | AI workflows — run with /skill-name |
| `tasks/` | Task templates and logs |
| `decisions/` | Append-only decision log |
| `archives/` | Nothing deleted — moved here instead |

## Active Clients
| Client | Folder |
|--------|--------|
| Alex Brownstein | `clients/ahb-advisors/` |
| Ilan Bernstein | `clients/trigger-eyeclone/` |
| Oliviero Domenighini | `clients/inference-chain/` |
| Val Kalis | `clients/inference-chain/` |
| Richard Davis | `clients/inference-group/` |
| Jordan Chandler | `clients/vercel/` |
| Rob Rooney, Eoin Houlihan, Andy Newberry | `clients/legion/` |
| Rob Bate, Matt Lovitt | `clients/frontlinexp/` |
| Karl, Jono, Francois | `clients/fimiliar/` |

## Top Priority
Grow Fimiliar MRR to £50K. Floor: +£15K in 3 months. Everything should support this.

## Current Priorities & Goals
@context/current-priorities.md

## Per-Client File Structure
Each client folder contains:
- `[name]-strategy.md` — engagement and comment strategy
- `[name]-outreach.md` — DM and outreach strategy
- `profile.md` or `[name].md` — client profile
- `lists/` — prospect lists (CSV, built in Clay)
- `prospects/` — active prospect tracking
- `sources/` — onboarding docs and ICP research

## Skills
Custom skills live in `.claude/skills/`. Run them by typing the skill name in Claude Code.

**Live:**
- `/engagement-log` — daily commenting workflow per client
- `/outreach` — DM/outreach workflow per client
- `/daily-plan` — morning planning workflow
- `/audit` — full system health check
- `/list-build` — Clay filter list builder

## Rules
`.claude/rules/communication-style.md` — loaded automatically. Defines tone for internal (casual/direct) and external (professional/bright) communication.

## Decision Log
Log meaningful decisions in `decisions/log.md`. Append-only.
Format: `[YYYY-MM-DD] DECISION: ... | REASONING: ... | CONTEXT: ...`

## Task Management
- Templates: `tasks/templates/` (office-day, wfh-day)
- Log: `tasks/log/` (archived daily plans)

## Archive Rule
Don't delete — move to `archives/`.
