# Stage 3: Methodology and Data Pipeline

## Learning Objectives

By the end of this session, you will be able to:

- Map your datasets to a join strategy
- Choose appropriate ML models for your research question
- Document your methodology in a way that is reproducible and defensible

## From Question to Pipeline

Your research brief defined what you are studying. Now you define how.

A methodology has three parts:

1. **Data pipeline:** How do your datasets come together into a single analysis-ready table?
2. **Model selection:** What ML approach fits your question and data?
3. **Evaluation:** How will you know if your results are meaningful?

## Data Pipeline Design

### Step 1: Identify your join key

Every dataset in your pipeline needs to connect to the others through a shared key.

| Common Join Keys | Used By |
|------------------|---------|
| FIPS code (5-digit county) | EPA, CDC, Census, EJScreen |
| Date | EPA daily, NOAA daily, health records |
| Lat/Lon coordinates | NOAA weather stations, satellite data |
| Census tract (11-digit) | CDC PLACES, ACS, EJScreen |
| State abbreviation | BRFSS, many state-level sources |

If your datasets share a key, the join is direct. If they do not (e.g., weather stations have lat/lon but your outcome data uses FIPS codes), you need a **spatial join** (assign each county its nearest weather station).

### Step 2: Define your table

Sketch out what your final analysis table looks like:

```
Each row = one [unit of analysis] (county, patient, school, etc.)
Each column = one [variable]

Outcome variable: [what you are predicting]
Feature variables: [what you are predicting from]
```

Example:

```
Each row = one county-year
Outcome: annual respiratory mortality rate
Features: mean PM2.5, mean ozone, heat wave days, compound exposure days,
          poverty rate, insurance rate, % elderly, baseline asthma prevalence
```

### Step 3: Handle data quality

Before modeling, plan for:
- **Missing values:** Drop rows? Impute? Which strategy and why?
- **Suppressed cells:** CDC suppresses counts of 9 or fewer. How will you handle this?
- **Temporal alignment:** Are all your datasets on the same time scale (daily, monthly, annual)?
- **Spatial alignment:** Are all your datasets at the same geographic level?

## Model Selection

Match your model to your question type:

| Question Type | Example | Models |
|---------------|---------|--------|
| Predict a continuous value | "What will the mortality rate be?" | Linear regression, Random Forest, XGBoost, Neural Net |
| Classify into categories | "Will this patient be readmitted?" | Logistic regression, Random Forest, XGBoost, SVM |
| Find patterns/clusters | "Are there distinct groups in this data?" | K-means, DBSCAN, hierarchical clustering |
| Predict a time series | "What will air quality be next week?" | LSTM, ARIMA, Temporal Fusion Transformer |
| Understand feature importance | "What matters most?" | SHAP values on any of the above |

### For this program, start with:

1. **Random Forest** as your baseline (interpretable, hard to break, works on most tabular data)
2. **XGBoost** as your primary model (usually outperforms RF, still interpretable with SHAP)
3. **SHAP analysis** on your best model (this is often the publishable finding)

You can add neural networks or LSTMs if time allows, but a strong XGBoost + SHAP result is enough for a conference paper.

## Documenting Your Methodology

Write a methodology section (1-2 paragraphs) that includes:

1. What data you are using and how it joins together
2. What your outcome and feature variables are
3. What models you are training and why
4. How you are evaluating performance (accuracy, RMSE, AUC, etc.)
5. What your train/test split strategy is

This becomes the Methods section of your paper.

## Checkpoint

You move to Stage 4 when you have a documented methodology and a clear plan for what runs on HPC.
