# 🌾 USDA WASDE Commodity Forecasting & Time Series Analysis

## Overview

This project explores the **USDA World Agricultural Supply and Demand Estimates (WASDE)** dataset with the goal of building machine learning models capable of forecasting agricultural commodity statistics using historical USDA reports.

The project begins with extensive **Exploratory Data Analysis (EDA)** and data quality assessment before progressing toward feature engineering, time series modeling, and predictive analytics.

Current work is focused on **United States commodity data**, with reproducible analysis pipelines designed to scale to additional commodities and countries.

---

## Objectives

- Understand the structure and quality of the WASDE dataset.
- Identify commodities actively traded on open markets.
- Create a reproducible EDA pipeline for each commodity and attribute.
- Investigate revision patterns within USDA reports.
- Analyze temporal behavior of agricultural variables.
- Engineer features for machine learning models.
- Forecast future commodity values using time series methods.

---

## Dataset

**Source:** USDA World Agricultural Supply and Demand Estimates (WASDE)

Current scope:

- Country: United States
- Multiple commodities
- Multiple agricultural attributes
- Historical monthly releases
- Revision history preserved

Example attributes include:

- Production
- Yield
- Exports
- Imports
- Beginning Stocks
- Ending Stocks
- Domestic Use
- Feed Use
- Food Use
- Seed Use
- Crush
- Price

---

## Project Workflow

```
Raw WASDE Data
        │
        ▼
Data Cleaning
        │
        ▼
Feature Selection
        │
        ▼
Exploratory Data Analysis
        │
        ▼
Commodity-Specific Analysis
        │
        ▼
Feature Engineering
        │
        ▼
Time Series Modeling
        │
        ▼
Forecasting
```

---

## Exploratory Data Analysis

Current EDA includes:

### Dataset Summary

- Dataset dimensions
- Data types
- Missing value analysis
- Descriptive statistics

### Temporal Analysis

- Monthly observations
- Historical trends
- Revision sequences
- Release dates

### Distribution Analysis

- Histograms
- Boxplots
- Outlier detection

### Relationship Analysis

- Commodity comparisons

---

## Reproducible EDA Pipeline

A reusable Python function was developed that performs a complete exploratory analysis for any commodity/attribute combination.

The pipeline automatically generates:

- Dataset summary
- Missing value report
- Summary statistics
- Distribution plots
- Time series visualization
- Outlier analysis
- Revision analysis
- Correlation analysis (where applicable)

This allows identical analyses to be generated for every commodity with minimal code duplication.

Example usage:

```python
run_commodity_attribute_eda(
    df=df_us,
    commodity="Corn",
    attribute="Production",
    report_title="U.S. Feed Grain and Corn Supply and Use"
)
```

---

## Current Findings

### Revision Sequences

One of the most important discoveries so far is that many observations correspond to **multiple revisions** of the same market year.

This explains why naïve time series plots appear to "jump" unexpectedly despite representing the same reporting period.

Future forecasting models will account for these revisions rather than treating them as independent observations.

---

### Commodity Differences

Different commodities exhibit dramatically different:

- Units
- Magnitudes
- Variability
- Seasonal behavior

These differences suggest that commodity-specific preprocessing and modeling may outperform a single global forecasting model.

---

### Open Market Commodities

Current focus is on commodities commonly traded on public markets, including:

- Corn
- Soybeans
- Wheat
- Cotton
- Rice
- Oats
- Barley
- Sorghum

Additional commodities may be analyzed depending on project scope.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

Planned additions:

- Scikit-learn
- XGBoost
- Statsmodels
- LightGBM (optional)

---

## Planned Feature Engineering

Potential features include:

- Lag variables
- Rolling averages
- Rolling standard deviations
- Month
- Year
- Market year
- Revision number
- Time since initial report
- Commodity encoding

---

## Planned Machine Learning Models

Traditional time series:

- ARIMA
- SARIMA
- Exponential Smoothing

Machine learning:

- Random Forest
- XGBoost
- Gradient Boosting

Potential deep learning:

- LSTM
- Temporal Convolutional Networks

---

## Repository Structure

```
wasde_analysis/
├── .venv/                  # Python virtual environment (not tracked)
├── data/
│   ├── raw/                # Original WASDE report exports
│   └── processed/          # Cleaned, analysis-ready CSVs
├── notebooks/
│   └── wasde_eda/                # Exploratory data analysis notebooks
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Future Work

- Complete EDA for all major traded commodities.
- Validate data consistency across report titles.
- Engineer forecasting features.
- Compare statistical and machine learning forecasting methods.
- Evaluate forecasting performance using rolling-origin validation.
- Develop an automated reporting pipeline for commodity analyses.

---

## Author

**Mason Ralls**

B.S. Applied Mathematics  
Computational Statistics & Data Science

This repository documents ongoing work toward building reproducible machine learning workflows for agricultural commodity forecasting using USDA WASDE data.
