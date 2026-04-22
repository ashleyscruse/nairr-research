# Methodology and Data Pipeline

## The Five Methodology Questions

Your Research Brief tells you **what** you are studying. The methodology tells you **how**. Answer these five questions and you have a Methods section.

### 1. What goes in?

Your input data. Specifically:
- What datasets, what years, what geographic scope
- How they join together (the key that connects them)
- What the final analysis table looks like (each row is a ___, each column is a ___)

### 2. What comes out?

Your outcome variable. What are you predicting, classifying, or measuring?
- Continuous (a number like mortality rate)
- Categorical (a label like high/low risk)
- Time series, clusters, or patterns

**Write it:** "I am predicting [outcome] from [features]."

### 3. What features matter?

Your predictor variables:
- **Standard features** (raw columns from your datasets)
- **Engineered features** (new variables you create, often where the novelty is)

### 4. What models and why?

Not just "XGBoost" but why XGBoost and not something else.

| Question Type | Start With | Level Up |
|---|---|---|
| Predict a number | Linear regression | XGBoost, Random Forest |
| Classify into groups | Logistic regression | XGBoost, Random Forest |
| Find patterns | K-means | DBSCAN, hierarchical |
| Predict over time | ARIMA | LSTM |
| Understand what matters | Random Forest + SHAP | XGBoost + SHAP |

### 5. How do you know it worked?

- Train/test split strategy (80/20, cross-validation, temporal split)
- Evaluation metrics (RMSE, R-squared, F1, AUC)
- What a "good" result looks like for your question

## Data Pipeline Diagram

Draw the flow from raw data to results:

```
[Dataset A] ---\
                \
[Dataset B] -----> [JOIN on ___] --> [Feature Engineering] --> [Model] --> [Results]
                /
[Dataset C] ---/
```

## Computational Plan

Map each step to a resource:

| Step | Where | Queue | Estimated Time |
|------|-------|-------|----------------|
| Data download | Login node | N/A | 30 min |
| Data cleaning | Login node | N/A | 1-2 hrs |
| Feature engineering | Vista | gh-dev | 30 min |
| Model training | Vista | gh | 1-4 hrs |
| SHAP analysis | Vista | gh | 30 min |
| Visualization | JupyterHub | N/A | 1 hr |

## Checkpoint

- [ ] My methodology is specific enough that someone else could run this study
- [ ] I have identified join keys between my datasets
- [ ] I have chosen models with a clear justification
- [ ] I have an evaluation plan with specific metrics
- [ ] I know which steps need HPC and which don't
