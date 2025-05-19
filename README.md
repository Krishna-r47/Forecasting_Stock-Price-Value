
# Forecasting Time Series: (2022–2023)

A data analysis and forecasting project aimed at identifying trends, seasonality, and making future predictions for a univariate time series dataset using Excel-based statistical techniques.



## Problem Statement

To gain insights and forecast values for a given time series dataset spanning from **01-Sep-2022 to 01-Aug-2023**. The analysis includes:

- Exploratory Data Analysis (EDA)
- Data cleaning and preprocessing
- Seasonality and trend detection
- Building two forecasting models
- Evaluating predictions using standard error metrics



## Dataset Description

The time series contains:

- **Date** (format: `dd-mm-yyyy`)
- **Value** (numeric, unitless but assumed to reflect stock price-like behavior)
- **Series ID** (constant)



## Solution Approach

The following steps were undertaken:

1. **EDA**: Summary statistics (mean, median, std dev etc) and visualizations (line charts, boxplots).
2. **Data Cleaning**:
   - Removed invalid negative stock values.
   - Filled missing values using `FORECAST.ETS()` with seasonality detected as **8 months**.
   - Outlier detection using **IQR** on the **residuals** after seasonal decomposition.
3. **Modeling**:
   - **Linear Trend + Seasonality**
   - **Linear Trend + Dummy Variables**
4. **Evaluation Metrics**:
   - **MAD**, **MAPE**, **MSE**, and **Bias**



## Key Visuals

- Line chart showing original values and cleaned data
- Forecast comparisons between linear and seasonal techniques
- Residual boxplot for outlier detection
- Forecasted vs actual values visualization



## Modeling & Evaluation

### Model 1: Linear Trend + Seasonal Index
| Metric | Value      |
|--------|------------|
| MAD    | 11.04      |
| MAPE   | 59.00%     |
| MSE    | 179.67     |
| Bias   | -0.02      |

### Model 2: Linear Trend + Dummy Variables (Seasonality = 8)
| Metric | Value      |
|--------|------------|
| MAD    | 7.99       |
| MAPE   | 42.46%     |
| MSE    | 106.82     |
| Bias   | 0.00       |



## Forecast Output (Sep 2022 – Aug 2023)

| Month | Model 2 Forecast |
|-------|------------------|
| Sep 22 | 56.51            |
| Oct 22 | 62.45            |
| Nov 22 | 63.55            |
| Dec 22 | 72.70            |
| Jan 23 | 82.30            |
| Feb 23 | 85.45            |
| Mar 23 | 84.77            |
| Apr 23 | 74.11            |
| May 23 | 63.84            |
| Jun 23 | 69.78            |
| Jul 23 | 70.87            |
| Aug 23 | 80.03            |



## Insights & Conclusions

- The dataset exhibits **8-month seasonality**.
- There are **cyclical patterns**, but irregularities suggest **external factors** affect values.
- **Dummy variable model** performed better but still had noticeable prediction errors.
- A more advanced model (e.g., ARIMA, Prophet, ML-based regression) would likely improve performance.
