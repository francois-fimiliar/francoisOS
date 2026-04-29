# Engagement — Master Process

*Owner: Francois van Zyl*
*Last updated: 2026-04-28*

## The Pipeline

| Stage | Action | Cadence | Owner |
|-------|--------|---------|-------|
| 1. List build | Build target prospect list per client | Monthly | Francois |
| 2. Client approval | Share list with client for sign-off | Monthly (after list build) | Francois + Client |
| 3. Connections | Send connection requests to approved targets | Daily (max 200/week total across all clients) | Francois |
| 4. Intent monitoring | Track who's engaging with client posts, visiting profiles | Daily | Francois |
| 5. Engagement | Comment on / react to target content based on intent signals | Daily | Francois |
| 6. Outreach DMs | Send DMs to warmed prospects once threshold met | Daily | Francois |

## Framework Philosophy

- **Speed first.** Comments and DMs go out without per-piece approval once the framework is signed off. The framework is the approval gate — not individual outputs.
- **Scalable but human.** Each framework gives enough structure to be repeatable at volume, and enough breathing room to be genuinely custom every time. No copy-paste.
- **Explain the why.** Every engagement target should have a clear rationale — why this person, why now, what signal made them worth engaging. This keeps the activity intentional, not mechanical.
- **Two frameworks per client:** (1) commenting — for engaging with client audiences, competitors, and influencers; (2) DM outreach — for warmed prospects who've crossed the intent threshold.

## Rules & Limits

- **LinkedIn connection cap:** 200/week total across all clients. Distribute daily.
- **Comment volume:** 25/week per profile (5/day) — split 15 prospects / 7 influencers / 3 competitors
- **Comment quality:** 2-4 sentences minimum. Every comment must add a perspective, question, or example. No one-liners.
- **Comment timing:** Batch to 8-10am local time — early comments on fresh posts get more algorithm visibility and more replies from post authors.
- **Comment reply is the strongest signal:** A comment that generates a reply from the prospect = 2x the intent value of a comment that doesn't. Track this separately.
- **Warm prospect threshold:** Minimum 2-3 engagement touches AND at least one awareness signal (profile view, reply, or unprompted connection request)
- **Intent signals:** Profile view after interaction, reply to client's comment, comment on client's post, unprompted connection request, 2+ post likes in same week
- **DM rule:** Warm outreach only — no cold DMs. Ever. The comment engine creates the relationship; the DM makes it direct.
- **DM length:** Under 60 words / under 300 characters. Three sentences maximum for Message 1.
- **DM timing:** Signal threshold crossed → DM within 48 hours. Send between 8-10am or 2-4pm GMT for highest reply rates. Max 2 DMs per sequence without a reply.
- **Post frequency dependency:** Clients must post minimum 2-3x/week for the pipeline to function. No posts = no engagers = no DM triggers. Flag any client posting below this threshold.
- **Connection prioritisation:** Within the 200/week cap, prioritise prospects who have already received 2+ comments. Don't connect cold.

## Structure

Each client lives in `clients/<slug>/`:
- `<person>.md` — ICP, voice, strategy, target list, next actions
- `<person>-strategy.md` — engagement strategy: comment plan, influencer targets, competitor targets, topics, rules
- `influencers.md` — prioritised influencer list for the account
- `competitors.md` — competitor accounts to engage with
- `sources/` — raw ICP inputs (questionnaires, docs)
- `lists/<YYYY-MM-DD>/` — Clay filter criteria CSVs
- `prospects/<YYYY-MM-DD>/` — Clay output (enriched leads, ready for outreach)
- `templates/` — reusable strategy templates

Multi-person accounts (legion, frontlinexp, fimiliar) share `sources/`, `lists/`, `influencers.md`, and `competitors.md` but have individual profile and strategy files per person.

## Activity Tracking

All activity (connections sent, comments done, DMs sent) tracked in Excel.
Link: [ADD EXCEL TRACKER LINK]

## Client Roster

| Folder | People | Type | Status |
|--------|--------|------|--------|
| `ahb-advisors` | Alex Brownstein | Individual | Active |
| `trigger-eyeclone` | Ilan Brownstein | Individual | Active |
| `vercel` | Jordan Chandler | Individual | Active |
| `inference-group` | Richard Davis | Individual | Active |
| `inference-chain` | Oliviero Domenighini, Valentin Kalis | Company | Active |
| `legion` | Rob Rooney, Eoin Houlihan, Andy Newberry | Company | Active |
| `frontlinexp` | Rob Bate, Matt Lovitt | Company | Active |
| `fimiliar` | Karl Minnie, Jono Peters-Newman, Francois van Zyl | Internal | Active |

## Skills

| Skill | Trigger | What it does |
|-------|---------|--------------|
| `/list-build` | Monthly | Generates Clay filter criteria CSVs per client |
| `/engagement-log` | Daily | Guides commenting session per client |
| `/outreach` | Daily | Guides DM outreach session per client |

## Strategy Analysis

Deep-dive analysis of the engagement and outreach strategy — what the data says, honest gaps, industry/ICP-specific insights, and a structured experimentation framework.

`strategy-analysis.md` — last updated 2026-04-29

---

## Backlog — Scheduled Runs (not yet built)

These will become recurring automated runs once processes are defined:

| Run | What | Cadence |
|-----|------|---------|
| Engager scrape | Scrape current post engagers per client — filter for ICP match — add to prospect pipeline | TBD |
| Competitor scrape | Scrape competitors' followers/engagers per client — filter for ICP — add to connect queue | TBD |
| Influencer scrape | Scrape influencer followers/engagers per client — filter for ICP — add to connect queue | TBD |
