# Methodology and Data Pipeline

Your Research Brief tells you **what** you are studying. The methodology tells you **how**. Answer these questions and you have a Methods section. They work for any HPC computation, not only machine learning.

## What is your computation?

What kind of computation does your research need? Often one of:

- **Machine learning / predictive model** — predict or classify an outcome from data
- **Simulation or numerical model** — model how a system behaves over time or under conditions
- **Large-scale data processing / pipeline** — clean, join, or transform data too big for a laptop
- **Statistical analysis** — test relationships or differences at scale (regression, Bayesian, bootstrapping)
- **Optimization / parameter sweep** — search many configurations for the best one
- **Other / domain-specific**

**In one sentence, what will your computation do?**

## The Methodology Questions

### 1. What goes in?

Your input data:
- What datasets, what years, what scope
- How they join together (the key that connects them)
- What the final table looks like (each row is a ___, each column is a ___)

### 2. What comes out?

What your computation produces: a prediction, a simulated dataset, a processed table, a statistical result, an optimal configuration. Is it a number, a category, a time series, clusters, a dataset, or a statistical result?

### 3. What is your method?

- The approach you will use
- Why you chose it over alternatives
- Your baseline or point of comparison (the simpler result you compare against)

**If your computation is machine learning,** also decide your features (standard columns plus engineered variables, often where the novelty is) and your model. Match the model to your question:

| Question Type | Start With | Level Up |
|---|---|---|
| Predict a number | Linear regression | XGBoost, Random Forest |
| Classify into groups | Logistic regression | XGBoost, Random Forest |
| Find patterns | K-means | DBSCAN, hierarchical |
| Predict over time | ARIMA | LSTM |
| Understand what matters | Random Forest + SHAP | XGBoost + SHAP |

### 4. How do you know it worked?

Match your evaluation to your method:

- **Machine learning:** train/test split, metrics (RMSE, R-squared, F1, AUC), comparison to baseline
- **Simulation:** validation against known cases, convergence, sensitivity analysis
- **Data pipeline:** correctness and completeness checks, reproducibility
- **Statistics:** significance, effect size, model fit, assumptions checked
- **Optimization:** objective value, comparison to the baseline configuration

And, for any method: what does a "good" result look like for your question?

## Data Pipeline Diagram

Draw the flow from inputs to results:

```
[Input A] ---\
              \
[Input B] -----> [Combine / process] --> [Your computation] --> [Results]
              /
[Input C] ---/
```

## Computational Plan

Map each step to a resource:

| Step | Where | Queue | Estimated Time |
|------|-------|-------|----------------|
| Data download | Login node | N/A | 30 min |
| Preprocessing | Login node | N/A | 1-2 hrs |
| Main computation | Vista | gh | varies |
| Evaluation / analysis | Vista | gh | varies |
| Visualization | JupyterHub | N/A | 1 hr |

## Checkpoint

- [ ] I have named what kind of computation this is
- [ ] My methodology is specific enough that someone else could run this study
- [ ] I have identified how my data sources connect
- [ ] I have a clear way to tell whether the result is good
- [ ] I know which steps need HPC and which don't
