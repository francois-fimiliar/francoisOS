# Skill: daily-plan

Run each morning to generate today's time-blocked plan.

## Trigger
User runs `/daily-plan` or asks to plan the day.

## Steps

### 1. Archive yesterday
If `tasks/today.md` exists and is dated before today, move it to `tasks/log/YYYY-MM-DD.md` (use the date in the file header).

### 2. Pull calendar events
Use Google Calendar MCP — calendar `francois@fimiliar.com`, SAST timezone.
Fetch all events for today from 00:00 to 23:59.

### 3. Determine day type
- Monday / Tuesday / Wednesday = office day → use `tasks/templates/office-day.md`
- Thursday / Friday = WFH day → use `tasks/templates/wfh-day.md`

### 4. Build the plan
- Replace `{{DATE}}` with today's date (e.g. `Thursday 23 April 2026`)
- Replace `{{CALENDAR_EVENTS}}` with today's events as a bulleted list (time + title). If none, write `None scheduled.`
- Insert calendar events as fixed blocks in the schedule table — push other blocks around them
- Pull the top priorities from `context/current-priorities.md` and populate Must do / Should do

### 5. Write `tasks/today.md`
Overwrite with the completed plan.

### 6. Present
Show the schedule table and Must do list. One sentence on the day's main focus.
