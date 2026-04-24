# Skill: engagement-log

Daily engagement session — guides Francois through commenting and profile engagement for each active client.

## Trigger
User runs `/engagement-log` or asks to run engagement / do comments.

## Steps

### 1. Load process context
Read `projects/engagement/README.md`. Note pipeline rules and any active thresholds.

### 2. Select clients for session
Ask: "Which clients are we running engagement for today?" or if all clients, proceed through full roster.

### 3. Per-client loop
For each client:
  1. Read `projects/engagement/clients/[client].md`
  2. Surface: ICP, voice/style, strategy, and next actions
  3. Prompt Francois with what to focus on for this client's session:
     - Who to engage with (based on ICP and target list)
     - What angle to comment from (based on voice/style)
     - Any specific next actions flagged in the file
  4. After session: ask if any notes, observations, or next actions to log back to the client file
  5. Update client file `## Next actions` and `## Notes` if needed

### 4. Log reminder
Remind Francois to update Excel tracker with activity counts (connections, comments, etc.) for the session.

### 5. Done
Confirm session complete. Note any client files updated.
