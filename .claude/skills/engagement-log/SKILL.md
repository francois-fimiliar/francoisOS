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
  1. Read `projects/engagement/clients/[slug]/[person].md` — ICP, voice, next actions
  2. Read `projects/engagement/clients/[slug]/[person]-strategy.md` — comment plan, influencer targets, competitor targets, topics, rules
  3. Surface for the session:
     - Comment split for today (prospects / influencers / competitors)
     - Which influencers and competitors to prioritise
     - What angle to comment from (based on voice and strategy)
     - Any specific next actions flagged in the profile file
  4. After session: ask if any notes, observations, or next actions to log back to the client file
  5. Update `[person].md` — `## Next actions` and `## Notes` if needed

### 4. Log reminder
Remind Francois to update Excel tracker with activity counts (connections, comments, etc.) for the session.

### 5. Done
Confirm session complete. Note any client files updated.
