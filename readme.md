# Drought Data Analysis and Visualization

This project involves analyzing and visualizing global drought data to understand patterns, trends, and relationships among drought-related variables.

## Project Overview

The dataset contains information about various drought episodes, including:

- **Severity (km²)**: Area affected by drought.
- **Duration (days)**: Length of the drought episode.
- **Alertscore**: Severity alert score for the drought.
- **Episodealertscore**: Combined alert score for the drought episode.

The main goal is to perform exploratory data analysis (EDA) and visualizations to extract meaningful insights.

---

## Installation

Ensure Python (>=3.8) is installed along with the following libraries:

```bash
pip install pandas matplotlib seaborn
```

---

## Data Exploration

Perform initial exploration to understand the dataset:

```python
import pandas as pd

# Load the dataset
drought_df = pd.read_csv("path_to_your_drought_data.csv")

# Display first few rows
print(drought_df.head())

# Summary statistics
print(drought_df.describe())

# Data types and null values
print(drought_df.info())

# Frequency counts for categorical columns
print(drought_df['column_name'].value_counts())
```

---

## Visualization

Use `matplotlib` and `seaborn` for plotting:

### Histograms & Boxplots

```python
import matplotlib.pyplot as plt
import seaborn as sns

cols = ['Severity (km2)', 'Duration (days)', 'Alertscore', 'Episodealertscore']

# Histograms
for col in cols:
    plt.figure(figsize=(6,4))
    sns.histplot(drought_df[col], kde=True, bins=20)
    plt.title(f"Histogram of {col}")
    plt.show()

# Boxplots
for col in cols:
    plt.figure(figsize=(6,4))
    sns.boxplot(y=drought_df[col])
    plt.title(f"Boxplot of {col}")
    plt.show()
```

### Scatterplots & Pairplots

```python
# Pairplot
sns.pairplot(drought_df[cols])
plt.show()
```

### Heatmap

```python
plt.figure(figsize=(8,6))
sns.heatmap(drought_df[cols].corr(), annot=True, cmap='coolwarm')
plt.title("Correlation Heatmap")
plt.show()
```

---

## Analysis Goals

- Identify relationships and trends between variables
- Detect outliers and unusual patterns
- Compare distributions across different metrics
- Summarize insights from each visual

---

## Observations

Write notes for each plot describing:

- Skewness in distributions
- Strong or weak correlations
- Outliers
- Patterns in scatterplots

---

## Summary of Findings

Highlight key trends observed in the data, e.g.:

- Severity and Duration are positively correlated
- Alert scores are higher for larger affected areas
- Patterns observed in scatterplots indicate potential clusters or anomalies

---
