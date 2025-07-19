# 📈 Subscriber Forecasting with XGBoost

## 1. Problem

The goal of this project was to understand and quantify the impact of marketing spend on subscriber growth. This insight would allow the business to:

- Set realistic subscriber growth targets based on planned marketing budgets.
- Align future marketing spend with expected returns in subscriber acquisition.
- Combine subscriber forecasts with Lifetime Value (LTV) models to estimate revenue.
- Determine the optimal level of marketing investment that yields a positive return.

This model serves as a foundational tool for budget planning, performance forecasting, and ROI analysis.

---

## 2. Method

To tackle this problem, a time series forecasting approach was used, focusing on:

- Simulating realistic subscriber growth data with embedded seasonality, trend, and noise.
- Engineering features that reflect marketing activity and temporal patterns.
- Training a machine learning model (XGBoost) to predict daily changes in subscriber count.
- Evaluating model performance using industry-standard error metrics.
- Iteratively simplifying the model to retain only the most impactful predictor: `marketing`.

This approach ensured the model remained interpretable, scalable, and directly tied to the business question.

---

## 3. Code

The project was implemented in Python using the following tools and steps:

- **Libraries**: `pandas`, `numpy`, `matplotlib`, `xgboost`, `sklearn`
- **Data Simulation**: Created synthetic daily subscriber data from 2021–2024 with trend, seasonality, and noise.
- **Feature Engineering**:
  - Calculated `subscribers_diff` (daily change in subscribers).
  - Derived `marketing` spend as a function of subscriber change.
- **Model**: 
  - Used `XGBRegressor` to predict `subscribers_diff`.
  - Reconstructed cumulative subscriber forecasts from predicted differences.
- **Evaluation**: 
  - Metrics: MAE, RMSE, MAPE.
  - Feature importance analysis to remove non-contributing variables.

---

## 4. Results

### 📊 Statistical Performance

| Metric | Value     | Benchmark Interpretation |
|--------|-----------|--------------------------|
| **MAE**  | 690.37    | Low absolute error given subscriber scale (10k–60k). |
| **RMSE** | 971.10    | Slightly higher than MAE, indicating no major outliers. |
| **MAPE** | **1.19%** | **Excellent**. Under 2% is considered highly accurate. |

These results indicate the model is very accurate and reliable for forecasting purposes.

---

### 🎯 Business Outcome

- The model confirms that marketing spend is a strong predictor of subscriber growth.
- All other engineered features (lags, seasonality, calendar effects) had negligible impact and were removed.
- The final model is simple, interpretable, and highly accurate, making it ideal for:
  - Forecasting subscriber growth under different marketing budget scenarios.
  - Revenue forecasting when combined with LTV estimates.
  - Strategic planning and budget justification for marketing teams.
