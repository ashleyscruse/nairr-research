# Interpreting Results

## Before You Interpret: Verify

- [ ] Data joins are clean (no duplicated rows)
- [ ] Train/test split does not leak information
- [ ] Models trained without errors
- [ ] Baseline produces reasonable results (99% accuracy = something is wrong)

## Five Questions to Answer

### 1. What did you find?
State the main result in one sentence with numbers. Not "the model performed well" but "XGBoost achieved an R-squared of 0.78 on the test set."

### 2. Does it answer your question?
Go back to your Research Brief. Read your question. Does the result address it directly?

### 3. Does it fill the gap?
Read your gap statement. If you said "nobody has studied compound stressors," and SHAP shows the compound feature matters most, that is your contribution.

### 4. How does it compare to existing work?
Pull numbers from your literature review. "Prior studies reported R-squared of 0.55-0.65. Our model achieved 0.78."

### 5. What can't you claim?

| Limitation | Example |
|---|---|
| Geographic scope | "May not generalize beyond the states studied" |
| Temporal resolution | "Annual data cannot capture short-term effects" |
| Ecological fallacy | "County-level associations are not individual-level causation" |
| Data quality | "Suppressed counts may bias rural estimates" |
| Model limitations | "Correlation does not imply causation" |

## Activity

Write 2-3 paragraphs interpreting your results. Include your main finding, how it connects to the gap, and at least two limitations. This becomes your Results and Discussion sections.
