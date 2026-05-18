# Day 4 Plan — Interpretation + Start Writing

**Date:** Thursday, June 4, 2026
**Location:** Punta Cana, Dominican Republic
**Stages taught:** Stage 4 (Analysis) finishes in the morning; Stage 5 (Publication) begins in the afternoon
**Deliverables participants walk away with:** 3 to 5 publication-quality figures + written interpretation + limitations section + Methodology and Results sections drafted + writing environment set up with venue template

---

## Morning Block 1 — Daily Review + Continue Interpretation (9:00 – 10:30)

- **Purpose:** Move from "I have results" to "I can explain what they mean"
- **Format:** Stand-up + independent writing
- **Internal schedule (from facilitator guide):**
  - 9:00 – 9:15: Daily review, who has results, who is still debugging
  - 9:15 – 10:30: Continue interpretation and visualization work, write findings paragraphs
- **Lead resources:**
  - [docs/04-Analysis/02-interpretation.md](docs/04-Analysis/02-interpretation.md)
  - [docs/04-Analysis/03-visualization.md](docs/04-Analysis/03-visualization.md)
  - [templates/analysis.md](templates/analysis.md)
- **The five interpretation questions to answer** (from [analysis-stage.md:166-176](analysis-stage.md)):
  - What did you find (one sentence, with specific numbers)
  - Does it answer your research question (go back to the Research Brief)
  - Does it fill the gap (does the result speak to the gap you identified Day 1)
  - How does it compare to existing work (pull numbers from your lit review)
  - What can't you claim (the limitations section)
- **Common pitfalls to redirect** (from [analysis-stage.md:229-238](analysis-stage.md)):
  - "Model performed well" with no numbers → state R-squared, RMSE, comparison to baseline
  - Over-interpreting → "associated with," not "causes"
  - Ignoring bad results → negative results are publishable if you can explain why
  - Letting AI write the interpretation → AI drafts, you decide what the results mean
  - Spending all day on one figure → 80% quality on all figures first, polish after

## Morning Block 2 — Write the Limitations Section (10:30 – 11:30)

