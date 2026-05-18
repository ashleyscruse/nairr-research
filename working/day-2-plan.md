# Day 2 Plan — Methodology + HPC Onboarding

**Date:** Tuesday, June 2, 2026
**Location:** Punta Cana, Dominican Republic
**Stages taught:** Stage 2 (Design) in the morning; Stage 3 (Compute) begins in the afternoon
**Deliverables participants walk away with:** Methodology Document + pipeline diagram + computational plan + data staged on Vista + authenticated Tapis access

---

## Morning Block 1 — Stage 2: Design Introduction (9:00 – 9:45)

- **Purpose:** Establish the methodology framework so everyone can write a defensible methods section
- **Format:** Lecture / slides + worked example
- **Lead resource:** Stage 2 deck (outline exists in [design-stage.md:211-223](design-stage.md), slides not yet built)
- **Supporting resource:** [docs/02-Design/01-methodology.md](docs/02-Design/01-methodology.md) (already published)
- **Internal schedule (from facilitator guide):**
  - 9:00 – 9:15: Present Stage 2, explain the five methodology questions and three deliverables
  - 9:15 – 9:45: Walk through the example project's methodology (show how the five questions were answered for the example)
- **The five methodology questions to teach:**
  - What goes in (input data schema, join keys, observation count)
  - What comes out (outcome variable, continuous vs. categorical)
  - What features matter (raw vs. engineered, where the novelty lives)
  - What models and why (matched to question type, plus baseline)
  - How do you know it worked (split strategy, metrics, success criteria)
- **Question-type-to-model matching table** to present (from [design-stage.md:137-144](design-stage.md)):
  - Predict a number → linear regression baseline, XGBoost/Random Forest level-up
  - Classify into groups → logistic regression baseline, XGBoost level-up
  - Find patterns → K-means baseline, DBSCAN/hierarchical level-up
  - Predict over time → ARIMA baseline, LSTM/Temporal Fusion level-up
  - Understand what matters → Random Forest + SHAP

## Morning Block 2 — Design Hands-On (9:45 – 12:00)

- **Purpose:** Every participant has a completed Methodology Document, pipeline diagram, and computational plan before lunch
- **Format:** Self-selected entry-point work, pair review
- **Lead resource:** [templates/methodology.md](templates/methodology.md) (template ready in .md, .docx, .pdf)
- **Internal schedule (from facilitator guide):**
  - 9:45 – 10:00: Self-select entry point, distribute methodology template
  - 10:00 – 11:00: Guided work, answer the five methodology questions
  - 11:00 – 11:30: Draw data pipeline diagrams + fill in computational plan
  - 11:30 – 11:50: Pair review with a partner (partner reads, identifies anything unclear or missing)
  - 11:50 – 12:00: Revise based on feedback, finalize before lunch
- **Three entry points + Cohort 1 assignments** (from [design-stage.md:20-92](design-stage.md)):
  - Entry Point 1 ("I know my method"): Gloria Washington, Iman Dehzangi, Amelia Estwick, Hongmei Chi
  - Entry Point 2 ("I know my question but not my method"): Cheryl Swanier, Joseph Gaskin, Karina Liles, Nazia Sharmin, Nastassia Jones
  - Entry Point 3 ("What's a methodology?"): Stacy Imagbe, Candice Idlebird, Kristyan Gilmore
- **Pipeline diagram requirements** (drawn on paper, whiteboard, or digitally):
  - Each data source as a box
  - The join key connecting them
  - Transformations and engineering steps
  - The final analysis-ready table
  - What goes to HPC vs. what stays on a laptop
- **Computational plan table** to fill in:
  - Step / What Happens / Where (laptop or Vista) / Queue / Estimated Time
- **Common pitfalls + redirects** (from [design-stage.md:226-234](design-stage.md)):
  - "I'll figure out the method when I see the data" → method comes first
  - Complex model because it sounds impressive → start with simplest model that could work
  - No evaluation plan → define what good looks like
  - Pipeline is too vague → if a stranger could not reproduce it, add detail
  - Everything mapped to GPU queue → does cleaning really need a GPU?

## Lunch (12:00 – 1:00)

- Facilitators circulate, help anyone whose methodology is still incomplete

## Afternoon Block 1 — Stage 3: Compute Introduction + Tapis Setup (1:00 – 1:45)

- **Purpose:** Every participant is authenticated to morehouse.tapis.io and has a project directory on Vista
- **Format:** Lecture + guided live setup
- **Lead resource:** Stage 3 intro deck (does not yet exist, see to-do)
- **Supporting resources:**
  - [docs/03-Compute/01-project-setup.md](docs/03-Compute/01-project-setup.md) (already published)
  - [docs/03-Compute/05-tapis-workflows.md](docs/03-Compute/05-tapis-workflows.md) (already published)
- **Internal schedule (from facilitator guide):**
  - 1:00 – 1:15: Present Stage 3, three deliverables (data on Vista, working pipeline, raw output), three entry points
  - 1:15 – 1:45: Guided setup, everyone authenticates to morehouse.tapis.io, creates project directory on Vista
