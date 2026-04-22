# AI Tools That See Your Files

## The Problem with Copy-Paste

Most researchers use AI like this:

1. Open ChatGPT in a browser
2. Copy code from their editor
3. Paste it into the chat
4. Read the response
5. Copy the AI's output
6. Paste it back into their editor
7. Repeat

This is slow, error-prone, and disconnected from your actual work. The AI does not see your project, your files, your errors, or your data. It is working blind.

## The Alternative: Tools That See Your Files

A new generation of AI tools runs inside your development environment and has direct access to your project files, terminal, and output. No copying. No pasting. The AI sees what you see.

## The Tools

### Claude Code

**What it is:** A CLI (command line) agent that runs in your terminal with full access to your project files, terminal commands, and search.

**How to use it:**
```bash
# Install
npm install -g @anthropic-ai/claude-code

# Run in your project directory
cd /scratch/my_project
claude
```

Then talk to it naturally:

> "Read the dataset in data/raw.csv and write a preprocessing script that handles missing values, creates the compound exposure features I described in features.md, and saves the result to data/processed.csv"

Claude Code will read your files, write the script, and you can run it immediately.

**Best for:** Writing and debugging scripts, file manipulation, building pipelines, automating repetitive tasks.

### Cursor

**What it is:** An AI-powered code editor (VS Code fork) with inline AI that sees your entire project.

**Key features:**
- Highlight code and press Cmd+K to edit it with AI
- Tab to accept AI suggestions as you type
- Chat panel that sees all your open files
- Reference specific files with @filename

**Best for:** Writing code interactively, refactoring, exploring unfamiliar codebases.

### Antigravity (Google)

**What it is:** Google's agent-first IDE. A VS Code fork powered by Gemini with multi-agent orchestration.

**Key features:**
- Spawn multiple AI agents working on different parts of your project simultaneously
- Full project context (Gemini's long context window sees everything)
- Built-in browser automation for testing

**Best for:** Large projects, multi-step tasks, when you want several things done in parallel.

### VS Code + Copilot

**What it is:** The most widely used code editor with GitHub Copilot built in.

**Key features:**
- Inline code suggestions as you type
- Copilot Chat panel for longer questions
- Extensions for Python, Jupyter, remote development

**Best for:** If you already use VS Code and want AI without switching editors.

### Codex (OpenAI)

**What it is:** An async coding agent that runs in the background. You describe a task, it works on it, you review the result.

**Best for:** Tasks you want to hand off entirely (write tests, fix a bug, refactor a file).

## Non-File-Aware Tools (Still Useful)

These tools do not see your files, but they are valuable for specific tasks:

| Tool | Best For |
|------|----------|
| **Perplexity** | Research discovery, finding papers and datasets, answering factual questions |
| **Claude** (web) | Long-form writing, paper drafting, analyzing pasted text or PDFs |
| **Gemini Deep Research** | Deep literature review, synthesizing many sources |

## How They Fit the Research Framework

| Stage | File-Aware Tool | Non-File-Aware Tool |
|-------|-----------------|---------------------|
| 1. Ideation | - | Perplexity, Gemini (brainstorming) |
| 2. Discovery | - | Perplexity, Gemini Deep Research (lit review) |
| 3. Design | Claude Code, Cursor (pipeline design) | Claude (methodology writing) |
| 4. Compute | Claude Code (scripts, job submission, debugging) | - |
| 5. Analysis | Claude Code, Cursor (visualizations, SHAP) | Claude (interpretation writing) |
| 6. Publication | Cursor (formatting, LaTeX) | Claude (drafting, editing) |

## Activity: Try Each Tool

1. **Claude Code:** Install it, open it in your project directory, and ask it to read one of your data files and describe what it contains
2. **Cursor:** Open your project, highlight a function, and ask it to improve or document it
3. **Perplexity:** Search for recent papers related to your research question

By the end of this session, you should know which tool you prefer for which task. You do not need to use all of them. Pick the ones that fit your workflow.

## The Rule

AI writes code. AI drafts text. AI finds papers.

**You** decide the research question. **You** interpret the results. **You** own the paper.

The tools do not do the research. You do the research, faster.
