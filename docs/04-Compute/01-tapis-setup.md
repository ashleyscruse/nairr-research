# Stage 4: Getting Started with Tapis

## Learning Objectives

By the end of this session, you will be able to:

- Authenticate to the Morehouse Tapis tenant
- Navigate TapisUI to view systems, files, and apps
- Use the tapipy Python SDK to interact with Tapis programmatically

## What is Tapis?

Tapis is an API platform that lets you manage HPC resources (submit jobs, move files, run apps) without needing to be a systems administrator. Instead of SSH-ing into a supercomputer and writing Slurm scripts by hand, you interact with HPC through Python code or a web interface.

**Our tenant:** [morehouse.tapis.io](https://morehouse.tapis.io)

## Step 1: Authenticate

### Using Python (tapipy)

```python
from tapipy.tapis import Tapis

t = Tapis(base_url='https://morehouse.tapis.io',
          username='your_tacc_username',
          password='your_tacc_password')
t.get_tokens()

# Verify it worked
print(t.access_token.access_token[:20] + '...')
```

Your token lasts 4 hours. When it expires, call `t.get_tokens()` again.

### Using TapisUI

1. Go to [morehouse.tapis.io](https://morehouse.tapis.io)
2. Log in with your TACC credentials
3. You should see the dashboard with Systems, Files, Apps, Jobs in the sidebar

## Step 2: Explore Available Systems

Systems are the HPC and storage resources registered on the tenant.

```python
# List all systems available to you
systems = t.systems.getSystems()
for s in systems:
    print(f"{s.id:30s} {s.host}")
```

You should see the TACC systems on our allocation:

| System | Host | GPU | Purpose |
|--------|------|-----|---------|
| Vista | vista.tacc.utexas.edu | H200 (96GB) | Primary compute, GPU jobs |
| Frontera | frontera.tacc.utexas.edu | None (CPU) | Large-scale CPU jobs |
| Stampede3 | stampede3.tacc.utexas.edu | Mixed | General purpose |
| Lonestar6 | ls6.tacc.utexas.edu | A100 | GPU compute |

## Step 3: Browse Files

```python
# List your home directory on Vista
files = t.files.listFiles(systemId='vista-morehouse', path='/home1/')
for f in files:
    print(f"{f.type:5s} {f.size:>10d} {f.name}")
```

### TACC File System

| Directory | Variable | Use For | Quota |
|-----------|----------|---------|-------|
| /home1/ | $HOME | Scripts, config files | 10 GB |
| /work2/ | $WORK | Software, libraries | 1 TB |
| /scratch/ | $SCRATCH | Active job data, large datasets | No limit (purged after 10 days) |

**Rule of thumb:** Put your code in $HOME, your data in $SCRATCH, your installed software in $WORK.

## Step 4: Explore Available Apps

```python
# List all apps available on the tenant
apps = t.apps.getApps()
for a in apps:
    print(f"{a.id:30s} v{a.version}")
```

## Step 5: Upload a Test File

```python
# Create a project directory on scratch
t.files.mkdir(systemId='vista-morehouse', path='/scratch/my_project')

# Upload a small test file
with open('test.txt', 'w') as f:
    f.write('Hello from Tapis!')

t.files.insert(systemId='vista-morehouse',
               path='/scratch/my_project/',
               file=open('test.txt', 'rb'))

# Verify it's there
files = t.files.listFiles(systemId='vista-morehouse',
                          path='/scratch/my_project/')
for f in files:
    print(f.name)
```

## What You Just Did

You authenticated to Tapis, browsed HPC systems and files, and uploaded data to a supercomputer, all from Python. No SSH, no Slurm scripts, no command line. This is how you will interact with HPC for the rest of the week.

## Checkpoint

You move to the next session when you can authenticate, list systems, browse files, and upload a file through Tapis.
