---
name: daily-plan
description: Use when the user runs /daily-plan, asks to plan the day, start the morning, or generate today's schedule and time blocks.
---

# Skill: daily-plan

Run each morning to generate today's time-blocked plan.

## Trigger
User runs `/daily-plan` or asks to plan the day.

## Steps

### 1. Archive yesterday
If `tasks/today.md` exists and is dated before today:
- Move it to `tasks/log/YYYY-MM-DD.md` (use the date in the file header)
- Check `tasks/week.md` for yesterday's section — any unchecked `[ ]` items carry forward into today's section in week.md

### 2. Pull calendar events
Use Google Calendar MCP — calendar `francois@fimiliar.com`, SAST timezone.
Fetch all events for today from 00:00 to 23:59.

### 3. Determine day type
- Monday / Tuesday / Wednesday = office day → use `tasks/templates/office-day.md`
- Thursday / Friday = WFH day → use `tasks/templates/wfh-day.md`

### 4. Pull today's tasks from week.md
Read `tasks/week.md`. Find today's section. These tasks are the primary Must do list.
If no section exists for today, fall back to `context/current-priorities.md`.

### 5. Build the plan
- Replace `{{DATE}}` with today's date (e.g. `Thursday 23 April 2026`)
- Replace `{{CALENDAR_EVENTS}}` with today's events as a bulleted list (time + title). If none, write `None scheduled.`
- Insert calendar events as fixed blocks in the schedule table — push other blocks around them
- Must do = today's tasks from week.md (carried items first, then new)
- Should do = supporting tasks from current-priorities.md if relevant

### 6. Write `tasks/today.md`
Overwrite with the completed plan.

### 7. Context check
Quickly scan `context/current-priorities.md` and `decisions/log.md`. If anything looks stale or a recent decision wasn't logged, flag it in one line before presenting the plan. Keep it short — one line max, only if genuinely needed.

### 8. Present
Show the schedule table and Must do list. One sentence on the day's main focus.

---

## Weekly rollover
When the new week starts (first `/daily-plan` on a Monday):
- Archive the previous week.md to `tasks/log/week-YYYY-MM-DD.md` (use the Monday date)
- Create a fresh `tasks/week.md` for the new week (Mon–Fri, blank sections)
