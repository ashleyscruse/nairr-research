# Stage 1: Defining a Research Question

## Learning Objectives

By the end of this session, you will be able to:

- Articulate a specific, answerable research question from a broad area of interest
- Evaluate whether a question is scoped appropriately for a week-long project
- Understand what makes a research question suitable for HPC

## Example Research Walkthrough

Before you start your own project, we walk through a complete research workflow from start to finish. This shows you the full arc: question, data, pipeline, model, results, and paper.

### Example Project: Compound Environmental Stressors and Respiratory Health Outcomes

**Research question:** Do compound environmental stressors (air pollution + extreme heat + humidity occurring simultaneously) predict respiratory health outcomes better than any single stressor alone?

**Why this question works:**
- It addresses a gap in the literature (most studies use a single pollutant)
- It has publicly available data (EPA, NOAA, CDC)
- It requires HPC (joining large spatiotemporal datasets, training multiple models, running SHAP analysis)
- It produces results worth publishing

### What makes a good research question for this program?

| Good fit | Not a good fit |
|----------|----------------|
| Can be answered with available public data | Requires months of data collection or IRB approval |
| Benefits from computational scale (HPC) | Can be fully solved on a laptop |
| Has a clear gap in the literature | Has been studied extensively |
| Can produce preliminary results in 5 days | Requires years of longitudinal data to answer |
| Leads to a publishable paper | Is purely exploratory with no target venue |

## Activity: Define Your Research Question

Work through the following prompts. By the end of this session you should have a one-sentence research question.

1. **What broad area are you interested in?** (e.g., health, climate, education, cybersecurity, AI fairness)
2. **What specific phenomenon within that area?** (e.g., respiratory disease, student outcomes, network intrusion detection)
3. **What relationship are you trying to understand?** (e.g., "How does X affect Y?" or "Can we predict Y from X?")
4. **What makes this computational?** Why would this question benefit from HPC rather than a laptop?
5. **Write your question in one sentence.**

### Using AI to refine your question

Open Perplexity, Claude, or Gemini Deep Research and try:

> "I'm interested in [your area]. What are the most active research questions in this space right now? What gaps exist in the literature that could be addressed with machine learning and large-scale computing?"

Use the AI output as a starting point, not as your answer. You decide what question is worth your time.

## Checkpoint

You move to the next stage when you can state your research question in one or two sentences and explain why it needs HPC.
