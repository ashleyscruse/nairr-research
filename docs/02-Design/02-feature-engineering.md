# Feature Engineering

Raw data is rarely ready for modeling. Feature engineering is the process of creating new variables that better capture the patterns you care about. This is where your domain expertise matters more than any AI tool.

## Types of Engineered Features

### Threshold features
```python
# Days where PM2.5 exceeded EPA standard
df['high_pm25_days'] = (df['daily_pm25'] > 35).groupby('county').sum()
```

### Temporal features
```python
# 7-day rolling average
df['pm25_7day_avg'] = df.groupby('county')['pm25'].transform(lambda x: x.rolling(7).mean())

# Lagged variables
df['pm25_lag_30'] = df.groupby('county')['pm25'].shift(30)
```

### Compound features
```python
# High pollution AND high heat at the same time
df['compound_exposure'] = ((df['daily_pm25'] > 35) & (df['heat_index'] > 105)).astype(int)
```

### Spatial features
```python
# Population density
df['pop_density'] = df['population'] / df['land_area_sq_mi']
```

## Using AI Tools

In Claude Code or Cursor, with your data loaded:

> "Look at the dataframe in data_prep.py. Create compound exposure features that capture when high PM2.5 and high heat index occur simultaneously. Create threshold features, rolling averages, and lag variables."

The AI writes the code. You decide whether the features make scientific sense.

## Which Features Matter?

You will not know until you run SHAP in Stage 4. The publishable finding is often: "The compound feature we engineered ranked higher than any single variable."

## Checkpoint

You should have a feature engineering plan and the code to execute it, even if you have not run it on full data yet.
