# Fimiliar Engagement OS — Handover Guide

*For: Karl Minnie, Jonathan Peters-Newman*
*From: Francois van Zyl*
*Date: 2026-05-01*

---

## What this is

This repo is the operational brain for Fimiliar's LinkedIn engagement and outreach function. Every active client has a folder containing their strategy, outreach framework, prospect lists, and tracking files. AI workflows (skills) automate the daily process.

---

## Getting started

### 1. Install Claude Code

Download and install the Claude Code CLI:
https://claude.ai/code

You will need an Anthropic account. Ask Francois for access if needed.

### 2. Clone the repo

```
git clone https://github.com/francois-fimiliar/francoisOS.git
cd francoisOS
```

### 3. Open Claude Code

```
claude
```

Claude will automatically read the repo context and load everything it needs.

### 4. First prompt — get oriented

Paste this to get a full briefing:

> "Read CLAUDE.md, context/work.md, context/team.md, and context/current-priorities.md. Then give me a complete overview of this repo — what it contains, how it's structured, which clients are active, and what the current priorities are."

---

## Folder structure

```
francoisOS/
├── HANDOVER.md                  ← you are here
├── CLAUDE.md                    ← repo instructions for the AI
├── context/                     ← company, team, and priority context
├── projects/
│   └── engagement/
│       ├── HANDOVER-TODO.md     ← full to-do list
│       ├── clients/             ← one folder per client
│       │   ├── ahb-advisors/    ← Alex Brownstein
│       │   ├── trigger-eyeclone/← Ilan Bernstein
│       │   ├── inference-chain/ ← Oliviero + Val
│       │   ├── inference-group/ ← Richard Davis
│       │   ├── vercel/          ← Jordan Chandler
│       │   ├── legion/          ← Rob Rooney, Eoin, Andy
│       │   ├── frontlinexp/     ← Rob Bate, Matt Lovitt
│       │   └── fimiliar/        ← Karl, Jono, Francois
│       └── templates/           ← strategy + outreach templates
├── references/                  ← SOPs and style guides
├── tasks/                       ← task templates and logs
├── decisions/                   ← append-only decision log
└── archives/                    ← nothing deleted, moved here
```

---

## Per-client file structure

Every client folder follows the same pattern:

| File | What it contains |
|------|-----------------|
| `[name]-strategy.md` | Comment strategy — who to target, voice, comment types, influencers, competitors |
| `[name]-outreach.md` | DM strategy — intent thresholds, message framework, voice rules |
| `profile.md` or `[name].md` | Client profile — ICP, background, next actions |
| `lists/` | Prospect lists built in Clay (CSV) |
| `prospects/` | Active prospect tracking — inbound connections, profile viewers, DMs |
| `sources/` | Onboarding docs and ICP research |

---

## AI skills (workflows)

Run these inside Claude Code by typing the skill name:

| Skill | What it does |
|-------|-------------|
| `/engagement-log` | Daily commenting workflow — pulls strategy per client, logs activity |
| `/outreach` | DM/outreach workflow — pulls outreach strategy per client |
| `/daily-plan` | Morning planning — builds the day's schedule |
| `/audit` | System health check — flags stale tasks, context drift, skill gaps |
| `/list-build` | Builds Clay filter criteria and ICP lists for a client |

---

## How to use the agent day-to-day

**Start a session:**
> "Read CLAUDE.md and give me a status on where things stand across all clients."

**Run engagement for a specific client:**
> "/engagement-log Alex Brownstein"

**Run outreach for a specific client:**
> "/outreach Jono"

**Check the to-do list:**
> "Pull up the handover to-do list and tell me what's outstanding."

**Update a client file:**
> "Update Alex Brownstein's outreach file to reflect that we've sent the Bloomberg connections."

---

## To-do list

Full task list by client: `projects/engagement/HANDOVER-TODO.md`

---

## Rules

- Communication style is defined in `.claude/rules/communication-style.md` — the AI loads this automatically.
- Don't delete files — move to `archives/` instead.
- Log meaningful decisions in `decisions/log.md`.

---

## Questions

Reach Francois on WhatsApp or Teams.
