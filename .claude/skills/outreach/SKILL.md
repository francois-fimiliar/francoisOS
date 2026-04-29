# Skill: outreach

Daily outreach session — guides Francois through sending DMs to warmed prospects for each active client.

## Trigger
User runs `/outreach` or asks to run outreach / do DMs.

## Steps

### 1. Load process context
Read `projects/engagement/README.md`. Note intent threshold, DM timing rules, and warm-only philosophy.

### 2. Select clients for session
Ask: "Which clients are we running outreach for today?" or proceed through full roster.

### 3. Per-client loop
For each client:
  1. Read `projects/engagement/clients/[slug]/[person].md` — ICP, voice, next actions
  2. Read `projects/engagement/clients/[slug]/[person]-outreach.md` — intent threshold, message framework, voice rules, no-go list
  3. Surface for the session:
     - Which prospects have crossed the intent threshold (signals fired)
     - The correct message angle based on the signal type
     - Any flagged prospects in the profile's next actions
  4. Draft DM(s) for Francois to review — reference the specific signal, one question, under 80 words, no pitch
  5. After session: ask if any notes, outcomes, or follow-up actions to log back to the client file
  6. Update `[person].md` — `## Next actions` and `## Notes` if needed

### 4. Log reminder
Remind Francois to update Excel tracker with DM counts for the session.

### 5. Done
Confirm session complete. Note any client files updated.
