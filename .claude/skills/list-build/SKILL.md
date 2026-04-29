---
name: list-build
description: Use when building Clay target lists for a client — generates ICP filtering criteria, an industry fit prompt, and 10 downloadable Clay filter CSVs split by the client's specific industry verticals.
---

# List Build

Generates Clay-ready filter lists for a client based on their ICP sources.

## Inputs Required
- Client name (to locate their sources)

## Step 1 — Load Client ICP

Read all source files for the client from `projects/engagement/clients/<client>/sources/`. Also check `projects/engagement/clients/<client>/profile.md` (or `<person>.md` for multi-person accounts) for the full ICP summary and any Sales Nav saved searches already built.

## Step 2 — Complete ICP Filtering

Answer every field below using only the client's ICP sources. Be specific — no vague defaults.

### Company Filters
| Field | Values |
|---|---|
| Location | Countries / regions to include |
| Company size | Headcount range(s) |
| Employee count | Min–Max (or tiers if multiple ICPs) |
| Estimated revenue | Annual revenue range(s) |
| Industry — Include | All matching LinkedIn industry labels |
| Industry — Exclude | Industries that are definitively not a fit |
| Keywords — Include | Description/keyword signals that indicate fit |
| Keywords — Exclude | Signals that disqualify (e.g. "staffing agency", "tax filing", "franchise") |
| Technologies used | Tools in their stack relevant to the offer |
| Funding history | Funded / raising / bootstrapped preference |
| Job postings | Roles being hired for that signal buying intent |

### People Filters
| Field | Values |
|---|---|
| Location | Match company geography |
| Job titles — Include | Exact and similar titles (decision makers) |
| Job titles — Exclude | Titles that are definitely not buyers |
| Seniority | Owner / Partner / CXO / VP / Director |
| Job function | Finance / Operations / General Management / Entrepreneurship etc. |
| Months in role | Min months in current role (usually 6+) |
| Number of experiences | Min (usually 2+) |
| Bio keywords | Words in headline / about / bio that signal fit |

## Step 3 — Industry Fit Prompt

Generate a yes/no prompt for evaluating whether a company belongs to one of this client's target industries. The prompt must:
- Accept: Company Name, Company Domain, Company Description as inputs
- Output: **Yes** or **No** only
- Apply: if unsure, default to Yes
- Cover: every target industry from the client's ICP, written broadly enough to catch variants (e.g. "Financial Services" catches "Investment Banking", "Private Equity", "Corporate Finance")

```
You are a B2B researcher evaluating whether a company fits within any of the following target industries:

[LIST ALL CLIENT TARGET INDUSTRIES — be exhaustive, include variants]

INPUT:
Company Name: {{company_name}}
Company Domain: {{company_domain}}
Company Description: {{company_description}}

Does this company belong to any of the industries listed above?

RULES:
- Answer Yes or No only.
- If unsure, answer Yes.
- Base your answer on the company's primary business, not its customers.

OUTPUT:
Yes or No
```

## Step 4 — Define the 10 Campaign Splits

Before generating CSVs, plan the 10 splits. Divide the client's target industries across 10 lists so each list is a coherent, targetable segment. Rules:
- No list should be too broad to be useful or too narrow to produce volume
- Larger/higher-priority industry clusters get their own list; smaller ones get grouped
- The same people/experience/location/bio filters apply to all 10 lists — only the company industry and keyword filters change per list
- Show the plan and get confirmation before generating CSVs

Example split structure (adapt to client):
```
List 1: [Primary industry cluster A]
List 2: [Primary industry cluster B]
List 3: [Secondary cluster A + B]
...
List 10: [Catch-all or lowest-priority vertical]
```

## Step 5 — Generate 10 Clay Filter CSVs

For each list, output a CSV with exactly three columns: `Section`, `Filter Field`, `Value`.

Sections to include in every list:
- **Company Attributes** — Industry Include/Exclude, Description Keyword Include/Exclude
- **Job Title** — Seniority, Job Function, Job Title Include/Exclude
- **Experience** — Months in Current Role Min, Number of Experiences Min, Experience Description Keywords
- **Location** — Country Include, Region Include/Exclude, State/City Include (if applicable)
- **Professional Bio** — Bio Keywords, Headline Keywords, About Section Keywords

### CSV format
```csv
"Section","Filter Field","Value"
"Company Attributes","Industry — Include","Financial Services"
"Company Attributes","Industry — Exclude","Retail"
"Company Attributes","Description Keyword — Include","growth"
"Company Attributes","Description Keyword — Exclude","staffing agency"
"Job Title","Seniority","Owner"
"Job Title","Job Function","Finance"
"Job Title","Job Title — Include (Similar To)","CEO"
"Job Title","Job Title — Exclude","Intern"
"Experience","Months in Current Role — Min","6"
"Experience","Number of Experiences — Min","2"
"Experience","Experience Description Keyword","growth"
"Location","Country — Include","United States"
"Location","Region — Exclude","APAC"
"Professional Bio","Bio Keyword","CFO"
"Professional Bio","Headline Keyword","founder"
"Professional Bio","About Section Keyword","EBITDA"
```

Name files: `01_Campaign_List_1_of_10.csv` through `10_Campaign_List_10_of_10.csv`

Save all 10 to `projects/engagement/clients/<client>/lists/<YYYY-MM-DD>/`. For multi-person accounts (Legion, FrontlineXP) with separate ICPs, save under `lists/<person-slug>/<YYYY-MM-DD>/`.

## Output Checklist
- [ ] ICP filtering table completed (all fields, no blanks)
- [ ] Industry fit prompt generated
- [ ] 10 campaign splits confirmed
- [ ] 10 CSVs generated and saved
