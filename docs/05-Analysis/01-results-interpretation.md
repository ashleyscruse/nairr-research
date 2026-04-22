# Stage 5: Interpreting Results

## Learning Objectives

By the end of this session, you will be able to:

- Evaluate model performance using appropriate metrics
- Interpret what your results mean in the context of your research question
- Identify limitations and articulate what your results do and do not show

## Before You Interpret: Verify Your Pipeline

**The hard line between Stage 4 and Stage 5:** Do not interpret results until you have verified that:

- [ ] Your data joins are clean (no duplicated rows, no mismatched keys)
- [ ] Your train/test split does not leak information (no future data in training set)
- [ ] Your models trained without errors (check logs)
- [ ] Your baseline model produces reasonable results (if Random Forest gives 99% accuracy, something is wrong)

Bad inputs produce bad results no matter how good your interpretation is.

## Model Performance Metrics

Choose metrics based on your task:

### Regression (predicting a continuous value)

| Metric | What It Tells You | When to Use |
|--------|-------------------|-------------|
| RMSE | Average magnitude of error | When large errors matter more |
| MAE | Average absolute error | When all errors matter equally |
| R-squared | How much variance your model explains | Always report alongside RMSE/MAE |

### Classification (predicting a category)

| Metric | What It Tells You | When to Use |
|--------|-------------------|-------------|
| Accuracy | % of correct predictions | Only when classes are balanced |
| Precision | Of predicted positives, how many are correct | When false positives are costly |
| Recall | Of actual positives, how many did you catch | When false negatives are costly |
| F1 | Balance of precision and recall | When you care about both |
| AUC-ROC | How well the model separates classes | Always report for binary classification |

## Interpreting Feature Importance (SHAP)

SHAP (SHapley Additive exPlanations) values tell you how much each feature contributed to each prediction. This is often the most publishable part of your analysis.

```python
import shap

explainer = shap.TreeExplainer(model)
shap_values = explainer.shap_values(X_test)

# Summary plot: which features matter most?
shap.summary_plot(shap_values, X_test)

# Dependence plot: how does one feature affect predictions?
shap.dependence_plot("compound_exposure_days", shap_values, X_test)
```

### What to look for in SHAP results

- **Which features rank highest?** If your novel engineered features (e.g., compound exposure) rank above standard features (e.g., PM2.5 alone), that supports your hypothesis.
- **Direction of effect:** Does increasing the feature increase or decrease the predicted outcome? Does that make scientific sense?
- **Interactions:** Do SHAP interaction plots reveal relationships between features that the raw data does not show?

## Connecting Results to Your Research Question

Answer these questions in writing:

1. **What did you find?** State the main result in one sentence.
2. **Does it answer your research question?** Directly address the question from Stage 1.
3. **How does it compare to existing work?** Connect back to your literature review from Stage 2.
4. **What does it mean practically?** Who cares about this result and why?
5. **What are the limitations?** Be honest about what your results cannot tell us.

### Common limitations to acknowledge

- Limited geographic scope (your results may not generalize to other regions)
- Temporal resolution (annual data cannot capture short-term effects)
- Ecological fallacy (county-level associations do not imply individual-level causation)
- Data quality (suppressed cells, missing monitors, measurement error)
- Model limitations (correlation is not causation, even with ML)

## Activity

Write 2-3 paragraphs interpreting your results. Include:
- Your main finding
- How it connects to the gap you identified
- At least two limitations

This becomes the Results and Discussion section of your paper.

## Checkpoint

You move to Stage 6 when you can clearly state what you found, why it matters, and what the limitations are.
