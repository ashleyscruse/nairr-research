# Jupyter HPC with GPU Access

## Two Ways to Use Jupyter

| | JupyterHub | Jupyter HPC |
|--|------------|-------------|
| Where it runs | Shared container | Vista compute node |
| URL | jupyter.tacc.cloud | Launched via idev |
| GPU access | No | Yes (H200, 96GB) |
| Allocation cost | Free | Draws from your SUs |
| Best for | Standard work, exploration | Model training, GPU compute |

## Launching Jupyter HPC

### Step 1: SSH into Vista
```bash
ssh your_username@vista.tacc.utexas.edu
```

### Step 2: Request a compute node
```bash
idev -p gh-dev -N 1 -n 1 -t 01:00:00 -A TRA25001
```

### Step 3: Start Jupyter
```bash
module load gcc/13.2.0
module load python3
jupyter notebook --ip=0.0.0.0 --no-browser
```

Note the node name (e.g., `c642-022`) and token.

### Step 4: SSH tunnel (new terminal on your laptop)
```bash
ssh -N -L 8888:NODE_NAME:8888 your_username@vista.tacc.utexas.edu
```

### Step 5: Open in browser
```
http://localhost:8888/tree?token=YOUR_TOKEN
```

## Verify GPU Access

```python
import torch
print(f"CUDA available: {torch.cuda.is_available()}")
print(f"GPU: {torch.cuda.get_device_name(0)}")
print(f"Memory: {torch.cuda.get_device_properties(0).total_mem / 1e9:.1f} GB")
```

## When to Use What

| Task | Use |
|------|-----|
| Exploring data, plotting | JupyterHub |
| Writing and testing code | JupyterHub or gh-dev |
| Training on GPU | Jupyter HPC (gh) |
| Long overnight run | Batch job via Tapis |

## Important

- Jupyter HPC sessions consume allocation. Close when done.
- gh-dev has a 2-hour limit. Use for testing.
- Check running jobs: `squeue -u your_username`
