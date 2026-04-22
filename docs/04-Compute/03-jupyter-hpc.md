# Stage 4: Jupyter HPC with GPU Access

## Learning Objectives

By the end of this session, you will be able to:

- Launch a Jupyter notebook running directly on an HPC compute node
- Access GPU resources (H200) from within a notebook
- Understand when to use Jupyter HPC vs. JupyterHub vs. batch jobs

## Two Ways to Use Jupyter on TACC

| | JupyterHub | Jupyter HPC |
|--|------------|-------------|
| **Where it runs** | Lightweight shared container | Directly on a Vista compute node |
| **URL** | [jupyter.tacc.cloud](https://jupyter.tacc.cloud) | Launched via Tapis job or idev |
| **GPU access** | No | Yes (H200, 96GB) |
| **Allocation cost** | Free | Draws from your allocation (SUs) |
| **Best for** | Standard work, data exploration, lightweight tasks | Model training, GPU inference, large datasets |
| **Multi-user** | Yes | One user per session |

**For this program:** You have access to both. Use JupyterHub for lightweight work. Use Jupyter HPC when you need GPU power.

## Launching Jupyter HPC (Interactive Method)

### Step 1: SSH into Vista

```bash
ssh your_username@vista.tacc.utexas.edu
```

### Step 2: Request an interactive compute node

```bash
idev -p gh-dev -N 1 -n 1 -t 01:00:00 -A TRA25001
```

This gives you a GPU node for 1 hour on the gh-dev queue.

### Step 3: Load modules and start Jupyter

```bash
module load gcc/13.2.0
module load python3
jupyter notebook --ip=0.0.0.0 --no-browser
```

Note the node name (e.g., `c642-022`) and the token in the output.

### Step 4: Create an SSH tunnel

In a **new terminal** on your laptop:

```bash
ssh -N -L 8888:NODE_NAME:8888 your_username@vista.tacc.utexas.edu
```

Replace `NODE_NAME` with the node from Step 2.

### Step 5: Open in your browser

```
http://localhost:8888/tree?token=YOUR_TOKEN
```

You are now running a Jupyter notebook on a Vista compute node with a 96GB H200 GPU.

## Launching Jupyter HPC (Tapis Method)

If a Jupyter HPC app is registered on the Morehouse tenant, you can launch it through Tapis:

```python
job = t.jobs.submitJob(
    name='jupyter-hpc-session',
    appId='jupyter-hpc',
    appVersion='1.0',
    execSystemId='vista-morehouse',
    execSystemLogicalQueue='gh-dev',
    nodeCount=1,
    maxMinutes=120
)
```

Check with the Tapis team for the exact app ID and configuration.

## Verifying GPU Access

Once inside your Jupyter notebook, verify you have GPU access:

```python
import torch

print(f"CUDA available: {torch.cuda.is_available()}")
print(f"GPU count: {torch.cuda.device_count()}")
if torch.cuda.is_available():
    print(f"GPU name: {torch.cuda.get_device_name(0)}")
    print(f"GPU memory: {torch.cuda.get_device_properties(0).total_mem / 1e9:.1f} GB")
```

Expected output:
```
CUDA available: True
GPU count: 1
GPU name: NVIDIA H200
GPU memory: 96.0 GB
```

## When to Use What

| Task | Use |
|------|-----|
| Exploring data, making plots | JupyterHub |
| Writing and testing code | JupyterHub or Jupyter HPC (gh-dev) |
| Training a model on GPU | Jupyter HPC (gh queue) |
| Running a long experiment overnight | Batch job via Tapis |
| Demonstrating results to a colleague | JupyterHub |

## Important Notes

- Jupyter HPC sessions consume allocation (SUs). Close them when you are done.
- The gh-dev queue has a 2-hour limit. Use it for testing, then move to gh for real work.
- Your files on $SCRATCH are accessible from both JupyterHub and Jupyter HPC.
- If your session disconnects, the kernel may still be running. Check with `squeue -u your_username`.

## Checkpoint

You move to Stage 5 when you have run your models and have raw results ready to interpret.
