# Decision Log

Append-only. When a meaningful decision is made, log it here.

Format: [YYYY-MM-DD] DECISION: ... | REASONING: ... | CONTEXT: ...

---

[2026-04-23] DECISION: Remove local google-calendar MCP server, use claude.ai Google Calendar connector only | REASONING: Local MCP auth was broken, causing failed attempts + schema fallback to claude.ai connector on every session, burning tokens unnecessarily. claude.ai connector is stable and connected. | CONTEXT: Removed via `claude mcp remove google-calendar`. claude.ai connector (calendarmcp.googleapis.com) is now sole calendar integration.

[2026-04-23] DECISION: Build weekly task board (tasks/week.md) as primary task management layer | REASONING: today.md only covered the current day — no way to allocate tasks across the week without manual editing. New system: tasks allocated conversationally by day into week.md, daily-plan pulls today's section automatically, incomplete tasks carry forward. | CONTEXT: week.md covers Mon–Fri, archived weekly on Monday rollover to tasks/log/.

[2026-04-23] DECISION: Two-repo architecture — francoisOS + fimiliarOS | REASONING: francoisOS is Francois's personal assistant layer; fimiliarOS will be the business OS (processes, docs, team flows). francoisOS eventually sits on top of fimiliarOS. Other team members can build their own personal layers on top. | CONTEXT: Starting with francoisOS only. fimiliarOS built out as business processes are systematised. Goal is full business infrastructure living in one place, with personal assistants as the interface layer on top.

[2026-04-24] DECISION: Split Alex Brownstein's comment target audience into two segments — Ad industry ICP + AI influencers/voices | REASONING: Keeps Alex visible as an AI thought leader while staying relevant to his core commercial audience. Pure ICP commenting loses the AI positioning; pure AI commentary loses the sales signal. | CONTEXT: Applies to engagement list building and daily commenting workflow for Alex.

[2026-04-23] DECISION: Connect Google Calendar MCP (claude.ai connector) | REASONING: Enables daily-plan skill to pull live calendar events each morning, making time blocking context-aware without manual input. | CONTEXT: Connected via claude.ai Connectors. Calendar: francois@fimiliar.com, SAST timezone. Google Drive also available via same connector.

[2026-04-24] DECISION: Build engagement function as a business unit inside francoisOS under `projects/engagement/` | REASONING: Needs strategy, process, and per-client context in one place — not scattered. Skills drive daily execution by reading from these files. | CONTEXT: Pipeline: List → Approval → Connections → Intent Monitoring → Engagement → DMs. 14 active clients across individuals, Legion, FrontlineXP, and Fimiliar internal.

[2026-04-24] DECISION: Activity tracking in Excel (not francoisOS) for MVP | REASONING: Team requested Excel while learning the operation. francoisOS is the brain (strategy, context, process); Excel is the ledger (activity data). Strangler fig — migrate when patterns are understood. | CONTEXT: Applies to connection counts, comments done, DMs sent, etc. Client files hold no activity log for now.

[2026-04-24] DECISION: Design specs live at `projects/[workstream]/spec.md` | REASONING: Keeps design docs co-located with the project they describe. No separate docs folder needed. | CONTEXT: Established when moving engagement spec from `docs/superpowers/specs/` to `projects/engagement/spec.md`.

[2026-04-28] DECISION: Engagement project uses client-first directory structure — all client assets under `clients/[slug]/` | REASONING: Type-first structure (sources/, lists/, prospects/ at top level) fragmented context and made it hard to see everything for a given client in one place. | CONTEXT: Each slug maps to a company name. Multi-person accounts share sources/ and lists/ but split prospects/ by person.

[2026-04-28] DECISION: Client folder slugs use company name, not person name | REASONING: People move; company relationships persist. Prevents re-organisation when individuals change. | CONTEXT: Standardised across all 8 active client folders — ahb-advisors, trigger-eyeclone, vercel, inference-group, inference-chain, legion, frontlinexp, fimiliar.

[2026-04-28] DECISION: Clay list building split by industry × geography (or ABM for named accounts), not by persona | REASONING: Persona-split lists (HR, Finance, Ops) produce over-narrow filters that miss volume. Industry × geo keeps company filters broad; persona breadth is handled via multi-function job title filters within each list. | CONTEXT: Applied when rebuilding FrontlineXP (4 lists) and Legion/Andy (4 ABM lists). Rob Rooney's 4 lists follow his existing Sales Nav saved search structure.

