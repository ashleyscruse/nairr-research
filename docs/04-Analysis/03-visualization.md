# Visualization

## Figures Every Paper Needs

| Figure | What It Shows | When to Use |
|---|---|---|
| SHAP summary plot | Which features matter most | Always |
| Model comparison chart | How models compare on metrics | Multiple models |
| Confusion matrix | Where the model makes mistakes | Classification |
| Geographic map | Spatial patterns | Spatial data |
| Time series plot | Trends over time | Temporal data |

## Using AI to Generate Figures

In Claude Code or Cursor:

> "I have SHAP values in results/shap_values.npy and test features in data/processed/X_test.csv. Generate a SHAP summary plot. Save at 300 DPI to figures/fig1_shap.png. Colorblind-friendly palette."

> "Create a bar chart comparing Random Forest and XGBoost on RMSE and R-squared from results/metrics.json. Save to figures/fig2_comparison.png."

Review every figure. AI gets the structure right but may mislabel axes.

## Publication Quality Checklist

- [ ] 300 DPI minimum
- [ ] Every axis labeled with units
- [ ] Font readable at column width
- [ ] Colorblind-friendly (viridis, cividis, RdYlBu)
- [ ] Legend only if needed
- [ ] Descriptive title
- [ ] Saved as PNG or PDF

## Checkpoint

You should have 3-5 figures that clearly communicate your results.
