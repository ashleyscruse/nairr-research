# Curriculum To-Dos — All Days

Consolidated list of gaps to fill before the program starts. Pulled from the per-day plans ([day-1-plan.md](day-1-plan.md), [day-2-plan.md](day-2-plan.md), [day-3-plan.md](day-3-plan.md), [day-4-plan.md](day-4-plan.md), [day-5-plan.md](day-5-plan.md)).

---

## Master Week Deck

One single deck for the whole program, segmented by day and by section. Work through it sequentially across the week.

- [ ] **Build the master deck.** Sections below.

### Day 1 sections

- [ ] Section 1: Welcome + Week Overview + Framework (9:00 – 10:00)
- [ ] Section 2: Example Project Walkthrough — full 5-stage tour (10:00 – 10:30)
- [ ] Section 3: Stage 1 — Ideation (10:30 – 12:00); outline in [ideation-stage.md:104-116](ideation-stage.md)
- [ ] Section 4: Literature Review with AI (1:00 – 2:30)
- [ ] Section 5: Dataset Discovery (2:30 – 3:30)
- [ ] Section 6: Target Venues (3:30 – 4:30)

### Day 2 sections

- [ ] Section 7: Stage 2 — Design (9:00 – 9:45); outline in [design-stage.md:211-223](design-stage.md)
- [ ] Section 8: Stage 3 — Compute Introduction + Tapis Setup (1:00 – 1:45)
- [ ] Section 9: Three Ways to Use AI for Coding (3:00 – 3:30)

### Day 3 sections

- [ ] Section 10: Stage 4 — Analysis Introduction (metrics, SHAP) (2:00 – 2:45); outline in [analysis-stage.md:213-226](analysis-stage.md)
- [ ] Section 11: Visualization Guide (3:30 – 5:00)

### Day 4 sections

- [ ] Section 12: Stage 5 — Publication Introduction (1:00 – 1:30); outline in [publication-stage.md:289-302](publication-stage.md)
- [ ] Section 13: Paper Structure + Writing Order (inside the Stage 5 section)

### Day 5 sections

- [ ] Section 14: Peer Review — the six questions reviewers answer (10:15 – 11:15)
- [ ] Section 15: Submission Logistics (1:00 – 1:30)
- [ ] Section 16: Continued Access — TACC, NAIRR Pilot, morehouse.tapis.io (1:30 – 2:00)
- [ ] Section 17: Closing Remarks (3:30 – 4:00)

---

## Day 1 — Research Foundation

- [ ] Build or locate the example research project walkthrough materials for the 10:00 – 10:30 slot (notebook, slides section, or narrative); confirm with Nelson whether this exists somewhere outside this folder
- [ ] Confirm the afternoon block timing (1:00 – 5:00) with Nelson; current proposed structure is 1:00 lit review, 2:30 datasets, 3:30 venues, 4:30 brief completion
- [ ] Open `templates/research-accelerator-workbook.xlsx` and confirm what's inside; decide whether it stays as a Day 1 resource or moves to another stage
- [ ] Print a one-page week-at-a-glance schedule handout for each participant
- [ ] Build an AI prompt cheat sheet card (one printable page pulling the ~15 prompts from the Ideation lesson pages)
- [ ] Make name tents with pre-assigned entry-point labels based on the Cohort 1 sort in [ideation-stage.md:14-89](ideation-stage.md)
- [ ] Decide who facilitates which Cohort 1 entry-point group during the 10:30 – 12:00 Ideation block (Ashley vs. Nelson)
- [ ] Confirm the room/venue setup supports self-selected entry-point groups working in parallel (table clusters, wall space for the pipeline diagrams that come Day 2)

## Day 2 — Methodology + HPC Onboarding

