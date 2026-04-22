# Stage 5: Visualization

## Learning Objectives

By the end of this session, you will be able to:

- Create publication-quality visualizations of your results
- Use SHAP plots to communicate feature importance
- Generate geographic maps if your data is spatial

## Visualization Principles for Papers

Figures in a paper are not decorations. Each figure should answer a specific question:

| Figure Type | Question It Answers |
|-------------|---------------------|
| SHAP summary plot | Which features matter most? |
| SHAP dependence plot | How does one feature affect the prediction? |
| Bar chart of model comparison | Which model performed best? |
| Geographic map | Where are the effects strongest? |
| Time series plot | How do patterns change over time? |
| Confusion matrix | Where does the model make mistakes? |

## SHAP Visualizations

```python
import shap
import matplotlib.pyplot as plt

explainer = shap.TreeExplainer(model)
shap_values = explainer.shap_values(X_test)

# Figure 1: Feature importance (global)
fig, ax = plt.subplots(figsize=(10, 8))
shap.summary_plot(shap_values, X_test, show=False)
plt.tight_layout()
plt.savefig('fig1_shap_summary.png', dpi=300, bbox_inches='tight')

# Figure 2: Single feature dependence
fig, ax = plt.subplots(figsize=(8, 6))
shap.dependence_plot("compound_exposure_days", shap_values, X_test,
                      interaction_index="poverty_rate", show=False)
plt.tight_layout()
plt.savefig('fig2_compound_dependence.png', dpi=300, bbox_inches='tight')
```

## Model Comparison

```python
import pandas as pd
import matplotlib.pyplot as plt

results = pd.DataFrame({
    'Model': ['Random Forest', 'XGBoost', 'LSTM'],
    'RMSE': [12.3, 10.8, 11.5],
    'R-squared': [0.72, 0.78, 0.75]
})

fig, axes = plt.subplots(1, 2, figsize=(12, 5))

axes[0].barh(results['Model'], results['RMSE'], color='#2196F3')
axes[0].set_xlabel('RMSE (lower is better)')
axes[0].set_title('Model Comparison: RMSE')

axes[1].barh(results['Model'], results['R-squared'], color='#4CAF50')
axes[1].set_xlabel('R-squared (higher is better)')
axes[1].set_title('Model Comparison: R-squared')

plt.tight_layout()
plt.savefig('fig3_model_comparison.png', dpi=300, bbox_inches='tight')
```

## Geographic Maps

If your data is spatial (county-level, state-level):

```python
import geopandas as gpd
import matplotlib.pyplot as plt

# Load county shapefile
counties = gpd.read_file('https://www2.census.gov/geo/tiger/GENZ2022/shp/cb_2022_us_county_5m.zip')

# Merge your results with the shapefile
counties['FIPS'] = counties['STATEFP'] + counties['COUNTYFP']
merged = counties.merge(your_results, on='FIPS')

# Plot
fig, ax = plt.subplots(figsize=(14, 8))
merged.plot(column='prediction_error', cmap='RdYlBu_r', legend=True, ax=ax)
ax.set_title('Prediction Error by County')
ax.axis('off')
plt.savefig('fig4_geographic_map.png', dpi=300, bbox_inches='tight')
```

## Using AI for Visualization

In Claude Code or Cursor, with your results file open:

> "I have model results in results.csv with columns [list them]. Create publication-quality figures: (1) a SHAP summary plot, (2) a bar chart comparing model performance, and (3) a geographic map of prediction errors by county. Use matplotlib, save at 300 DPI."

Review every figure. Make sure axis labels, titles, and legends are correct and clear.

## Figure Formatting for Submission

| Element | Standard |
|---------|----------|
| Resolution | 300 DPI minimum |
| Format | PNG or PDF (check venue requirements) |
| Font size | Readable when printed at column width |
| Colors | Colorblind-friendly palettes (use viridis, cividis, or RdYlBu) |
| Labels | Every axis labeled with units |
| Legend | Only if multiple series; place inside plot if space allows |

## Checkpoint

You move to Stage 6 when you have 3-5 figures that clearly communicate your results.
