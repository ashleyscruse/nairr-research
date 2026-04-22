# Tapis and HPC Workflows

## What is Tapis?

Tapis lets you manage HPC resources (submit jobs, move files, run apps) through Python or a web interface. No SSH, no Slurm scripts by hand.

**Our tenant:** [morehouse.tapis.io](https://morehouse.tapis.io)

## Authentication

```python
from tapipy.tapis import Tapis

t = Tapis(base_url='https://morehouse.tapis.io',
          username='your_tacc_username',
          password='your_tacc_password')
t.get_tokens()
```

Token lasts 4 hours. Call `t.get_tokens()` again when it expires.

## Browse Systems and Files

```python
# List systems
systems = t.systems.getSystems()
for s in systems:
    print(s.id, s.host)

# List files
files = t.files.listFiles(systemId='vista-morehouse', path='/scratch/username/')
for f in files:
    print(f.name)
```

## Batch vs. Interactive

| | Batch | Interactive |
|--|-------|-------------|
| What | "Run this script for me" | "Give me a node to work on" |
| How | `t.jobs.submitJob(...)` | `idev` or Jupyter HPC |
| Good for | Training models, overnight runs | Developing, testing, exploring |

## Submitting a Batch Job

```python
job = t.jobs.submitJob(
    name='my-training-job',
    appId='app-id',
    appVersion='0.1',
    execSystemId='vista-morehouse',
    execSystemLogicalQueue='gh-dev',
    nodeCount=1,
    coresPerNode=72,
    maxMinutes=30,
    memoryMB=256000
)
print(f"Job submitted: {job.uuid}")
```

## Monitoring

```python
import time
status = t.jobs.getJob(jobUuid=job.uuid).status
while status not in ['FINISHED', 'FAILED', 'CANCELLED']:
    print(f"Status: {status}")
    time.sleep(30)
    status = t.jobs.getJob(jobUuid=job.uuid).status
print(f"Done: {status}")
```

## Vista Queues

| Queue | Cores/Node | GPU | Max Time | Use For |
|-------|-----------|-----|----------|---------|
| gg | 144 | None | 48 hrs | CPU-only jobs |
| gh | 72 | 1x H200 (96GB) | 48 hrs | GPU jobs (real runs) |
| gh-dev | 72 | 1x H200 (96GB) | 2 hrs | Testing and debugging |

**Start with gh-dev** for testing. Move to gh for real runs.

## Common Errors

| Error | Fix |
|---|---|
| `ModuleNotFoundError` | `module load python3` before running |
| `CUDA out of memory` | Reduce batch size |
| `FileNotFoundError` | Use $SCRATCH paths, not /Users/ |
| Job stuck in QUEUED | Check `squeue -u username`, try gh-dev |
