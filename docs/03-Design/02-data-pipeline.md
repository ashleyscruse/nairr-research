# Stage 3: Feature Engineering

## Learning Objectives

By the end of this session, you will be able to:

- Transform raw data into features that improve model performance
- Create interaction and compound features that capture relationships between variables
- Understand why feature engineering is where domain expertise matters most

## What is Feature Engineering?

Raw data is rarely ready for modeling. Feature engineering is the process of creating new variables from existing ones that better capture the patterns you care about.

This is where your domain expertise matters more than any AI tool. You know your field. You know which relationships are interesting. The AI can write the code, but you decide what to compute.

## Types of Engineered Features

### Threshold features

Turn continuous values into binary indicators:

```python
# Days where PM2.5 exceeded the EPA standard
df['high_pm25_days'] = (df['daily_pm25'] > 35).groupby('county').sum()

# Heat wave indicator (consecutive days above 95F)
df['heat_wave'] = (df['max_temp'] > 95).rolling(3).sum() >= 3
```

### Temporal features

Capture patterns over time:

```python
# 7-day rolling average of air quality
df['pm25_7day_avg'] = df.groupby('county')['pm25'].transform(
    lambda x: x.rolling(7).mean()
)

# Lagged variables (last month's pollution predicting this month's health)
df['pm25_lag_30'] = df.groupby('county')['pm25'].shift(30)

# Seasonal indicators
df['summer'] = df['month'].isin([6, 7, 8]).astype(int)
```

### Compound features

Capture the interaction between multiple variables. This is where novelty lives.

```python
# Compound exposure: high pollution AND high heat at the same time
df['compound_exposure'] = (
    (df['daily_pm25'] > 35) & (df['heat_index'] > 105)
).astype(int)

# Compound intensity: how bad is the combination?
df['compound_intensity'] = df['daily_pm25'] * df['heat_index']
df.loc[~df['compound_exposure'], 'compound_intensity'] = 0

# Count of compound exposure days per county per year
df['compound_days_annual'] = df.groupby(['county', 'year'])['compound_exposure'].sum()
```

### Spatial features

Capture geographic context:

```python
# Distance to nearest EPA monitor
df['monitor_distance_km'] = haversine(df['county_lat'], df['county_lon'],
                                       df['monitor_lat'], df['monitor_lon'])

# Population density
df['pop_density'] = df['population'] / df['land_area_sq_mi']
```

## Using AI Tools for Feature Engineering

This is where file-aware AI tools earn their keep. Instead of writing every transformation by hand:

**In Claude Code or Cursor:**

> "Look at the dataframe I loaded in data_prep.py. The columns are [list them]. I want to create compound exposure features that capture when high PM2.5 and high heat index occur simultaneously. Create threshold features, rolling averages, and lag variables. Write the code."

The AI writes the code. You review whether the features make scientific sense.

## Which Features Matter?

You will not know which features matter until you run your models. That is what Stage 5 (Analysis) is for. SHAP values will tell you which engineered features actually improved the model.

The publishable result is often: "The compound exposure feature we engineered ranked higher in importance than any single stressor, suggesting that the interaction between pollutants and heat is more predictive than either alone."

## Checkpoint

You move to Stage 4 when you have a feature engineering plan and the code to execute it (even if you have not run it on full data yet).
