# Stage 2: AI-Powered Literature Review

## Learning Objectives

By the end of this session, you will be able to:

- Conduct a rapid literature review using AI tools
- Distinguish between what AI surfaces and what you verify
- Build a working bibliography in Zotero
- Identify what has been studied (saturated) and what has not (gaps)

## Why Literature Review Before Compute

You do not touch HPC until you know what has already been done. If your question has been answered, running the same experiment on a supercomputer is a waste of allocation. The literature review tells you:

- Whether your question is novel
- What methods others have used (so you can build on them or improve)
- What data others have used (so you can find the same or better)
- Where to publish (which venues accept this type of work)

## AI Tools for Literature Review

| Tool | Best For | Limitation |
|------|----------|------------|
| **Perplexity** | Quick survey of a topic, finding recent papers | May miss niche or very recent work |
| **Gemini Deep Research** | Long-form literature synthesis, reading many papers at once | Can hallucinate citations |
| **Claude** | Analyzing specific papers, comparing findings, drafting summaries | Cannot search the web (use with PDFs or pasted text) |
| **Google Scholar** | Finding specific papers, citation tracking, "cited by" chains | Manual, no AI synthesis |
| **Semantic Scholar** | AI-powered paper recommendations, citation graphs | Less coverage of non-CS fields |
| **Connected Papers** | Visual graph of related papers from a seed paper | Limited to one seed at a time |

## Workflow: AI-Accelerated Literature Review

### Step 1: Broad Survey (15 minutes)

Use Perplexity or Gemini Deep Research:

> "What is the current state of research on [your topic]? Summarize the most cited recent papers (2022-2026), the methods they use, the datasets they rely on, and the gaps identified in review papers. Include specific paper titles and authors."

Read the output critically. Note:
- Which papers come up repeatedly (these are foundational)
- What methods dominate (this is what you're building on or differentiating from)
- What the AI says the gaps are (you will verify these)

### Step 2: Verify Key Papers (30 minutes)

For the 5-10 most important papers the AI surfaced:
1. Search for them on Google Scholar to confirm they exist
2. Read the abstract and conclusion
3. Add them to Zotero
4. Note: what data did they use? What method? What did they find?

**Important:** AI tools sometimes generate fake citations. Always verify before citing.

### Step 3: Find the Edges (15 minutes)

Use Connected Papers or Semantic Scholar with one of your key papers as a seed. Look for:
- Papers that cite your key papers (what came after?)
- Papers cited by your key papers (what came before?)
- Clusters of related work you missed

### Step 4: Draft Your Literature Summary (20 minutes)

Use Claude with the papers you have verified:

> "Here are the key papers I found on [topic]. [Paste titles, authors, and key findings for each]. Summarize the current state of this field in 3-4 paragraphs. Identify what has been well-studied and where the gaps are."

Review and edit the output. This becomes the basis for your Related Work section.

## Zotero Setup

[Zotero](https://www.zotero.org/) is a free reference manager. Install the browser extension to save papers with one click.

1. Download Zotero from [zotero.org](https://www.zotero.org/)
2. Install the browser connector
3. Create a collection for your project
4. Save papers directly from Google Scholar, arXiv, or journal sites

## Checking References

Before you cite anything:
- Does the paper actually exist? (Search for it on Google Scholar)
- Does it say what you think it says? (Read the abstract at minimum)
- Is it peer-reviewed? (Conference proceedings and journal articles, not blog posts)
- Is it recent enough? (For a fast-moving field, 2-3 years is the window)

## Checkpoint

You move to the next session when you have:
- A Zotero collection with 10-15 verified papers
- A 3-4 paragraph summary of the current state of the field
- A clear sense of what has been done and what has not
