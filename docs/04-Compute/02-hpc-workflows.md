# Stage 4: HPC Workflows on Vista

## Learning Objectives

By the end of this session, you will be able to:

- Submit a batch job to Vista through Tapis
- Monitor job status and retrieve output
- Understand the difference between batch and interactive jobs
- Stage your research data on HPC and run your first experiment

## Batch vs. Interactive

| | Batch Job | Interactive Job |
|--|-----------|-----------------|
| **What it is** | "Run this script for me" | "Give me a compute node to work on" |
| **How it works** | You submit and walk away, come back for results | You sit on the node and work in real time |
| **Good for** | Training models, processing large datasets, overnight runs | Developing code, testing, exploring data |
| **Tapis** | `t.jobs.submitJob(...)` | Use Jupyter HPC (next session) |

## Submitting a Batch Job

### Step 1: Prepare your script

Write a Python script that does something useful. For example, a data preprocessing script:

```python
# preprocess.py
import pandas as pd
import sys

print("Starting preprocessing...")
print(f"Python version: {sys.version}")

# Your data processing code here
# df = pd.read_csv('/scratch/my_project/raw_data.csv')
# df_clean = df.dropna()
# df_clean.to_csv('/scratch/my_project/clean_data.csv', index=False)

print("Preprocessing complete.")
```

### Step 2: Upload the script

```python
t.files.insert(systemId='vista-morehouse',
               path='/scratch/my_project/',
               file=open('preprocess.py', 'rb'))
```

### Step 3: Submit the job

```python
job = t.jobs.submitJob(
    name='preprocessing-run-1',
    appId='your-app-id',
    appVersion='0.1',
    execSystemId='vista-morehouse',
    execSystemLogicalQueue='gh',
    nodeCount=1,
    coresPerNode=72,
    maxMinutes=30,
    memoryMB=256000,
    fileInputs=[{
        "name": "script",
        "sourceUrl": "tapis://vista-morehouse/scratch/my_project/preprocess.py",
        "targetPath": "preprocess.py"
    }]
)

print(f"Job submitted: {job.uuid}")
```

### Step 4: Monitor the job

```python
import time

status = t.jobs.getJob(jobUuid=job.uuid).status
while status not in ['FINISHED', 'FAILED', 'CANCELLED']:
    print(f"Status: {status}")
    time.sleep(30)
    status = t.jobs.getJob(jobUuid=job.uuid).status

print(f"Final status: {status}")
```

**Job lifecycle:**

```
PENDING > PROCESSING_INPUTS > STAGING_INPUTS > STAGING_JOB >
SUBMITTING_JOB > QUEUED > RUNNING > ARCHIVING > FINISHED
```

### Step 5: Get the output

```python
# List job output files
output = t.jobs.getJobOutputList(jobUuid=job.uuid, outputPath='/')
for f in output:
    print(f.name)

# Download results
t.jobs.getJobOutputDownload(jobUuid=job.uuid, outputPath='/results.csv')
```

## Vista Queue Reference

| Queue | Cores/Node | GPU | Max Time | When to Use |
|-------|-----------|-----|----------|-------------|
| gg | 144 | None | 48 hrs | CPU-only jobs (data processing, classical ML) |
| gh | 72 | 1x H200 (96GB) | 48 hrs | GPU jobs (deep learning, large models) |
| gh-dev | 72 | 1x H200 (96GB) | 2 hrs | Quick tests and debugging |

**Start with gh-dev** for testing (2 hour limit keeps you from burning allocation on broken code). Move to gh for real runs.

## Activity: Submit Your First Job

1. Write a simple Python script that prints system info and lists files in a directory
2. Upload it to Vista via Tapis
3. Submit it as a batch job to the gh-dev queue
4. Monitor it until it finishes
5. Download and review the output

Then repeat with your actual research script (data download, preprocessing, or model training).

## Checkpoint

You move to the next session when you have successfully submitted a job, monitored it, and retrieved output.
