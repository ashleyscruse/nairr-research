# Day 1 Plan — Research Foundation

**Date:** Monday, June 1, 2026
**Location:** Punta Cana, Dominican Republic
**Stage taught:** Stage 1 (Ideation)
**Deliverable participants walk away with:** Completed Research Brief (research question, gap, data sources, target venues)

---

## Morning Block 1 — Welcome + Week Overview + Framework (9:00 – 10:00)

- **Purpose:** Orient participants to the full week, set expectations, confirm pre-program setup
- **Format:** Lecture / slides with light Q&A
- **Lead resource:** Deck A (does not yet exist, see to-do)
- **Content to cover:**
  - Welcome, introductions, housekeeping (venue logistics, schedule, meals, Slack/email channels)
  - Who is in the room (each participant gives 30 seconds: name, institution, what they're working on)
  - The promise of the week: arrive with a research question, leave with a paper draft
  - Tour of the 5-stage research framework
    - Stage 1: Ideation (today)
    - Stage 2: Design (Tuesday AM)
    - Stage 3: Compute (Tuesday PM through Wednesday)
    - Stage 4: Analysis (Wednesday PM through Thursday AM)
    - Stage 5: Publication (Thursday PM through Friday)
  - The hard rule of the week: AI accelerates every stage, you make every decision between stages
  - What they walk away with by Friday afternoon:
    - Submission-ready (or revision-ready) paper draft formatted to a target venue
    - Reproducible HPC pipeline on Vista
    - Continued-access plan for TACC / NAIRR / morehouse.tapis.io
  - Pre-program checklist confirmation (raise hands)
    - TACC account created, MFA active
    - Can log into morehouse.tapis.io
    - GitHub account exists, Git installed locally
    - Editor installed (VS Code, Cursor, or Antigravity)
    - Claude Code CLI installed
    - Zotero installed with browser connector
  - Anyone not set up: pair with a facilitator during the 10:00 break to fix before Ideation starts

## Morning Block 2 — Example Research Project Walkthrough (10:00 – 10:30)

- **Purpose:** Give every participant a complete mental model of the 5-stage pipeline before they start their own
- **Format:** Live walkthrough / demo
- **Lead resource:** Example project materials (do not yet exist as a Day 1 walkthrough, see to-do)
- **Content to cover:**
  - The example project (compound environmental stressors + respiratory mortality, or equivalent)
  - How the question was scoped: from broad topic to one-sentence research question
  - The gap: what had not been done and why
  - The data sources and how they joined together
  - The methodology in one slide: features, model, evaluation
  - What the HPC pipeline looked like end to end
  - Key results and figures
  - Where this work fits as a publication
- **Why this matters:** Participants who can see a finished example understand what "good" looks like before they try to make their own

## Morning Block 3 — Stage 1: Ideation (10:30 – 12:00)

- **Purpose:** Every participant leaves with a one-sentence research question that is specific, answerable in 5 days, and benefits from HPC
- **Format:** Brief lecture, self-selection, guided work, share-out
- **Lead resource:** Deck B (outline exists in [ideation-stage.md:104-116](ideation-stage.md), slides not yet built)
- **Supporting resources:**
  - [docs/01-Ideation/01-entry-points.md](docs/01-Ideation/01-entry-points.md) (already published)
  - [docs/01-Ideation/02-research-questions.md](docs/01-Ideation/02-research-questions.md) (already published)
  - [templates/research-brief.md](templates/research-brief.md) (template ready in .md, .docx, .pdf)
- **Internal schedule (from facilitator guide):**
  - 10:30 – 10:45: Present Stage 1 + the three entry points
  - 10:45 – 11:00: Participants self-select an entry point and begin work
    - Entry Point 1 ("I have a project"): scope existing work for HPC + this week
    - Entry Point 2 ("I have a concept"): use AI to narrow a direction to a question
    - Entry Point 3 ("I'm starting fresh"): use AI to brainstorm from scratch
  - 11:00 – 11:30: Guided work, facilitators circulate
  - 11:30 – 11:50: Share-out, each person states their question in one sentence, group gives feedback
  - 11:50 – 12:00: Revise based on feedback, finalize before lunch
- **Pre-sorted entry points for Cohort 1** (from [ideation-stage.md:14-89](ideation-stage.md)):
  - Entry Point 1: Gloria Washington, Iman Dehzangi, Nastassia Jones, Amelia Estwick
  - Entry Point 2: Cheryl Swanier, Hongmei Chi, Joseph Gaskin, Karina Liles, Stacy Imagbe, Candice Idlebird
  - Entry Point 3: Kristyan Gilmore, Nazia Sharmin
- **Assessment criteria for each question** (facilitators apply during share-out):
  - Specific (you can tell exactly what they're studying)
  - Answerable this week (preliminary results in 5 days)
  - HPC-suitable (actually needs more than a laptop)
  - Data exists (plausible public source)
  - Publishable (you can imagine a venue)
- **Common pitfalls + redirects** (from [ideation-stage.md:130-138](ideation-stage.md)):
  - Too broad → "pick one disease, one data source, one method"
  - Doesn't need HPC → "what changes with 50,000 data points instead of 50?"
  - No public data → "can we reframe around data that exists?"
  - Dissertation-sized → "what's the smallest publishable piece?"
  - Attached to infeasible idea → "keep that as long-term goal, what's step one?"

## Lunch (12:00 – 1:00)

- Informal time, facilitators available for one-on-ones with anyone whose question is still shaky

## Afternoon Block 1 — Literature Review with AI (1:00 – 2:30)

- **Purpose:** Every participant has 10–15 verified papers in Zotero and a 3–4 paragraph summary of the field they're entering
- **Format:** Brief lecture, hands-on work, AI tool demonstration
- **Lead resource:** [docs/01-Ideation/03-literature-review.md](docs/01-Ideation/03-literature-review.md) (already published)
- **Content to cover:**
  - Why literature review before compute (don't burn HPC allocation answering solved questions)
  - AI tools for literature review and their tradeoffs
    - Perplexity: quick survey, recent papers
    - Gemini Deep Research: long-form synthesis (warning: can hallucinate citations)
    - Claude: analyzing specific papers, drafting summaries
    - Google Scholar: manual citation tracking
    - Semantic Scholar, Connected Papers: graph-based discovery
  - The 4-step workflow
    - Broad survey (15 min, AI-led)
    - Verify key papers (30 min, manual via Google Scholar, add to Zotero)
    - Find the edges (15 min, Connected Papers / Semantic Scholar)
    - Draft a summary (20 min, AI-assisted)
  - Zotero setup walkthrough (download, connector, project collection)
- **Hand-on activity:**
  - Each participant runs the broad-survey prompt on their own question
  - Verifies and saves 10–15 papers to Zotero
  - Drafts a 3–4 paragraph field summary
- **Hard rule:** AI-generated citations must be verified before they go in the brief

## Afternoon Block 2 — Dataset Discovery (2:30 – 3:30)

- **Purpose:** Every participant has at least one confirmed dataset with a clear download path and understands its columns
- **Format:** Brief lecture, hands-on search, evaluation
- **Lead resource:** [docs/01-Ideation/04-dataset-discovery.md](docs/01-Ideation/04-dataset-discovery.md) (already published)
- **Content to cover:**
  - Data requirements for a 5-day project
    - Publicly available (no IRB)
    - Machine-readable (CSV, JSON, API, not PDFs)
    - Large enough to justify HPC
    - Documented (column dictionaries exist)
  - Major public data sources: data.gov, Kaggle, Hugging Face Datasets, Google Dataset Search, AWS Open Data, Papers With Code
  - Domain-specific sources by field: health (CDC WONDER, PLACES, CMS), climate (EPA AQS, NOAA, NASA SEDAC), education (IPEDS, NCES), social science (ACS, ICPSR), cybersecurity (CICIDS, NSL-KDD), finance (FRED, SEC EDGAR)
  - Dataset evaluation checklist (6 questions): access, format, size, fields, join key, known issues
  - AI prompt pattern for dataset discovery
- **Hands-on activity:**
  - Each participant identifies at least one primary dataset
  - Documents it in the Research Brief data sources table
  - Identifies the join key if multiple datasets are needed

## Afternoon Block 3 — Target Venues (3:30 – 4:30)

- **Purpose:** Every participant has 2–3 target venues with deadlines, page limits, and fit rationale
- **Format:** Brief lecture, hands-on search
- **Lead resource:** [docs/01-Ideation/05-target-venues.md](docs/01-Ideation/05-target-venues.md) (already published)
- **Content to cover:**
  - Conference vs. journal tradeoffs (timeline, length, review process, networking)
  - Why a conference or workshop paper is realistic for a week-long project
  - How to find the right venue
    - Look where your key papers were published
    - Check scope, acceptance rate, timeline
  - Deadline trackers: WikiCFP, AI Deadlines, Conference Ranks
  - Submission costs (submission fees, registration, page charges, open access, color figures)
  - Reminder: ask institution about publication support funds before paying out of pocket
- **Hands-on activity:**
  - Each participant identifies 2–3 target venues
  - Records venue, type, deadline, page limit, fit rationale in the Research Brief venue table

## Afternoon Block 4 — Complete the Research Brief + Share-Out (4:30 – 5:00)

- **Purpose:** Every participant has a complete one-page Research Brief
- **Format:** Independent writing, then group share-out
- **Lead resource:** [templates/research-brief.md](templates/research-brief.md) (template ready)
- **Activity:**
  - Complete all 5 sections of the Research Brief
    - Research question (one sentence)
    - Gap it fills + 3–5 key papers
    - Data sources (primary + supporting + join keys)
    - 2–3 target venues with deadlines
    - Proposed approach (method, outcome variable, features, what success looks like)
  - Run the self-check (5 items at the bottom of the template)
  - One-minute share-out per person: state your question + your venue
- **End-of-day handoff:** Anyone without a completed brief is told they're starting Day 2 behind; they self-manage the catch-up

## What participants walk away with at the end of Day 1

- A one-page Research Brief, complete
- A Zotero library with 10–15 verified papers
- A 3–4 paragraph summary of their field
- One confirmed dataset (minimum) with a download path
- 2–3 target venues with deadlines and fit notes
- A working mental model of the full 5-stage framework
- Confirmation their pre-program setup is functional

---

## To-do — gaps that still need to be filled before Day 1

- [ ] **Build Deck A: Welcome + Week Overview + Framework** (~9:00 – 10:00 slot)
- [ ] **Build Deck B: Stage 1 — Ideation** (outline exists in [ideation-stage.md:104-116](ideation-stage.md), needs to be turned into actual slides)
- [ ] **Build or locate the example research project walkthrough materials** for the 10:00 – 10:30 slot (notebook, slides, or narrative). Confirm with Nelson whether this exists somewhere outside this folder
- [ ] **Confirm the afternoon block timing** (1:00 – 5:00) with Nelson; current proposed structure is 1:00 lit review, 2:30 datasets, 3:30 venues, 4:30 brief completion
- [ ] **Open `templates/research-accelerator-workbook.xlsx`** and confirm what's inside; decide whether it stays as a Day 1 resource or moves to another stage
- [ ] **Print a one-page week-at-a-glance schedule handout** for each participant
- [ ] **Build an AI prompt cheat sheet card** (one printable page pulling the ~15 prompts from the Ideation lesson pages)
- [ ] **Make name tents with pre-assigned entry-point labels** based on the Cohort 1 sort in [ideation-stage.md:14-89](ideation-stage.md)
- [ ] **Decide who facilitates which Cohort 1 entry-point group** during the 10:30 – 12:00 Ideation block (Ashley vs. Nelson)
- [ ] **Confirm the room/venue setup** supports self-selected entry-point groups working in parallel (table clusters, wall space for the pipeline diagrams that come Day 2)
