# Day 3 Plan — Compute + Begin Analysis

**Date:** Wednesday, June 3, 2026
**Location:** Punta Cana, Dominican Republic
**Stages taught:** Stage 3 (Compute) continues through the morning and early afternoon; Stage 4 (Analysis) begins in the afternoon
**Deliverables participants walk away with:** Raw model output (metrics, predictions, trained models) + initial read on whether their results make sense

---

## Morning Block 1 — Daily Review + Pipeline Completion (9:00 – 10:30)

- **Purpose:** Get every participant from "data is staged" to "first job is submitted"
- **Format:** Stand-up review + hands-on building
- **Internal schedule (from facilitator guide):**
  - 9:00 – 9:15: Daily review, who has data staged, who has scripts running, where blockers are
  - 9:15 – 10:30: Pipeline completion, feature engineering, model training scripts, submit first jobs
- **Lead resources:**
  - [docs/03-Compute/05-tapis-workflows.md](docs/03-Compute/05-tapis-workflows.md) (job submission via Tapis)
  - [docs/03-Compute/06-jupyter-hpc.md](docs/03-Compute/06-jupyter-hpc.md) (interactive GPU work)
  - [docs/02-Design/02-feature-engineering.md](docs/02-Design/02-feature-engineering.md) (feature engineering reference)
- **Activities:**
  - Finish feature engineering scripts
  - Write model training scripts using AI tools
  - Submit first jobs to the gh or gh-dev queue
  - Entry Point 3 participants use JupyterHub interactive sessions rather than Slurm batch jobs

## Morning Block 2 — Run Experiments (10:30 – 12:00)

- **Purpose:** Every participant has raw output by lunch
- **Format:** Independent work, facilitators circulate for debugging
- **Internal schedule (from facilitator guide):**
  - 10:30 – 12:00: Run experiments, submit jobs to gh or gh-dev, monitor, debug, iterate
- **Goal stated explicitly:** Raw output (model files, metrics.json, predictions) saved by 12:00
- **Common debugging issues to expect** (and how to redirect):
  - Module not found → check module load and the activated environment
  - Out of memory → switch queue or reduce batch size
  - Job pending forever → check queue limits, consider gh-dev for short jobs
  - Permission denied → check $SCRATCH path, not $HOME
  - Script works on laptop but not Vista → path differences, Python version mismatch
- **The hard handoff to Stage 4** (from [framework.md:131-133](framework.md)):
  - Do not interpret results until pipeline ran correctly, data joins are clean, models trained without errors
  - Bad inputs produce bad results no matter how good the interpretation is

## Lunch (12:00 – 1:00)

- Anyone with failed jobs uses lunch to talk to a facilitator about what went wrong

## Afternoon Block 1 — Compute Cleanup (1:00 – 2:00)

- **Purpose:** Everyone who didn't finish in the morning gets to raw output
- **Format:** Independent work, facilitators target the people who are behind
- **Internal schedule (from facilitator guide):**
  - 1:00 – 2:00: Continue compute for anyone not finished, rerun failed jobs, adjust parameters
- **Activities:**
  - Participants with results already: begin preliminary cleanup of output files, organize results/ directory
  - Participants still running: facilitator-supported debugging
  - Universal: verify output files exist and are readable before moving to Stage 4

## Afternoon Block 2 — Stage 4: Analysis Introduction (2:00 – 2:45)

- **Purpose:** Establish how to read ML output before they look at their own
- **Format:** Lecture + worked example
- **Lead resource:** Stage 4 deck (outline exists in [analysis-stage.md:213-226](analysis-stage.md), slides not yet built)
- **Supporting resource:** [docs/04-Analysis/01-metrics-reference.md](docs/04-Analysis/01-metrics-reference.md)
- **Internal schedule (from facilitator guide):**
  - 2:00 – 2:15: Present Stage 4, distribute metrics reference card
  - 2:15 – 2:45: Walk through the example project's results, show how to read metrics, SHAP, and visualizations
- **Two entry points + Cohort 1 assignments** (from [analysis-stage.md:24-78](analysis-stage.md)):
  - Entry Point 1 ("I can interpret ML output"): Gloria Washington, Iman Dehzangi, Hongmei Chi, Amelia Estwick, Nazia Sharmin
  - Entry Point 2 ("I have numbers but don't know what they mean"): Cheryl Swanier, Joseph Gaskin, Karina Liles, Nastassia Jones, Stacy Imagbe, Candice Idlebird, Kristyan Gilmore
