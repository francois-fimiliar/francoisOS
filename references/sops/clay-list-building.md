# SOP: Clay List Building

*Last updated: 2026-04-28*

## Overview

Two-phase process: Claude generates the filter criteria, Francois builds and exports in Clay.

**Output:** Exported CSV of ~500 targeted prospects per list, filed under the correct client in `projects/engagement/clients/`.

---

## Phase 1 — Generate Filter Criteria (Claude)

Run `/list-build [client name]` in Claude Code.

Claude reads the client's ICP from `projects/engagement/clients/[slug]/` and outputs one CSV per list. Each CSV uses the `Section / Filter Field / Value` format matching Clay's import structure.

Lists are split by industry × geography (or ABM for account-based campaigns). Typically 3–5 lists per client — no more than needed to cover the ICP cleanly.

Files are saved to: `projects/engagement/clients/[slug]/lists/[YYYY-MM-DD]/`

---

## Phase 2 — Build in Clay

### 2.1 Set up the table

1. Go to the **Connection List Building** section in Clay.
2. Copy the template: **Template Connection List LinkedIn Rank**.
   - The template contains ~17 columns (a mix of enrichment and formula columns).
3. If it's an ABM campaign, also copy the ABM target list table structure alongside it (included in the standard template).
4. Rename the table and all relevant fields before doing anything else.

### 2.2 Import target accounts (ABM only)

1. Import the target accounts CSV (e.g. `Target Accounts.csv`) into the ABM table's enriched account column.
2. Run enrichment to populate company data.
3. QA the enrichment results — see section 2.3 below.
4. Once QA'd, use the ABM account list as a lookup field in the people table to scope people-finding to those accounts only.

### 2.3 QA the ABM list

For each account, verify the enrichment pulled the correct company:

- Check: company name matches, biography/description looks right, headcount is in the expected range.
- If the match is wrong:
  1. Search for the company on LinkedIn.
  2. On the company's LinkedIn page, find the URL they have posted there — typically a regional recruitment or careers page link.
  3. Copy that URL and paste it into the company link field in Clay.
  4. Clay re-runs enrichment automatically and resolves to the correct company.

### 2.4 Apply people filters

In the people table, populate the following fields from the filter criteria CSV:

- **Job titles / positions** — copy from the Job Title section of the CSV
- **Location** — copy from the Location section of the CSV

Two filters are applied automatically to every table as standard (table-level filters, not columns):

- **Bio filter** — filters by keywords present in the person's LinkedIn bio
- **2026 mention filter** — filters for people who have been active on LinkedIn in 2026 (via a reaction or a comment)

### 2.5 Narrow the list

Target: **~500 people per list**, ideally fewer. Tighten filters until the list is specific and clean. Quality over volume.

### 2.6 Export

1. Click **Tools → Export**.
2. Hand the exported file to Claude with the client name and segment.
3. Claude renames the file per convention and files it:

**Naming convention:** `[Company] Person Source (Segment) DD:MM:YYYY.csv`

**Filed to:** `projects/engagement/clients/[slug]/prospects/[person]/[date]/`

---

## Quick Reference

| Step | Who | Tool |
|---|---|---|
| Generate filter criteria | Claude | `/list-build` |
| Build tables + import accounts | Francois | Clay |
| QA ABM enrichment | Francois | Clay + LinkedIn |
| Apply filters + narrow list | Francois | Clay |
| Export | Francois | Clay |
| Rename + file export | Claude | francoisOS |
