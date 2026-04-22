# Metrics Reference

Keep this open while reviewing your results.

## Regression (predicting a number)

| Metric | What It Tells You | Good | Watch Out |
|---|---|---|---|
| **R-squared** | % of variation your model explains | Above 0.7 | R-squared of 0.99 = probably data leakage |
| **RMSE** | Average error size (same units as outcome) | Much smaller than your outcome's std dev | Compare to mean of your outcome |
| **MAE** | Average absolute error, less sensitive to outliers | Lower than RMSE | If MAE is much less than RMSE, you have big outliers |

## Classification (predicting a category)

| Metric | What It Tells You | Good | Watch Out |
|---|---|---|---|
| **Accuracy** | % correct | Above 85% | Misleading if classes are imbalanced |
| **Precision** | "When the model says yes, how often is it right?" | Above 80% | High precision + low recall = too cautious |
| **Recall** | "Of all real cases, how many did it catch?" | Above 80% | High recall + low precision = too many false alarms |
| **F1** | Balance of precision and recall | Above 0.75 | Use when both false positives and negatives matter |
| **AUC-ROC** | How well the model separates classes | Above 0.85 | Always report for binary classification |

## Reading SHAP Plots

### Summary Plot
- **Top to bottom:** Features ranked by importance
- **Left/right position:** How much the feature pushed predictions down (left) or up (right)
- **Color:** Red = high value of the feature, Blue = low value
- **Wide spread:** Feature has strong, variable effect
- **Tight cluster near zero:** Feature does not matter

### Dependence Plot
- **Upward trend:** Higher values increase predictions
- **Flat line:** Feature does not matter
- **Nonlinear:** Effect changes at certain thresholds

## Red Flags

| What You See | What It Means |
|---|---|
| R-squared of 0.99 | Data leakage or a bug |
| 95% accuracy on imbalanced data | Model just predicts majority class |
| Train 98%, test 60% | Overfitting |
| All SHAP values near zero | Your features don't predict the outcome |
| One feature dominates | Check for leakage |
