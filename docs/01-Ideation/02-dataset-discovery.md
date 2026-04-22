# Stage 1: Dataset Discovery

## Learning Objectives

By the end of this session, you will be able to:

- Identify publicly available datasets relevant to your research question
- Evaluate whether a dataset is suitable for your project (size, format, access, licensing)
- Understand common data formats and how datasets join together

## Finding Public Data

For a week-long project, you need data that is:

- **Publicly available** (no IRB, no months-long data use agreements)
- **Machine-readable** (CSV, JSON, API, not locked in PDFs)
- **Large enough** to justify HPC (otherwise, why not use a laptop?)
- **Documented** (you need to know what the columns mean)

### Major Public Data Sources

| Source | What It Has | Access |
|--------|-------------|--------|
| [data.gov](https://data.gov) | 250,000+ US government datasets across all domains | Free download |
| [Kaggle](https://kaggle.com/datasets) | Community-contributed datasets, many with starter notebooks | Free account |
| [Hugging Face Datasets](https://huggingface.co/datasets) | NLP, vision, audio datasets ready for ML | Free |
| [UCI ML Repository](https://archive.ics.uci.edu/) | Classic ML benchmark datasets | Free |
| [Google Dataset Search](https://datasetsearch.research.google.com/) | Search engine specifically for datasets | Free |
| [AWS Open Data](https://registry.opendata.aws/) | Large-scale datasets hosted on S3 | Free |
| [Papers With Code](https://paperswithcode.com/datasets) | Datasets linked to published papers and benchmarks | Free |

### Domain-Specific Sources

| Domain | Source | URL |
|--------|--------|-----|
| Health | CDC WONDER, CDC PLACES, CMS Public Use Files | wonder.cdc.gov, data.cdc.gov |
| Climate/Environment | EPA AQS, NOAA, NASA SEDAC | aqs.epa.gov, ncei.noaa.gov |
| Education | IPEDS, NCES | nces.ed.gov |
| Social Science | US Census ACS, ICPSR | census.gov, icpsr.umich.edu |
| Cybersecurity | CICIDS, NSL-KDD, CTU-13 | Various |
| Finance | FRED, SEC EDGAR | fred.stlouisfed.org, sec.gov |
| Text/NLP | Common Crawl, Wikipedia dumps, arXiv | commoncrawl.org |

## Evaluating a Dataset

Before committing to a dataset, answer these questions:

1. **Can I access it right now?** If it requires an application, approval, or purchase, it may not work for this week.
2. **What format is it in?** CSV and JSON are easiest. APIs are fine if documented. Proprietary formats may slow you down.
3. **How big is it?** Small enough to download in minutes, large enough to justify HPC.
4. **What are the columns/fields?** Do you understand what each variable represents?
5. **How does it connect to other data?** What is the join key? (FIPS code, date, ID, coordinates)
6. **Are there known issues?** Missing values, suppressed cells, sampling bias?

## Activity: Find Your Data

1. Based on your research question from the previous session, search for 2-3 candidate datasets
2. For each dataset, fill out:
   - Name and source URL
   - Format and size
   - Key variables relevant to your question
   - Join key (how it connects to other data you might need)
   - Any access limitations
3. Pick your primary dataset and one supporting dataset

### Using AI for dataset discovery

Try this in Perplexity or Gemini:

> "I'm researching [your question]. What publicly available datasets could I use? I need data that is free, machine-readable, and large enough to benefit from HPC. List specific dataset names, URLs, and what variables they contain."

## Checkpoint

You move to Stage 2 when you have at least one confirmed dataset with a clear download path and you understand what variables it contains.
