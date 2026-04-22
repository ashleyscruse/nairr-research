# Project Setup and File Structure

## The Standard Structure

Every participant uses the same file structure. This makes troubleshooting faster and maps directly to a reproducible GitHub repo.

```
project-name/
    README.md
    requirements.txt
    .gitignore
    data/
        raw/           -- Downloaded datasets (NOT in Git)
        processed/     -- Cleaned, joined data (NOT in Git)
    scripts/
        download_data.sh
        build_dataset.py
        train_model.py
        evaluate.py
    notebooks/
        exploration.ipynb
        analysis.ipynb
    results/           -- Model output (NOT in Git, except small summaries)
    figures/            -- Plots for your paper
```

## Why Each Folder Exists

| Folder | Purpose | In Git? |
|---|---|---|
| data/raw/ | Untouched downloads. Never modify. | No (download script is in Git instead) |
| data/processed/ | Cleaned, analysis-ready data | No (regenerate from scripts) |
| scripts/ | Every pipeline step as a separate script | Yes (core of your repo) |
| notebooks/ | Interactive exploration and analysis | Yes |
| results/ | Model outputs, metrics | Small summaries yes, large files no |
| figures/ | Publication plots | Yes (they go in your paper) |

## What Lives Where

```
YOUR LAPTOP                 GITHUB                    VISTA ($SCRATCH)

Edit scripts  ---push--->  github.com/you/project  ---pull--->  Run scripts
Write notebooks                                                  Download data
Draft paper                                                      Train models
     <----------pull---  github.com/you/project  <---push---  Save results
```

## On Vista

Your project lives in $SCRATCH:
```
/scratch/username/project-name/
```

Not $HOME (10GB quota). Not $WORK (for installed software).

$SCRATCH has no quota but files are purged after 10 days of inactivity. Your scripts are safe in Git.

## Naming Conventions

- No spaces in file or folder names
- Lowercase everything
- Scripts named by what they do: `download_data.py`, `train_model.py`
- No version numbers in filenames (that is what Git is for)
