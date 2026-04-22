# AI Coding Tools

There are three ways to use AI to write code. We are teaching you to move from Method 3 (what you already do) to Methods 1 and 2 (what is faster).

## Method 1: IDE-Integrated

**Tools:** Cursor, Antigravity, VS Code + Copilot

The AI lives inside your editor. It sees your open files, your project, and your cursor position. Highlight code and ask it to change things, or type and it suggests completions.

**Best for:** Writing new code, refactoring, inline editing.

**Limitation:** Runs on your laptop. You still push to GitHub and pull on Vista to run on HPC.

## Method 2: CLI/Desktop with File Access

**Tools:** Claude Code (CLI), Claude desktop app

The AI runs in your terminal and has direct access to your project files. It can read, write, run commands, and search your codebase.

```bash
cd /path/to/your/project
claude
```

Then talk to it:

> "Read methodology.md and write a preprocessing script that follows the pipeline described there."

> "Run train_model.py and fix any errors."

**Best for:** Building entire scripts from your methodology, debugging, automating multi-step tasks.

**On Vista:** Claude Code can run in a Vista terminal or JupyterHub terminal with direct access to your HPC files.

## Method 3: Copy and Paste

**Tools:** Claude (web), ChatGPT, Gemini (web)

Copy code from your editor, paste into a chat, read the response, copy it back.

**Best for:** Quick one-off questions, brainstorming. Also works as a fallback.

**Why we are moving away from this:** The AI has no context. It does not see your files, your data, or your errors. Every paste loses information. It is slow.

## Which Method for Which Task

| Task | Method 1 (IDE) | Method 2 (CLI) | Method 3 (Browser) |
|---|---|---|---|
| Write a new script | Good | Best | Slow |
| Debug an error | Best | Good | Works |
| Build from methodology doc | Good | Best | Works |
| Working on Vista | N/A | Best | Works |
| Quick question | Copilot | Overkill | Best |
| Writing paper text | N/A | Works | Best |

## The Teaching Moment

The contrast sells itself. Take a task like "write a script to download and clean this dataset." Do it with Method 3 first (5+ minutes of copy-paste). Then do the same task with Method 2 (one shot). Show both live.