- **Three entry points + Cohort 1 assignments** (from [compute-stage.md:24-100](compute-stage.md)):
  - Entry Point 1 ("I can code"): Gloria Washington, Iman Dehzangi, Hongmei Chi, Amelia Estwick, Nazia Sharmin
  - Entry Point 2 ("I can follow along"): Cheryl Swanier, Joseph Gaskin, Karina Liles, Nastassia Jones
  - Entry Point 3 ("This is my first time"): Stacy Imagbe, Candice Idlebird, Kristyan Gilmore
- **Standard project structure to teach** (from [compute-stage.md:120-144](compute-stage.md)):
  - Standard folder layout: data/raw, data/processed, scripts, notebooks, results, figures
  - $SCRATCH vs. $HOME vs. $WORK
  - What lives in Git, what does not
  - The laptop ↔ GitHub ↔ Vista flow
- **Naming conventions** to enforce:
  - No spaces in filenames
  - Lowercase
  - Scripts named by what they do
  - No version numbers in filenames (Git handles that)

## Afternoon Block 2 — Data Acquisition + Cleaning (1:45 – 3:00)

- **Purpose:** Every participant has their data on Vista, cleaned and ready for feature engineering
- **Format:** Hands-on, facilitators circulate, AI tools active
- **Lead resources:**
  - [docs/03-Compute/03-data-transfer.md](docs/03-Compute/03-data-transfer.md)
  - [docs/03-Compute/02-git.md](docs/03-Compute/02-git.md)
- **Internal schedule (from facilitator guide):**
  - 1:45 – 2:30: Data acquisition, download or upload datasets to Vista; Entry Point 3 participants use the example project data as a starting point
  - 2:30 – 3:00: Data cleaning and joining, use AI tools to generate preprocessing scripts
- **Activities:**
  - Authenticate to Tapis (Entry Point 1 self-serve, Entry Point 2/3 guided)
  - Set up Git repo on laptop, push to GitHub, pull on Vista
  - Download data via wget, curl, scp, or Tapis transfer (size-dependent strategy from [compute-stage.md:418](compute-stage.md))
  - Use AI tools (Claude Code, Cursor) to generate cleaning + join scripts from the methodology doc

## Afternoon Block 3 — Three Ways to Use AI for Coding (3:00 – 3:30)

- **Purpose:** Everyone knows how to use AI tools effectively for HPC work, not just chat-and-paste
- **Format:** Live demo of each method
- **Lead resource:** [docs/03-Compute/04-ai-coding.md](docs/03-Compute/04-ai-coding.md)
- **Three methods to demonstrate:**
  - Method 1: IDE-integrated (Cursor, Antigravity, VS Code + Copilot) — AI lives inside the editor
  - Method 2: Desktop / CLI with file access (Claude Code, Claude desktop) — AI sees and edits project files directly
  - Method 3: Browser chat (the baseline most people start with) — what to move away from
- **Demo prompt patterns to show live:**
  - "Read methodology.md and write a preprocessing script that follows the data pipeline described there. Save it to scripts/build_dataset.py"
  - "Run train_model.py and tell me what happened. If there's an error, fix it."
  - "Look at the results in results/metrics.json and tell me if the model is overfitting."

## Afternoon Block 4 — Independent Build (3:30 – 5:00)

- **Purpose:** Each participant ends the day with a working data pipeline and is ready to submit jobs tomorrow morning
- **Format:** Independent work, facilitators circulate
- **Activities:**
  - Finish data cleaning + joining
  - Begin feature engineering scripts
  - Write training script skeletons (do not run yet, that's Day 3 morning)
  - Pair Entry Point 3 participants with a facilitator or Entry Point 1 partner

## What participants walk away with at the end of Day 2

- A completed Methodology Document (five questions answered)
- A data pipeline diagram
- A computational plan mapping steps to Vista resources
- Authenticated access to morehouse.tapis.io
- A project directory on Vista following the standard structure
- Data downloaded, cleaned, and staged in $SCRATCH
- A Git repository on GitHub linked to their Vista workspace
- Functional fluency with at least one AI coding tool (Claude Code, Cursor, or VS Code + Copilot)

---

## To-do — gaps that still need to be filled before Day 2

- [ ] **Build Deck C: Stage 2 — Design** (outline in [design-stage.md:211-223](design-stage.md), needs to be turned into actual slides)
- [ ] **Build Deck D: Stage 3 — Compute Introduction** (covers the 1:00 – 1:45 block: three deliverables, three entry points, project structure, $SCRATCH vs. $HOME)
- [ ] **Build the example project's methodology walkthrough materials** for the 9:15 – 9:45 slot (slides or notebook showing how the example answered the five methodology questions)
- [ ] **Pre-stage example project data on Vista** for Entry Point 3 participants to use as a starting point in the 1:45 – 2:30 slot
- [ ] **Confirm Vista allocation status** and queue access (gh, gh-dev) is live for every participant's TACC username before Day 2
- [ ] **Print methodology pipeline diagram worksheets** (blank diagram template for the 11:00 – 11:30 block)
- [ ] **Print the computational plan table** as a fillable handout
- [ ] **Test the AI coding demo flow** before showing it live (Claude Code + Cursor + a sample project) so the demo does not crash mid-session
- [ ] **Decide facilitation split for the afternoon**: who covers Entry Point 1 vs. Entry Point 2 vs. Entry Point 3 (Ashley vs. Nelson)
- [ ] **Confirm what the example project actually is** (compound stressors or another) and lock it across all Day 2 materials so the same example carries forward from Day 1
