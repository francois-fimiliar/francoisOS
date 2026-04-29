# Engagement & Outreach Strategy — Deep Dive Analysis

*Written: 2026-04-29*
*Owner: Francois van Zyl*

---

## The Short Answer

The strategy is directionally right. Warm-only outreach, comment-first relationship building, and per-client specificity are all supported by data and will outperform standard practice. The risks aren't in the philosophy — they're in execution gaps that will quietly kill results if not addressed: no attribution loop, no post content dependency acknowledged, volume that doesn't scale to one person, and voice/tone inputs missing for more than half the roster.

The biggest lever no one talks about: **the comment that gets a reply is worth 10x the comment that doesn't.** Every optimisation decision flows from that.

---

## What the Data Actually Says

### Warm outreach vs cold
- Trigger-based outreach (sent within 48hrs of a signal) gets 25-35% reply rates vs 1-5% for cold
- Personalisation boosts replies 32% over templates — but only when it references exactly what the person said, not just inserts their name
- Messages under 300 characters get 19% more responses than longer messages
- Tuesday 8-10am and 2-4pm GMT are peak response windows — the DM inbox is checked more

**Implication:** The warm-only philosophy is correct. The DM length rule is too loose — current standard is <80 words (~400-500 chars). Should be <60 words / <300 chars, especially Message 1.

### Comment strategy
- Value-add comments (2-4 sentences with a specific angle) outperform one-liners on engagement rate
- Being an early commenter on a post (first 30-60 min after publishing) gets significantly more visibility as LinkedIn's algorithm surfaces early comments
- Comments that generate a reply from the post author = 2x the intent signal of a comment that doesn't
- Consistent presence under the same influencers over 8-12 weeks builds recognition before you've ever DMed anyone

**Implication:** The 2-4 sentence minimum is right. But there's no timing component in the strategy. Early commenting windows matter.

### Post content as the flywheel
- LinkedIn personal profiles generate 8x more organic reach than company pages
- Carousels/document posts get 11.2x more impressions than text-only posts
- Posts between 1,242-2,500 characters perform 32% better than shorter ones
- Consistency of posting schedule outperforms posting quality as a reach driver

**Implication:** The entire comment strategy assumes clients are posting regularly. If they're not, there are no engagers to scrape, no comment replies to trigger DMs, and the whole pipeline stalls. Post frequency is a dependency the current strategy doesn't track or enforce.

---

## Current Strategy — Honest Assessment

### What's strong

**Warm-only philosophy.** This is the most important decision and it's correct. Cold outreach on LinkedIn is broken. Warm trigger-based DMs convert at 10-20x the rate. The intent threshold table is a good framework — especially the reply-to-comment signal being ranked "very high."

**Per-client specificity.** The strategy files are genuinely different per client. Alex's McKinsey-style analytical voice, Rob Rooney's FM operational depth, Rob Bate's enterprise retail/hospitality WFM angle — these aren't swapped templates. That depth is a real competitive advantage if the execution matches it.

**15/7/3 comment split logic.** Prospect commenting for direct visibility, influencer commenting for audience discovery, competitor commenting for positioning — this three-track approach is right. Most agencies only do prospect commenting.

**Intent signal hierarchy.** The ranking (reply to comment > comment on post > unprompted connection > profile view > 2+ likes) maps to actual conversion probability. Reply to comment is the strongest signal because it requires effort from the prospect.

### What's weak or risky

**Volume isn't sustainable for one person at current scope.**

25 comments/week × 14 profiles = 350 comments/week. That's 70/day. At 3-5 minutes per comment (find post, read, write, post) = 3.5-6 hours/day on comments alone, before DMs, client check-ins, reporting, or anything else. This will either compress into low-quality mechanical comments or break entirely within 2-3 weeks.

The honest options: reduce profiles in scope, reduce daily cadence per profile, or hire someone to execute under the framework.

**Attribution is broken from day 1.**

The Excel tracker exists but has no link, no enrichment loop, and no mechanism to close the loop between "person replied to my comment" → "enriched prospect" → "booked call" → "deal." Without this, you can't measure what's working, you can't justify the effort to clients, and you can't improve the strategy with real data.

Clay is in the toolkit but it's only connected to the list-build step. The pipeline should flow: comment reply → enrichment in Clay → intent score → routed to DM queue. That routing step doesn't exist yet.

**Post content is a dependency, not a given.**

For the DM strategy to work, clients need to be getting comment replies on their posts — because the highest-value DM triggers are "replied to your comment" and "commented on your post." If a client isn't posting consistently, there are no incoming engagers to monitor and no trigger signals to act on. The strategy should define a minimum post frequency threshold per client, and flag when a client drops below it.

**Voice/tone missing for 8 of 14 profiles.**

