# Stage 6: Formatting and Submission

## Learning Objectives

By the end of this session, you will be able to:

- Format your paper for a specific conference or journal
- Use Overleaf for LaTeX-based submissions
- Prepare supplementary materials and a reproducibility package
- Identify appropriate venues and submission deadlines

## Formatting for Your Target Venue

Every venue has specific formatting requirements. Check before you write, not after.

### Common Formats

| Venue Type | Template | Typical Page Limit |
|------------|----------|-------------------|
| ACM conferences (SIGCSE, CHI, CSCW) | ACM Primary Article Template | 6-10 pages |
| IEEE conferences | IEEE Conference Template | 6-8 pages |
| Springer journals | Springer LaTeX Template | No strict limit |
| Elsevier journals | Elsevier Article Template | No strict limit |
| AAAI/NeurIPS workshops | Venue-specific | 4-6 pages |

### Using Overleaf

[Overleaf](https://www.overleaf.com/) is a browser-based LaTeX editor. No local installation required.

1. Create an account at [overleaf.com](https://www.overleaf.com/)
2. Start a new project using your venue's template (search "ACM template" or "IEEE template" in Overleaf's gallery)
3. Paste your sections into the template
4. Upload your figures
5. Add your references via BibTeX (export from Zotero)

### If your venue accepts Word or Markdown

Some venues accept Word documents. If so, you can draft in any editor and format later. Google Docs works for collaborative editing.

## Anonymizing Your Submission

Many venues use double-blind review. If so:

- Remove your name and affiliation from the paper
- Replace "our previous work (Smith, 2024)" with "prior work (Anonymous, 2024)"
- Do not include acknowledgments that identify you
- Remove identifying information from file metadata

## Using AI to Format

In Claude Code or Cursor, with your draft open:

> "Convert this paper draft into LaTeX using the ACM Primary Article Template. Preserve all content. Add proper section headers, figure references, table formatting, and a bibliography section. Output a .tex file."

> "Here is my Zotero bibliography exported as BibTeX. Check that every citation in the paper has a corresponding BibTeX entry and that every BibTeX entry is cited in the paper."

## Reproducibility Package

Strong submissions include materials that let reviewers replicate your work:

- [ ] Code (scripts for data processing, model training, evaluation)
- [ ] Data access instructions (URLs, API endpoints, download scripts)
- [ ] Environment specification (requirements.txt or conda environment.yml)
- [ ] README explaining how to run everything
- [ ] Trained model weights (if small enough)

Host this on GitHub. Link to it in your paper (if not anonymous) or prepare to share after acceptance.

## Finding Conferences and Deadlines

| Resource | URL | What It Tracks |
|----------|-----|----------------|
| WikiCFP | wikicfp.com | Conference deadlines across CS |
| AI Deadlines | aideadlines.com | AI/ML conference deadlines |
| Conference Ranks | portal.core.edu.au | Conference quality rankings |

### Venue Selection Checklist

- [ ] Does this venue publish work in my topic area?
- [ ] Is the acceptance rate realistic for a first submission?
- [ ] Is the deadline achievable?
- [ ] Is the venue peer-reviewed?
- [ ] Will presenting here advance my career?

## After This Week

Your paper may not be submission-ready on Day 5. That is normal. What you should have:

- A complete first draft
- All figures and tables
- A target venue identified
- A Zotero bibliography
- A timeline for revision and submission

The revision process typically takes 2-4 weeks after the initial draft. Plan for it.

## Continued Access to TACC and NAIRR

Your TACC account and allocation do not expire when this program ends. You can continue to:

- Submit jobs through [morehouse.tapis.io](https://morehouse.tapis.io)
- Access JupyterHub at [jupyter.tacc.cloud](https://jupyter.tacc.cloud)
- Use your $SCRATCH and $WORK directories on Vista
- Apply for additional NAIRR allocations through [nairrpilot.org](https://nairrpilot.org)
