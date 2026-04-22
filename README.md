# Research Accelerator: Leveraging HPC to Accelerate Your Research

A structured, week-long curriculum that takes researchers from a question to preliminary results and a paper draft using high performance computing.

> Most researchers know HPC exists. Few know how to make it part of their actual workflow. This curriculum closes that gap.

## What This Is

A hands-on training program designed for faculty and researchers who want to integrate high performance computing into their research pipeline. Participants arrive with a research question and leave with preliminary results, a reproducible HPC workflow, and a paper draft ready for submission.

The curriculum covers the full research lifecycle, not just the compute.

| Day | Focus | What You Walk Away With |
|---|---|---|
| 1 | Research Foundation | A defined research question, identified dataset, and literature review |
| 2 | HPC Workflows | Your data on an HPC system, jobs submitted through Tapis, first results |
| 3 | AI-Assisted Research | Proficiency with AI coding tools that accelerate scripting, analysis, and writing |
| 4 | Analysis and Writing | Interpreted findings, visualizations, and a paper draft in progress |
| 5 | Publication Prep | A submission-ready paper draft and a plan for continued access to HPC resources |

## Who This Is For

Researchers and faculty at any career stage who want to:

- Use HPC resources (TACC, NAIRR, or institutional clusters) to run experiments that are too large for a laptop
- Learn how to submit and manage computational jobs without becoming a systems administrator
- Integrate AI coding tools into their research workflow instead of copying and pasting between browser tabs
- Produce a publication from the work they do during the program

No prior HPC experience is required. Familiarity with Python or R is helpful but not mandatory.

## Curriculum Highlights

**Example Research Project**

Every participant walks through a complete, publishable research workflow on Day 1 before starting their own. The example project uses publicly available data, machine learning models trained on HPC, and produces results worth writing about. This gives everyone a mental model for the full pipeline before they build their own.

**HPC Through Tapis**

Participants learn to manage HPC resources through [Tapis](https://tapis-project.org/), an API platform that handles job submission, file management, and system access without requiring deep command-line expertise. The curriculum covers both JupyterHub (for interactive work) and Jupyter HPC (for GPU-accelerated computing on dedicated nodes).

**AI Tools With File Access**

The program prioritizes AI tools that can see and work with your files directly. No more copying code into a chat window and pasting the response back.

| Tool | What It Does |
|---|---|
| Claude Code | CLI agent with full access to your project files, terminal, and search |
| Cursor | AI-powered code editor with inline editing and full file context |
| Antigravity | Google's agent-first IDE with multi-agent orchestration and full project context |
| VS Code + Copilot | Familiar editor with built-in AI assistance |
| Codex | OpenAI's async coding agent that runs in the background |
| Perplexity | Research discovery and literature search |
| Claude | Writing, analysis, and reasoning for non-code tasks |
| Gemini Deep Research | Long-context literature review and synthesis |

**Publication Pipeline**

The goal is not to learn tools for the sake of learning tools. The goal is a paper. The curriculum builds toward submission from Day 1, with dedicated time for writing, peer feedback, and formatting for target conferences and journals.

## Structure

```
research/
  README.md
  nairr-project.md       -- example research project specification
  workshop_notes.md       -- Tapis and TACC technical reference
```

## Author

**Ashley Scruse, Ph.D.**
Deputy Director, Morehouse Supercomputing Facility
[ashley.scruse@morehouse.edu](mailto:ashley.scruse@morehouse.edu)