Rob Rooney, Andy Newberry, Matt Lovitt, Richard Davis, Ilan, Karl, Jono — all running on working assumptions. A comment that sounds wrong for the person is worse than no comment: it's visible to hundreds of people including prospects. Getting these inputs is not optional, it's urgent.

**The 48hr DM window requires daily monitoring with no tooling.**

Crossing the intent threshold → DM within 48 hours. With 14 profiles, that means monitoring 14 sets of post engagers, profile views, and connection requests daily. There's no automation for this — it all relies on Francois manually checking. This will be the first thing that slips when volume gets high.

**Connection cap not integrated into the comment strategy.**

200 connections/week total. 14 profiles × 15 prospect comments = 210 comment targets per week. Not everyone who gets a comment needs a connection request, but there's no rule for when to connect vs when to just comment. Without that decision, either connection requests are sent too aggressively (LinkedIn shadow-limits accounts) or not systematically enough (warm pipeline doesn't grow).

---

## By Industry & ICP — What Actually Works

### Ad-tech / media consulting (Alex Brownstein)

The senior ad-tech LinkedIn community is small and interconnected — probably 200-300 real decision-makers in Alex's ICP who are active. In tight communities, consistent high-quality presence matters more than volume. Being wrong once in a comment section in front of Ari Paparo costs more than being silent.

**Specific insight:** Alex's Marketecture contributor status is an underused asset. Adtech people who engage with Marketecture content are pre-qualified to a very high degree. Those comment sections should be a daily priority, not just "High" on a list.

**What works for this ICP:** Analytical specificity with sourced numbers. This audience reads everything. Generic engagement won't build relationships — only comments that add real analytical value will get noticed. One excellent comment per week under Shelly Palmer or Josh Bersin is worth more than five mediocre ones.

### Enterprise FM SaaS (Legion — Rob Rooney)

FM is genuinely underserved on LinkedIn. There are far fewer people competing for attention in IWFM and FMJ comment sections compared to, say, HR or fintech. This is an advantage: being a consistent, knowledgeable voice in a small niche creates reputation faster than in a crowded space.

**Specific insight:** The ROI story (agency worker cost reduction, demand forecasting) resonates hardest at budget time — Q3/Q4 for most FM operators is when contracts renew. Timing comment intensity around procurement cycles would increase conversion. Track contract renewal signals in LinkedIn posts.

**What works for this ICP:** Operational specificity. FM COOs have a very precise problem (unpredictable demand, expensive agency workers, TUPE complexity). Comments that name the exact problem get replies. Generic WFM commentary is ignored.

### Enterprise hospitality/retail WFM (Legion — Andy Newberry)

Hospitality and retail operations leaders are active on LinkedIn, especially post-COVID, and especially around labour/workforce topics. But they respond to outcome-first messaging more than technical depth. They're not buying WFM software because it's technically elegant — they're buying it because they can't fill Christmas rotas.

**What works for this ICP:** Concrete outcome examples. "Saved 18% on agency spend at a multi-site retailer" opens conversations. Abstract WFM capability descriptions don't.

### B2B SaaS GTM (FrontlineXP — Rob Bate, Matt Lovitt)

Enterprise retail/hospitality buyers reading FrontlineXP-adjacent content (Josh Bersin, customer experience trade accounts) are sophisticated buyers who've seen a lot of sales approaches. They respond to peer-to-peer credibility. Rob Bate's independent cross-platform WFM angle is a genuine differentiator — lean into the independence, not the product.

### Individual consultants (Richard Davis, Oliviero, Val)

These profiles have a different primary goal: building intellectual reputation that attracts inbound. For consultants, a comment that gets you quoted, referenced, or followed by a respected voice is a better outcome than a DM reply. The comment strategy should optimise for being the most cited perspective in a given topic thread, not just being visible.

### Developer-adjacent (Jordan Chandler — Vercel)

Senior eng and CTO profiles on LinkedIn have a very high threshold for authentic engagement. They respond to genuine technical curiosity and will immediately dismiss anything that reads like marketing. The comment strategy here should be technically substantive or not run at all.

---

## The Attribution Problem — What to Build

Without attribution, the strategy is unfalsifiable. You can't tell if it's working, which parts are working, or why.

**Minimum viable attribution loop:**

1. When a comment generates a reply, log it (comment target, reply type, date) in the Excel tracker with a "signal" flag
2. When a reply → DM sent, log the signal that triggered it and the DM angle used
3. When a DM gets a reply, log the reply rate and which angle worked
4. When a DM conversation converts to a call, log the full path: first comment → signal → DM angle → call

This doesn't require new tools — it's an additional tab in the existing Excel tracker. But it needs to be built now, before data is lost.

**What Clay enables (once the loop is built):**

Enrichment of comment engagers → firmographic scoring → prioritise top-fit prospects for DMs. This is the highest-leverage automation in the stack and it's not yet wired in. Once it is, the comment-to-DM pipeline becomes systematic rather than manual.

