# Getting Data onto Vista

## Decision Guide

| Data Size | Best Method |
|---|---|
| Under 50MB | Upload via Tapis, TapisUI, or GitHub |
| 50MB - 1GB | wget on Vista |
| Over 1GB | Download script on Vista, build on compute node |
| API-based | Script that calls the API from Vista |

## Method 1: wget on Vista (primary method)

From the login node or a Jupyter terminal:

```bash
wget -O /scratch/username/project/data/raw/file.csv https://data-source-url.com/file.csv
```

For compressed files:
```bash
wget -O /scratch/username/project/data/raw/data.zip https://data-source-url.com/data.zip
unzip /scratch/username/project/data/raw/data.zip -d /scratch/username/project/data/raw/
```

## Method 2: Download and Build Script (for large datasets)

When data comes in multiple files or needs transformation, write a setup script.

**Download step (login node):**
```bash
#!/bin/bash
for YEAR in 2018 2019 2020 2021 2022; do
    wget -O data/raw/pm25_${YEAR}.zip \
        "https://aqs.epa.gov/aqsweb/airdata/daily_88101_${YEAR}.zip"
done
```

**Build step (compute node):**
```bash
idev -p gh-dev -N 1 -n 1 -t 00:30:00 -A TRA25001
module load gcc/13.2.0 python3
python scripts/build_dataset.py
```

Commit the scripts to Git. Do NOT commit the data.

## Method 3: API Calls

```python
import requests
url = "https://api.census.gov/data/2022/acs/acs5?get=NAME,B17001_001E&for=county:*&in=state:13"
response = requests.get(url)
with open('data/raw/census.json', 'w') as f:
    f.write(response.text)
```

## Method 4: Tapis Upload (small files)

```python
t.files.insert(systemId='vista-morehouse',
               path='/scratch/username/project/data/raw/',
               file=open('local_file.csv', 'rb'))
```

## Method 5: TapisUI (small files, no code)

Go to morehouse.tapis.io > Systems > Files > drag and drop.

## The Rule

Under 50MB: upload however you want. Everything else: write a script and run it on Vista.