[2026-04-29] DECISION: Comment strategy framework — 25 comments/week per profile (5/day), split 15 prospects / 7 influencers / 3 competitors | REASONING: 5/day is validated best practice (~15-20 mins); split reflects intent priority — prospects are the primary conversion path, influencers build ICP-adjacent visibility, competitors position the client's POV. Quality over volume — 2-4 sentences minimum, every comment adds something. | CONTEXT: Applied across all 14 client profiles. Per-client strategy files created at `clients/[slug]/[person]-strategy.md`.

[2026-04-29] DECISION: Warm-only outreach — DMs triggered by intent signals only, never cold | REASONING: Cold outreach breaks trust and brand. The comment engine builds name recognition first; DMs are the natural next step in an already-started relationship. Intent threshold: minimum 2-3 engagement touches AND at least one awareness signal (profile view, reply, or unprompted connection). | CONTEXT: Applies to all 14 client profiles. No DM without a signal. Per-client outreach strategy files to be built.

[2026-04-29] DECISION: Per-client engagement strategy files as the execution layer | REASONING: Engagement session skill was reading from profile files (ICP/voice) but lacked a concrete operating doc — what to comment on, who to target, which influencers, which competitors, what to avoid. Strategy files fill that gap without bloating the profile files. | CONTEXT: 14 strategy files created at `clients/[slug]/[person]-strategy.md`. Template at `projects/engagement/templates/engagement-strategy.md`.

[2026-04-29] DECISION: DM length tightened to under 60 words / under 300 characters (was: under 80 words) | REASONING: Data shows messages under 300 chars get 19% more replies. The old limit allowed bloated openers — this forces tighter, more conversational first DMs. | CONTEXT: Updated across all 14 outreach files and the outreach strategy template.

[2026-04-29] DECISION: Comments batched to 8-10am local time as default | REASONING: Early comments on fresh posts get more algorithm visibility and higher reply rates from post authors. Commenting throughout the day wastes visibility. | CONTEXT: Added to all 14 strategy files, engagement strategy template, and README.

[2026-04-29] DECISION: Post frequency (min 2-3x/week) added as a tracked dependency | REASONING: The entire engagement-to-DM pipeline depends on clients posting consistently. No posts = no engagers = no DM triggers. An unacknowledged dependency that could silently stall pipeline. | CONTEXT: Added to README as a rule — flag any client posting below threshold.

[2026-04-29] DECISION: Comment replies tracked separately as a quality metric | REASONING: A comment that generates a reply = 2x the intent signal of one that doesn't. Tracking only volume hides quality. Comment type + reply data is how the strategy improves over time. | CONTEXT: Added comment type and reply tracking to all 14 strategy files and engagement template.

[2026-04-29] DECISION: Signal monitoring will come through Fimiliar's own data system, not manual notification checking | REASONING: Manual monitoring of 14 profiles is unscalable. The data system will pre-surface intent signals before each /outreach session. | CONTEXT: /outreach skill will eventually read from surfaced signals rather than prompting manual checking — update the skill when the data system is ready.

[2026-04-29] DECISION: Voice/tone inputs for 7 clients default to working assumptions until inputs received | REASONING: Can't block execution on missing inputs — working assumptions are good enough to start. Quality improves incrementally as inputs come in. | CONTEXT: Rob Rooney, Andy Newberry, Matt Lovitt, Richard Davis, Ilan, Karl, Jono all have working assumptions in their strategy files. Update each file when real input is received.

[2026-04-30] DECISION: Profile views treated as standalone DM triggers for Ilan — casual "saw you checking out my profile" opener | REASONING: Strategy requires 2-3 prior engagement touches but Ilan's pipeline is just launching and needs volume moving. Profile view alone is sufficient signal to start a conversation if the person is in ICP. Casual opener is disarming and human — better reply rates than analytical openers. | CONTEXT: Two templates: Option A (simple curiosity) and Option B (return the favour + industry challenge question). Both documented in ilan-bernstein-outreach.md. Send while view is still recent.

[2026-04-30] DECISION: Session outputs tracked in per-client CSV files (comments + DMs) | REASONING: Comments and DMs drafted in session need client approval before sending. CSV format gives Ilan a clean, reviewable list with post links and draft text — easy to approve, edit, or skip per row. | CONTEXT: Two CSV types per client per session: `[client]-comments-[date].csv` and `[client]-profile-viewers-[date].csv`. Stored in `clients/[slug]/prospects/`.

[2026-04-30] DECISION: Alex's comment voice is context-dependent — analytical for data/market posts, playful/self-deprecating for personal/cultural posts | REASONING: Initial strategy file described a single analytical register. Live session revealed Alex's real comments are more varied — personal/cultural posts get a lighter, more human touch (e.g. McKinsey slide deck post: "betrayal?" framing). Data/market posts stay dry and analytical. | CONTEXT: Update alex-brownstein-strategy.md to reflect the two registers. Don't default to analytical for every post type.

---
