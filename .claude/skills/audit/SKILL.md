---
name: audit
description: Use when the user asks to audit, review the system, check what's stale, clean up, or says anything like "what needs updating" or "what's out of date". Also trigger at session start when context freshness matters.
---

# Skill: audit

Run a full system health check. Scan all layers of the OS, surface anything stale or missing, and produce a clean action list.

## What to check

Work through each section below. Read the relevant files, apply the logic, and record your findings. Don't skip a section even if it seems fine — a clean bill of health is also useful.

### 1. Tasks

Read `tasks/today.md`:
- Is it dated today? If not: WARN — `/daily-plan` hasn't been run yet today

Read `tasks/week.md`:
- Find any sections for days before today that contain unchecked `[ ]` items
- If found: WARN — list the stale tasks and their day

Check `tasks/log/`:
- Note the most recently archived file date — this shows the last time `/daily-plan` ran and filed a plan

### 2. Context freshness

Read `context/current-priorities.md`:
- Find the "Last updated" date at the top
- If older than 14 days: WARN — priorities may be stale
- If older than 30 days: STALE — update needed

Read `context/goals.md`:
- Check if the quarter matches today's date. If we're in a new quarter and goals haven't been updated: WARN

Skim `context/me.md`, `context/work.md`, `context/team.md`:
- Look for anything obviously outdated: role changes, client list changes, team changes, location/commute changes
- Flag anything that seems mismatched with recent task content or decisions

### 3. Decision log

Read `decisions/log.md`:
- Find the most recent entry date
- If older than 14 days: WARN — check whether recent sessions included meaningful decisions that weren't logged
- If older than 30 days: STALE — decisions are not being logged regularly

### 4. Projects

List `projects/`:
- If completely empty: note it (this is expected early on — just flag that no workstreams have been formalised yet)
- For each project folder: check for a `README.md`. If missing: WARN
- For each README.md: note the last-modified date. If older than 30 days: WARN — may be stale

### 5. Skills

Read `CLAUDE.md` Skills section:
- Cross-reference **Live** list vs actual files in `.claude/skills/`
- If CLAUDE.md lists a skill as live but the directory doesn't exist: STALE — mismatch
- Check the **Urgent** and **Backlog** lists — flag items that have been there since system creation with no movement (compare against decisions/log.md or tasks for signals of progress)

### 6. References

Check `references/sops/`:
- If empty or only `.gitkeep`: WARN — no SOPs documented yet. Flag which recurring workflows are running without a documented SOP (cross-reference current-priorities.md)

Check `references/examples/`:
- If empty or only `.gitkeep`: note it (lower priority than SOPs)

### 7. Wishlist

Read `wishlist.md`:
- Flag any items that look immediately actionable given current priorities (compare against `context/current-priorities.md`)
- Flag any items that have been superseded by decisions already made (e.g. something was on the wishlist and then a decision was logged)

---

## Output format

Present the audit as a clean report. Use these status markers inline:

- `OK` — looks good, nothing needed
- `WARN` — needs attention soon
- `STALE` — overdue, action required

```
## francoisOS Audit — [DATE]

### Tasks
[one line per check, status marker + finding]

### Context
[one line per file checked]

### Decisions
[one line — last entry date + status]

### Projects
[one line per finding]

### Skills
[one line per finding]

### References
[one line per folder]

### Wishlist
[only flag items worth acting on — skip if nothing stands out]

---

### Action items
1. [highest priority action]
2. [next]
...
```

Keep each line tight. If a section is fully clean, one line: `OK — nothing to flag`. Don't pad. The action list at the bottom should be ordered by urgency — the most stale or highest-impact item goes first.

After presenting the report, ask: "Want me to handle any of these now?"