- **Purpose:** Every participant has an honest, specific limitations section
- **Format:** Independent writing, facilitator-supported
- **Common limitations to teach** (from [analysis-stage.md:179-186](analysis-stage.md)):
  - Geographic scope (results may not generalize beyond the studied region)
  - Temporal resolution (annual data cannot capture acute effects)
  - Ecological fallacy (county-level associations are not individual-level causation)
  - Data quality (suppression, missingness, measurement error)
  - Model limitations (correlation is not causation)
  - Missing variables (what wasn't available in the data)
- **Hard rule:** "Every paper has limitations. Reviewers will find them. Better you name them first."

## Morning Block 3 — Pair Review of Analysis (11:30 – 12:00)

- **Purpose:** Catch interpretive errors before they harden into the paper draft
- **Format:** Pair exchange
- **Internal schedule (from facilitator guide):**
  - 11:30 – 12:00: Pair review, exchange analysis with a partner, does the interpretation match the numbers, are limitations honest
- **What partners look for:**
  - Are claims supported by specific numbers?
  - Does the interpretation connect back to the gap from Day 1?
  - Are limitations honest or sandbagged?
  - Are figures readable and labeled?

## Lunch (12:00 – 1:00)

- Last chance to clean up analysis before pivoting to writing

## Afternoon Block 1 — Stage 5: Publication Introduction (1:00 – 1:30)

- **Purpose:** Establish the three writing environments and the paper structure before anyone starts typing
- **Format:** Lecture + decision exercise
- **Lead resource:** Stage 5 deck (outline exists in [publication-stage.md:289-302](publication-stage.md), slides not yet built)
- **Supporting resource:** [docs/05-Publication/01-paper-writing.md](docs/05-Publication/01-paper-writing.md)
- **Internal schedule (from facilitator guide):**
  - 1:00 – 1:15: Present Stage 5, explain three writing environments and paper structure
  - 1:15 – 1:30: Participants choose their environment and set up
- **Three writing environments to teach** (from [publication-stage.md:24-111](publication-stage.md)):
  - Option 1: LaTeX in VS Code / Cursor / Antigravity (for ACM, IEEE, Springer venues; participants who know LaTeX)
  - Option 2: Overleaf (LaTeX without local installation; collaborative writing; LaTeX beginners)
  - Option 3: Word / Google Docs (for non-CS venues; participants not comfortable with code)
- **Decision guide to present:**
  - Targeting ACM/IEEE/Springer + know LaTeX → VS Code with LaTeX Workshop
  - Targeting ACM/IEEE/Springer + don't want to install → Overleaf
  - Targeting education / health / social science → Word or Google Docs
  - Collaborating with someone in real time → Overleaf or Google Docs
  - "I just want to get words on paper" → whatever they are fastest in
- **Paper structure to teach** (the seven sections and writing order):
  - Methodology (already written in Stage 2, just polish)
  - Results (already written in Stage 4, add figures)
  - Related Work (already drafted from Stage 1 lit review)
  - Introduction (now that you know what you found, frame the problem)
  - Discussion (interpretation + limitations, already drafted in Stage 4)
  - Conclusion (restate contribution in 3 to 4 sentences)
  - Abstract (write this last, after everything else exists)
- **The big mindset shift:** Writing the paper is assembly and polishing, not starting from scratch

## Afternoon Block 2 — Methodology + Results Sections (1:30 – 2:30)

- **Purpose:** Two of the seven paper sections drafted in one hour using prior-stage artifacts
- **Format:** Independent writing with AI assistance
- **Activities:**
  - Methodology: open methodology.md from Day 2, paste into paper, convert to past tense, add subsection headers per venue template
  - Results: open analysis.md and interpretation paragraphs from this morning, paste into paper, insert figure references using AI tools
- **AI prompt pattern to demonstrate** (from [publication-stage.md:150](publication-stage.md)):
  - "Here is my methodology document: [paste]. Draft a Methodology section for a conference paper targeting [venue]. Use past tense. Be specific about data sources, preprocessing steps, model configurations, and evaluation metrics. Target length: 1.5 pages."

## Afternoon Block 3 — Related Work + Introduction (2:30 – 3:30)

- **Purpose:** Two more sections drafted using Day 1 artifacts
- **Format:** Independent writing
- **Activities:**
  - Related Work: open the lit review summary from Day 1, expand into 1-2 pages, organize by gap-type from the Research Brief
  - Introduction: now that the results are known, frame the problem, motivation, and contribution; the contribution sentence comes from the gap statement
- **Writing order rationale:** Introduction is written 4th, not 1st, because the contribution depends on what was actually found

## Afternoon Block 4 — Continue Writing + Figures + References (3:30 – 5:00)

- **Purpose:** Paper draft is ~60% complete by end of day with figures embedded and reference manager set up
- **Format:** Independent work, facilitators circulate
- **Activities:**
  - Insert all figures with captions and in-text references
  - Set up reference management (Zotero to BibTeX for LaTeX; Zotero Word plugin for Word; Zotero Connector for Google Docs)
  - Verify every AI-generated citation against Google Scholar (AI tools hallucinate references)
  - Begin Discussion and Conclusion if time allows
- **Reference verification rule:** Every claim needs a citation, every citation needs to be verified

## What participants walk away with at the end of Day 4

- A complete interpretation with 5 questions answered (finding, fits question, fills gap, compares to lit, limitations)
- 3 to 5 publication-quality figures, embedded in the paper draft
- An honest limitations section
- A writing environment set up (VS Code + LaTeX, Overleaf, Word, or Google Docs)
- Methodology, Results, Related Work, and Introduction sections drafted
- Reference manager configured and connected to the writing environment
- Verified citations only (no AI hallucinations carried into the draft)

---

## To-do — gaps that still need to be filled before Day 4

- [ ] **Build Deck F: Stage 5 — Publication Introduction** (outline in [publication-stage.md:289-302](publication-stage.md), needs to be turned into actual slides)
- [ ] **Print the "writing environment decision guide" as a one-page handout** so participants can pick fast at 1:15 PM
- [ ] **Print the "paper structure + writing order" reference** as a one-page handout (seven sections, what goes where, write in this order)
- [ ] **Pre-load Overleaf templates** for the most likely target venues (ACM Primary Article Template, IEEE Conference Template, common journal templates) so participants can clone them at 1:15 PM without searching
- [ ] **Pre-download Word templates** for the most likely non-CS journals so participants who choose Option 3 have a starting point
- [ ] **Build a Zotero-to-BibTeX walkthrough** (could be a 5-minute slide section or a printed quick-reference) for the 3:30 – 5:00 block
- [ ] **Confirm Zotero is installed** for every participant from the Day 0 setup check
- [ ] **Decide facilitation split for the day**: morning is analysis support, afternoon is paper structure + writing tool setup; Nelson may take the Word/Google Docs track if Ashley takes LaTeX/Overleaf
- [ ] **Build (or locate) the example project's analysis writeup and figures** to use in the 9:15 – 10:30 walkthrough so participants see what a finished interpretation looks like
