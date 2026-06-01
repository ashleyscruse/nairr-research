# Research Accelerator: Leveraging AI and HPC to Accelerate Your Research

You already do research. This program is about setting up your workflow and your project so AI and high performance computing accelerate it. You arrive with a question and leave with preliminary results and a paper draft, moving faster than you could on your own.

## The Framework

This program follows a five-stage workflow for AI- and HPC-accelerated research. AI accelerates each stage; you make every decision between stages. The point is not to teach you how to do research (you already do that); it is to set up your project so the tools do the heavy lifting.

| Stage | Focus | Deliverable |
|-------|-------|-------------|
| 1. Ideation | Frame your question, validate the gap, find data, select venues | One-page research brief |
| 2. Design | Methodology, data pipeline, computational plan | Methodology document |
| 3. Compute | Data on HPC, working pipeline, raw output | Reproducible pipeline with results |
| 4. Analysis | Interpret results, visualize, connect to literature | Annotated results with figures |
| 5. Publication | Write, format, peer review, prepare submission | Paper draft with submission plan |

## Your workspace

Your research lives in the **HPC Research Starter**, a ready-to-go workspace with AI tools and HPC already wired in.

- Repo: [github.com/ashleyscruse/hpc-research-starter](https://github.com/ashleyscruse/hpc-research-starter)
- How to set it up: see the repo's **SETUP.md**

Make your own copy ("Use this template" or Fork), open it in VS Code, Cursor, Claude Code, or the web, and say hi. Your guide, **Sage**, walks you through getting set up.

## Daily schedule

Sessions run **10:00 AM to 3:00 PM** each day, with a lunch break. Mornings are guided; afternoons are hands-on work time with facilitators on hand.

| Day | Focus | You walk away with |
|---|---|---|
| **1 · Mon** | Set up your workspace for AI + Ideation | Workspace ready; research question and gap |
| **2 · Tue** | Target venues, methodology, getting onto TACC | Methodology + data on Vista |
| **3 · Wed** | Pipeline completion + analysis | Results and first figures |
| **4 · Thu** | Interpretation + start writing | Draft sections, limitations, figures |
| **5 · Fri** | Peer review + submission | Reviewed draft + submission plan |

## Daily agenda

### Day 1 · Monday — Set up your workspace + Ideation

| Time | Session | Lead |
|---|---|---|
| 10:00 to 10:15 | Welcome | Dr. Gosha |
| 10:15 to 10:30 | Check TACC access and troubleshoot login | Dr. Scruse |
| 10:30 to 11:00 | AI HPC accelerated research framework | Dr. Scruse |
| 11:00 to 11:30 | Set up your workspace for AI (starter repo + Sage) | Dr. Scruse |
| 11:30 to 12:00 | Ideation: your research question and the gap | Dr. Scruse |
| 12:00 to 1:00 | Lunch | |
| 1:00 to 2:00 | Literature review and dataset discovery | Whitney |
| 2:00 to 3:00 | Independent work: apply it and complete your research brief | Whitney |

### Day 2 · Tuesday — Venues, Methodology, TACC

| Time | Session | Lead |
|---|---|---|
| 10:00 to 10:15 | Daily agenda review | Dr. Scruse |
| 10:15 to 10:45 | Target venues | Dr. Scruse |
| 10:45 to 11:30 | Methodology and data pipeline | Dr. Scruse |
| 11:30 to 12:00 | Feature engineering | Whitney |
| 12:00 to 1:00 | Lunch | |
| 1:00 to 1:45 | Getting started on TACC (setup, $SCRATCH, Git) | Whitney |
| 1:45 to 2:30 | Data acquisition and cleaning | Whitney |
| 2:30 to 3:00 | Three ways to use AI for coding | Dr. Scruse |

### Day 3 · Wednesday — Pipeline completion + Analysis

| Time | Session | Lead |
|---|---|---|
| 10:00 to 10:15 | Daily agenda review | Dr. Scruse |
| 10:15 to 11:15 | Pipeline completion: AI coding, Git, Tapis and HPC workflows | Dr. Scruse |
| 11:15 to 12:00 | Run experiments (independent; optional Tapis breakout) | |
| 12:00 to 1:00 | Lunch | |
| 1:00 to 1:45 | Analysis introduction: metrics and SHAP | Whitney |
| 1:45 to 2:15 | Review your own results (independent) | |
| 2:15 to 3:00 | Generate visualizations and begin writing | Whitney |

### Day 4 · Thursday — Interpretation + Start writing

| Time | Session | Lead |
|---|---|---|
| 10:00 to 10:15 | Daily agenda review | Whitney |
| 10:15 to 11:00 | Continue interpretation (independent) | |
| 11:00 to 11:30 | Student pipelines into research | Whitney |
| 11:30 to 12:00 | Limitations and pair review of analysis (independent) | |
| 12:00 to 1:00 | Lunch | |
| 1:00 to 1:30 | Publication introduction | Dr. Scruse |
| 1:30 to 3:00 | Independent writing: methodology, results, related work, intro | |

### Day 5 · Friday — Peer review + Submission

| Time | Session | Lead |
|---|---|---|
| 10:00 to 10:15 | Daily agenda review | Whitney |
| 10:15 to 11:00 | Finish writing (Overleaf, anonymizing, AI formatting) | |
| 11:00 to 12:00 | Structured peer review | Whitney |
| 12:00 to 1:00 | Lunch | |
| 1:00 to 1:30 | Submission logistics | Whitney |
| 1:30 to 2:15 | Using NAIRR in future work and continued access to TACC | Dr. Scruse |
| 2:15 to 2:45 | Program evaluation | Dr. Newell |
| 2:45 to 3:00 | Closing remarks | |

## Pre-Event

Before arriving, all participants must complete the following:

- [ ] Create a [TACC account](https://portal.tacc.utexas.edu/account-request)
- [ ] Set up multi-factor authentication (Duo Mobile or Okta Verify)
- [ ] Verify you can log into [morehouse.tapis.io](https://morehouse.tapis.io)
- [ ] Create a [GitHub account](https://github.com) (if you don't have one)
- [ ] Install [Git](https://git-scm.com/downloads) on your laptop
- [ ] Install one of: [VS Code](https://code.visualstudio.com/), [Cursor](https://cursor.com), or [Antigravity](https://antigravity.google/)
- [ ] Install [Claude Code](https://claude.ai/code) (CLI)
- [ ] Install [Zotero](https://www.zotero.org/) with the browser connector

## Templates

All templates are available in multiple formats (Markdown, PDF, Word, Excel):

| Template | Stage | Purpose |
|----------|-------|---------|
| Research Brief | 1. Ideation | Question, gap, data sources, target venues |
| Methodology | 2. Design | Five methodology questions, pipeline diagram, computational plan |
| Compute Log | 3. Compute | Data staging, scripts, jobs, raw output |
| Analysis | 4. Analysis | Metrics, SHAP findings, interpretation, limitations |
| Metrics Reference | 4. Analysis | Plain-language guide to every metric |
| Peer Review | 5. Publication | Structured feedback for reviewing a partner's paper |
| Submission Plan | 5. Publication | Venue, deadline, revision timeline, checklist |

## Resources

- [Morehouse Tapis Tenant](https://morehouse.tapis.io)
- [Launching Jupyter on Vista (MSCF)](https://morehouse-supercomputing.github.io/jupyter-on-tapis/)
- [AI Tools Overview](./AI-Tools/01-tools-overview)

## Author

**Ashley Scruse, Ph.D.**
