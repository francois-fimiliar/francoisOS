# ColdIQ — Full Outbound Stack Inside Claude Code

Source: LinkedIn post + cheat sheet image by Alex Vacca & Monika Grycz, coldiq.com. Flagged as best-in-class reference for outbound rebuild.

---

## The 7-Step Workflow

### 1. Build the Company List
- Sources: Clay, Apollo.io, Sales Nav, AI Ark (70M+ database), Ocean.io (lookalike from paying customers)
- Claude Code handles 50k+ CSV rows natively

### 2. Score and Tier Accounts
- Run ICP criteria against raw CSV via lead-scoring skills
- Tier 1: manual outreach | Tier 2: multi-channel | Tier 3: email only

### 3. Layer Buying Signals
- **PredictLeads API**: hiring moves, tech stack changes, product launches, press
- **Trigify.io API**: comments, likes, competitor mentions, social signals

### 4. Find Decision-Makers
- Build search from ICP (title, seniority, department, geo)
- **LeadsFactory API**: pulls multiple decision-makers per company

### 5. Enrich and Validate Contacts
- Waterfall: Prospeo → CompanyEnrich → FullEnrich
- Clean risky emails before they hit sequencer

### 6. Generate Copy and Deploy
- Pull best-performing copy from Instantly.ai or lemlist via API
- Write custom angle based on signals, initiatives, and persona
- Batch 100–200 leads at a time to protect quality
- Create campaign, inject copy, upload leads, configure sending — all via API

### 7. Improve Every Next Campaign
- Analyze post-launch metrics
- Surface highest-performing segments
- Find lookalikes from top leads for next run
- Campaigns auto-improve like a retargeting pixel for outbound

---

## What Claude Code Automates (from cheat sheet)

| Automation | What it does |
|------------|-------------|
| ICP scoring at scale | Runs Python against raw CSV, outputs tiered account list — zero manual review |
| API chaining | Connects enrichment providers, sequencers, and CRMs without writing code |
| Copy generation | Pulls analytics from sequencer, identifies best-performing templates, injects context |
| Campaign creation | Creates campaign, adds copy, uploads leads, sets delivery settings — inside sequencer directly |
| Enrichment waterfall | Routes each contact through providers in sequence, stops when verified email found |
| Context memory | Stores leads, copy, campaign data, reply analytics — uses past performance to improve future campaigns |

---

## One-Time Setup

Four documents to create once:

| Doc | Purpose |
|-----|---------|
| `CLAUDE.md` | Master directives — scoring rules, tool preferences, workflow logic. Claude reads before every task. |
| API keys doc | Paste once — Claude reads the doc and handles connections |
| Copy frameworks doc | Best-performing templates — Claude picks the right one per campaign based on goal and audience |
| Scoring criteria doc | ICP filters in plain English — Claude runs Python against your CSV, zero guesswork |

---

## Full Tool Stack by Layer

| Layer | Tools |
|-------|-------|
| Signal (intent) | RB2B, PredictLeads, Trigify |
| Data — find | Apollo, Instantly Superbeam, Openmart, LeadsFactory, BuiltWith |
| Data — enrich | FullEnrich, CompanyEnrich, Prospeo |
| Data — validate | BounceBan |
| Action (sequencing) | Instantly, Lemlist |
| Automation (orchestrate) | Clay, n8n, Relevance AI |

---

## Relevance to Fimiliar

- Step 3 (buying signals via Trigify.io) maps directly to the comment-reply trigger pipeline — highest-leverage automation not yet built
- Step 6 (copy generation + campaign deploy via API) is the end state for `/outreach` — currently manual
- Step 7 (auto-improvement loop) is the long-term compounding layer — not in scope yet but worth designing toward
- ColdIQ worth following closely for implementation patterns