- [ ] Build the example project's methodology walkthrough materials for the 9:15 – 9:45 slot (slides section or notebook showing how the example answered the five methodology questions)
- [ ] Pre-stage example project data on Vista for Entry Point 3 participants to use as a starting point in the 1:45 – 2:30 slot
- [ ] Confirm Vista allocation status and queue access (gh, gh-dev) is live for every participant's TACC username before Day 2
- [ ] Print methodology pipeline diagram worksheets (blank diagram template for the 11:00 – 11:30 block)
- [ ] Print the computational plan table as a fillable handout
- [ ] Test the AI coding demo flow before showing it live (Claude Code + Cursor + a sample project) so the demo does not crash mid-session
- [ ] Decide facilitation split for the afternoon: who covers Entry Point 1 vs. Entry Point 2 vs. Entry Point 3 (Ashley vs. Nelson)
- [ ] Confirm what the example project actually is (compound stressors or another) and lock it across all materials so the same example carries forward from Day 1

## Day 3 — Compute + Begin Analysis

- [ ] Print the metrics reference card as a physical handout (one page, two-sided is fine; covers regression, classification, SHAP interpretation)
- [ ] Build example project results materials for the 2:15 – 2:45 walkthrough: the example's metrics.json, SHAP plot, and a slide section explaining what the numbers mean
- [ ] Prepare a Tapis troubleshooting cheat sheet for the morning compute blocks (common errors: module not found, OOM, permission denied, queue limits)
- [ ] Confirm gh and gh-dev queue access is live for every participant and queue wait times are acceptable for a 9:15 AM job submission
- [ ] Pre-stage example results in Vista (or in a shared GitHub repo) so participants whose own jobs failed have something to interpret in the afternoon
- [ ] Decide facilitation split for the day: morning is compute-heavy (Tapis support), afternoon shifts to analysis (metrics interpretation); Ashley and Nelson should split by phase or by entry point
- [ ] Decide how to handle participants who don't have raw output by 2:00 PM: do they keep grinding on compute, or pivot to interpreting the example data?

## Day 4 — Interpretation + Start Writing

- [ ] Print the "writing environment decision guide" as a one-page handout so participants can pick fast at 1:15 PM
- [ ] Print the "paper structure + writing order" reference as a one-page handout (seven sections, what goes where, write in this order)
- [ ] Pre-load Overleaf templates for the most likely target venues (ACM Primary Article Template, IEEE Conference Template, common journal templates) so participants can clone them at 1:15 PM without searching
- [ ] Pre-download Word templates for the most likely non-CS journals so participants who choose Option 3 have a starting point
- [ ] Build a Zotero-to-BibTeX walkthrough (a slide subsection or a printed quick-reference) for the 3:30 – 5:00 block
- [ ] Confirm Zotero is installed for every participant from the Day 0 setup check
- [ ] Decide facilitation split for the day: morning is analysis support, afternoon is paper structure + writing tool setup; Nelson may take the Word/Google Docs track if Ashley takes LaTeX/Overleaf
- [ ] Build (or locate) the example project's analysis writeup and figures to use in the 9:15 – 10:30 walkthrough so participants see what a finished interpretation looks like

## Day 5 — Peer Review + Submission Plan

- [ ] Print the peer review template as a physical worksheet (or distribute the .docx so participants can fill in digitally)
- [ ] Print the submission plan template as a physical worksheet (or .docx)
- [ ] Draft the program evaluation focus group questions + the written survey for the 2:00 – 2:30 block (anonymous, captures funder-reportable metrics)
- [ ] Build a "what to back up before you leave Vista" checklist for the continued-access block
- [ ] Prepare a one-page NAIRR Pilot allocation request walkthrough for participants who want to apply for their own institutional access after the workshop
- [ ] Set up a post-program Slack channel or email list before the program ends so the cohort has a continuity channel
- [ ] Confirm photographer / group photo plan for the closing block
- [ ] Decide facilitation split for the day: peer review block usually runs better with both facilitators circulating; submission logistics and continued-access blocks can be split (Ashley on NAIRR/TACC, Nelson on venue logistics)
