# Dataset Discovery

## What You Need

For a week-long project, your data must be:

- **Publicly available** (no IRB, no months-long approvals)
- **Machine-readable** (CSV, JSON, API, not locked in PDFs)
- **Large enough** to justify HPC
- **Documented** (you need to know what the columns mean)

## Major Public Data Sources

| Source | What It Has | URL |
|--------|-------------|-----|
| data.gov | 250,000+ US government datasets | data.gov |
| Kaggle | Community datasets with starter notebooks | kaggle.com/datasets |
| Hugging Face Datasets | NLP, vision, audio datasets | huggingface.co/datasets |
| Google Dataset Search | Search engine for datasets | datasetsearch.research.google.com |
| AWS Open Data | Large-scale datasets on S3 | registry.opendata.aws |
| Papers With Code | Datasets linked to published papers | paperswithcode.com/datasets |

## Domain-Specific Sources

| Domain | Source | URL |
|--------|--------|-----|
| Health | CDC WONDER, CDC PLACES, CMS | wonder.cdc.gov, data.cdc.gov |
| Climate/Environment | EPA AQS, NOAA, NASA SEDAC | aqs.epa.gov, ncei.noaa.gov |
| Education | IPEDS, NCES | nces.ed.gov |
| Social Science | US Census ACS, ICPSR | census.gov, icpsr.umich.edu |
| Cybersecurity | CICIDS, NSL-KDD | Various |
| Finance | FRED, SEC EDGAR | fred.stlouisfed.org |

## Evaluating a Dataset

Before committing, answer:

1. Can I access it right now?
2. What format is it in?
3. How big is it?
4. What are the columns/fields?
5. How does it connect to other data? (Join key)
6. Are there known issues? (Missing values, suppression)

## Using AI for Dataset Discovery

> "I'm researching [your question]. What publicly available datasets could I use? I need data that is free, machine-readable, and large enough to benefit from HPC. List specific dataset names, URLs, and what variables they contain."

## Checkpoint

You should have at least one confirmed dataset with a clear download path and you understand what variables it contains.
