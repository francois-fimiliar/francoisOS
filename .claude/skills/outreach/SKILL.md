# Skill: outreach

Daily outreach session — guides Francois through sending DMs to warmed prospects for each active client.

## Trigger
User runs `/outreach` or asks to run outreach / do DMs.

## Steps

### 1. Load process context
Read `projects/engagement/README.md`. Note warm prospect threshold and DM timing rules (check if defined — if still TBD, ask Francois what threshold to use for today).

### 2. Select clients for session
Ask: "Which clients are we running outreach for today?" or proceed through full roster.

### 3. Per-client loop
For each client:
  1. Read `projects/engagement/clients/[client].md`
  2. Surface: ICP, voice/style, strategy, and next actions
  3. Prompt Francois with outreach focus for this client:
     - Who qualifies as a warmed prospect (based on threshold / intent signals)
     - Suggested DM angle (based on voice/style and strategy)
     - Any flagged prospects in next actions
  4. After session: ask if any notes, outcomes, or next actions to log back to the client file
  5. Update client file `## Next actions` and `## Notes` if needed

### 4. Log reminder
Remind Francois to update Excel tracker with DM counts for the session.

### 5. Done
Confirm session complete. Note any client files updated.
