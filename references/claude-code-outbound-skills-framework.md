# Claude Code Outbound Skills Framework

Source: LinkedIn post (author unspecified). Flagged as background reference for Fimiliar's outreach system build.

---

## Context

Built by a team that was 100% reliant on Clay for outbound. Used Claude Code skills to map and diversify their entire outbound process — giving the full team access without needing Clay expertise.

---

## The 10 Core Skills

| # | Skill | Function |
|---|-------|----------|
| 1 | ICP + Segmentation | Builds ICP matrices using firmographic, technographic, and account fit signals |
| 2 | Campaign Strategist | Recommends which outbound plays to run, including signals |
| 3 | Account Sourcing | Pulls ICP-matching accounts from multiple databases, deduped |
| 4 | Account Enrichment | Finds custom data points for every sourced company |
| 5 | Contact Sourcing | Finds decision-makers, champions, and users |
| 6 | Contact Enrichment | Waterfall enrichment for email and phone data |
| 7 | Lead Scoring | Scores accounts in 3 tiers to segment outreach |
| 8 | Copywriter | Writes email and LinkedIn sequences, personalized at scale |
| 9 | Campaign Launcher | Creates campaigns in sequencers and pushes leads in |
| 10 | Campaign Analysis | Pulls analytics from email and LinkedIn sequencers |

---

## MCP Stack Required

- **Apollo.io** — account and contact sourcing
- **AI Ark** — enrichment
- **Findymail** — email finding
- **BetterContact** — waterfall enrichment
- **HubSpot** — CRM
- **Instantly.ai** — email sequencer
- **HeyReach** — LinkedIn sequencer

---

## Relevance to Fimiliar

- Fimiliar currently uses Clay as the primary data/enrichment layer — same dependency risk
- The skill architecture maps cleanly to the outreach workflow already being built in francoisOS
- Skills 1–3 align with `/list-build`; skills 7–9 align with `/outreach`
- Campaign Launcher + Analysis (9–10) are not yet built — potential future skills
- HeyReach MCP is the key unlock for LinkedIn sequencer automation
