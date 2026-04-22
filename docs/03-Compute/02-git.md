# Version Control with Git

If a script breaks, if a job corrupts your data, if you need to go back to a working version, Git is how you recover. This is not optional.

## Setting Up

### In VS Code / Cursor / Antigravity

1. Open your project folder
2. Source Control panel > Initialize Repository
3. Stage files, write a commit message, commit
4. Add remote and push to GitHub

### From the Terminal

```bash
cd /scratch/username/project-name
git init
git add .
git commit -m "Initial project setup"
git remote add origin git@github.com:username/project.git
git push -u origin main
```

### From GitHub Web

1. Create a new repo on github.com
2. Upload files through the browser
3. Clone to Vista: `git clone git@github.com:username/project.git`

## What to Commit vs. Ignore

| Commit | Do Not Commit |
|---|---|
| Scripts (.py, .R) | Raw data files (too large) |
| Notebooks (.ipynb) | Processed data (regenerate from scripts) |
| Config files, requirements.txt | Model weights (too large) |
| README, documentation | API keys or passwords |
| Small result summaries | Large output files |

**Rule of thumb:** If the file is larger than 50MB, do not commit it. Write a script that generates it instead.

## .gitignore Template

```
data/raw/
data/processed/
*.csv
*.parquet
*.zip
*.pkl
*.h5
*.pt
results/
.DS_Store
__pycache__/
.env
```

## Git Workflow

```
1. Write or modify a script
2. Test it
3. When it works: git add, git commit
4. Push to GitHub: git push
5. Repeat
```

Commit after every working step. Not at the end of the day.

## Where Git Runs

| Environment | Git Available? |
|---|---|
| Your laptop (VS Code, Cursor) | Yes |
| Vista login node | Yes (command line) |
| JupyterHub | Yes (terminal tab) |
| GitHub web interface | Yes (upload, edit) |