- **Metrics reference to teach** (from [analysis-stage.md:84-113](analysis-stage.md)):
  - Regression: R-squared, RMSE, MAE
  - Classification: accuracy, precision, recall, F1, AUC-ROC
  - Feature importance (SHAP): summary plot interpretation, color coding, dot positions
- **The "what does good mean" reminder:**
  - No universal threshold
  - Compare to your baseline
  - Compare to published work
  - If results are much better than published work, check for data leakage before celebrating

## Afternoon Block 3 — Review Your Own Results (2:45 – 3:30)

- **Purpose:** Each participant looks at their raw output and uses the metrics reference card to read it
- **Format:** Independent work + facilitator-led pair conversations
- **Internal schedule (from facilitator guide):**
  - 2:45 – 3:30: Participants review their own results using the reference card, facilitators circulate
- **Activities:**
  - Open metrics.json and read every metric
  - Compare primary model to baseline (did the more complex model actually help?)
  - Look at SHAP values, identify top 5 features
  - Sanity check: do the numbers seem reasonable for the question?

## Afternoon Block 4 — Generate Visualizations + Begin Writing Interpretation (3:30 – 5:00)

- **Purpose:** Each participant has at least one publication-quality figure by end of day, and has begun writing their interpretation
- **Format:** Hands-on, AI tools active
- **Lead resources:**
  - [docs/04-Analysis/02-interpretation.md](docs/04-Analysis/02-interpretation.md)
  - [docs/04-Analysis/03-visualization.md](docs/04-Analysis/03-visualization.md)
  - [templates/analysis.md](templates/analysis.md)
- **Figures every paper needs** (from [analysis-stage.md:131-138](analysis-stage.md)):
  - SHAP summary plot (almost always the main finding)
  - Model comparison bar chart
  - Confusion matrix (classification problems)
  - Geographic map (spatially structured data)
  - Time series plot (temporally structured data)
  - Partial dependence plot (deep dive on one feature)
- **Publication quality checklist** to enforce:
  - 300 DPI minimum
  - Every axis has a label with units
  - Readable at column width
  - Colorblind-friendly palette (viridis, cividis, RdYlBu)
  - Descriptive title (not "Figure 1" but a real description)
  - Saved as PNG or PDF
- **AI prompt patterns to demonstrate** (from [analysis-stage.md:152-158](analysis-stage.md)):
  - "Generate a publication-quality SHAP summary plot, save at 300 DPI to figures/fig1_shap_summary.png, use colorblind-friendly palette"
  - "Create a bar chart comparing Random Forest and XGBoost on RMSE and R-squared"
  - "Generate a choropleth map of prediction errors by county using results/county_predictions.csv"
- **Hard rule:** Review every figure, AI gets structure right but may mislabel axes or pick bad color scales

## What participants walk away with at the end of Day 3

- A working pipeline that runs end-to-end without errors on Vista
- Raw output saved: trained models, metrics.json, predictions, SHAP values
- Initial read on their metrics (do the numbers make sense?)
- At least one publication-quality figure in figures/
- The beginning of an interpretation paragraph
- Familiarity with the metrics reference card and SHAP plot reading

---

## To-do — gaps that still need to be filled before Day 3

- [ ] **Build Deck E: Stage 4 — Analysis Introduction** (outline in [analysis-stage.md:213-226](analysis-stage.md), needs to be turned into actual slides)
- [ ] **Print the metrics reference card** as a physical handout (one page, two-sided is fine; covers regression, classification, SHAP interpretation)
- [ ] **Build example project results materials** for the 2:15 – 2:45 walkthrough: the example's metrics.json, SHAP plot, and a slide explaining what the numbers mean
- [ ] **Prepare a Tapis troubleshooting cheat sheet** for the morning compute blocks (common errors: module not found, OOM, permission denied, queue limits)
- [ ] **Confirm gh and gh-dev queue access** is live for every participant and queue wait times are acceptable for a 9:15 AM job submission
- [ ] **Pre-stage example results** in Vista (or in a shared GitHub repo) so participants whose own jobs failed have something to interpret in the afternoon
- [ ] **Decide facilitation split for the day**: morning is compute-heavy (Tapis support), afternoon shifts to analysis (metrics interpretation); Ashley and Nelson should split by phase or by entry point
- [ ] **Decide how to handle participants who don't have raw output by 2:00 PM**: do they keep grinding on compute, or pivot to interpreting the example data?
