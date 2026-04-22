# Literature Review with AI

## Why Literature Review Before Compute

You do not touch HPC until you know what has already been done. If your question has been answered, running the same experiment on a supercomputer is a waste of allocation.

## AI Tools for Literature Review

| Tool | Best For | Limitation |
|------|----------|------------|
| **Perplexity** | Quick survey of a topic, finding recent papers | May miss niche work |
| **Gemini Deep Research** | Long-form synthesis, reading many papers at once | Can hallucinate citations |
| **Claude** | Analyzing specific papers, comparing findings, drafting summaries | May not surface niche or very recent papers |
| **Google Scholar** | Finding specific papers, citation tracking | Manual, no AI synthesis |
| **Semantic Scholar** | AI-powered paper recommendations | Less coverage outside CS |
| **Connected Papers** | Visual graph of related papers | Limited to one seed paper |

## Workflow

### Step 1: Broad Survey (15 minutes)

Use Perplexity or Gemini Deep Research:

> "What is the current state of research on [your topic]? Summarize the most cited recent papers (2022-2026), the methods they use, the datasets they rely on, and the gaps identified. Include specific paper titles and authors."

### Step 2: Verify Key Papers (30 minutes)

For the 5-10 most important papers:
1. Search Google Scholar to confirm they exist
2. Read the abstract and conclusion
3. Add to Zotero

**AI tools sometimes generate fake citations. Always verify before citing.**

### Step 3: Find the Edges (15 minutes)

Use Connected Papers or Semantic Scholar with a key paper as a seed. Look for papers that cite yours and papers cited by yours.

### Step 4: Draft Your Summary (20 minutes)

> "Here are the key papers I found on [topic]. [Paste titles and key findings]. Summarize the current state in 3-4 paragraphs. Identify what has been well-studied and where the gaps are."

## Zotero Setup

1. Download [Zotero](https://www.zotero.org/)
2. Install the browser connector
3. Create a collection for your project
4. Save papers from Google Scholar with one click

## Checkpoint

You should have 10-15 verified papers in Zotero and a 3-4 paragraph summary of the field.