---

## Experimentation Framework

Run experiments on the most uncertain assumptions. Don't experiment on your highest-value clients first.

**Current untested assumptions:**
- 5/day is the right comment volume
- <80 words is the right DM length
- Tuesday/Thursday peak windows apply to all ICPs
- Reply-to-comment is the primary conversion trigger (vs profile view, vs unprompted connection)
- 15/7/3 split is optimal (vs e.g. 18/5/2 or 20/5/0)

**Experiment protocol:**

| Step | Rule |
|------|------|
| One variable per experiment | Never change two things at once — you can't isolate what caused the result |
| Minimum 4 weeks per test | Shorter tests produce noise. LinkedIn reach fluctuates week to week |
| Baseline before you start | Log current DM reply rate, comment reply rate, connection acceptance rate before any change |
| Test on mid-value clients | Don't run new experiments on Alex or Rob Bate first — run them on clients where variation has lower risk |
| Log outcome against signal | For DM experiments, log which signal triggered each DM and which angle got a reply |

**Experiments to run, in priority order:**

**Experiment 1 — DM length (start immediately)**
- Current: <80 words (~400-500 chars)
- Test: <60 words / <300 chars — three sentences maximum
- Hypothesis: shorter DMs get more replies because they're less committal for the recipient
- Success metric: reply rate improvement after 20 DMs at each length
- Client: Alex Brownstein (high signal volume, clear ICP)

**Experiment 2 — Comment timing (week 2)**
- Current: comments are sent throughout the day
- Test: batch all comments to 8-10am (GMT+2) window when post is still fresh
- Hypothesis: early comments on fresh posts get more visibility from the algorithm and more replies from the author
- Success metric: comment reply rate before/after
- Client: Rob Bate (FrontlineXP — posts regularly at consistent times)

**Experiment 3 — Comment type mix (week 5)**
- Current: rotate across 5 types (insight add, experience bridge, contrarian, question, amplify)
- Test: increase contrarian comments to 40% of total (currently rotated equally)
- Hypothesis: contrarian comments generate more replies than amplifying comments because they invite a response
- Success metric: comment reply rate by type — need to tag type in Excel tracker first

**Experiment 4 — Influencer strategy depth vs volume (week 9)**
- Current: 7 influencer comments/week spread across 6-8 influencers
- Test: 7 influencer comments/week concentrated on 2-3 influencers (more consistent presence per person)
- Hypothesis: recognition builds faster with concentrated presence
- Success metric: do the same-influencer audience members start engaging with client posts over time? (Hard to measure — use 12-week horizon)

---

## Priority Actions (in order)

1. **Tighten DM length to <60 words / <300 chars.** Update all outreach files. Run the Alex experiment first.

2. **Build attribution tab in Excel tracker.** Log: signal type → DM angle → reply (Y/N) → conversation opened (Y/N) → call booked (Y/N). Start immediately so data isn't lost.

3. **Get voice/tone inputs from 7 remaining clients.** This is a risk to delivery quality. Define a deadline for each client — if not received within 2 weeks, use working assumption with explicit client sign-off.

4. **Define comment timing window.** Add to README and strategy files: batch comments between 8-10am local time. LinkedIn's algorithm favours early engagement.

5. **Add post frequency tracking to client files.** Define minimum: 2-3 posts/week per client. Flag when a client goes quiet — the DM pipeline stalls without posts generating engagers.

6. **Define connection request prioritisation rule.** Within the 200/week cap: connection requests should go to prospects who have already received 2+ comments from the client, not to cold discovery contacts.

7. **Wire Clay into the post-comment pipeline.** Once comment replies are being tracked, route those contacts through Clay for enrichment and firmographic scoring before they reach the DM queue. This is the highest-leverage automation in the stack.

8. **Manage scope vs volume realistically.** 350 comments/week for one person is not sustainable at quality. The right call is: prioritise the highest-value 6-8 profiles for full execution, and run a lighter (2-3/day) cadence on the rest until there's capacity to hire.

---

## What This Strategy Gets Right That Most Agencies Miss

1. **The DM is not the intro — it's the conversion.** Most agencies start with outreach. This strategy builds the relationship first through consistent commenting, then DMs when the signal is clear. That sequencing is why warm DM rates (25-35%) exist vs cold (1-5%).

2. **Per-person voice differentiation.** Generic comment templates are immediately visible to anyone in a tight professional niche. Alex's analytical precision is different from Rob Bate's enterprise practitioner voice, which is different from Jordan Chandler's technical authenticity. This is built in — it needs to be protected as you scale.

3. **Competitor commenting as positioning.** Commenting on competitors' content is underused. It puts the client's POV in front of the competitor's ICP audience — people who are already in the buying mindset for that category. The differentiation angle (Legion's FM-specific depth vs UKG's broad WFM) is precisely what belongs in those comment sections.
