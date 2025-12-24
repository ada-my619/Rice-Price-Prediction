# Rice Price Time Series Forecasting (Indonesia)

This repository explores time series forecasting of Indonesian rice prices using both statistical models (ARIMA) and machine learning models (XGBoost).
The project focuses on understanding price dynamics, regime shifts, and macroeconomic drivers using interpretable feature engineering and robust evaluation methods.

## Project Objectives

- Analyze the temporal behavior of rice prices at the provincial level (e.g. DKI Jakarta
- Compare ARIMA and XGBoost for short-term price forecasting
- Design feature engineering that captures:
  - price inertia
  - momentum and mean reversion
  - volatility and shocks
- Incorporate exogenous macro variables (e.g. crude oil, FX) as cost-pressure indicators
- Evaluate models under realistic time-series cross-validation
- Interpret model behavior using SHAP values and residual diagnostics

## Data Description
- Target variable
  - Daily rice price (IDR/kg), indexed by date
- Derived features
  - Price lags
  - Price differences (Δprice)
  - Rolling means and rolling volatility
  - Shock and normalized shock indicators
- Optional exogenous variables
  - Crude oil prices (transformed)
  - USD/IDR exchange rate (transformed)
 
## Key Findings
- Rice prices exhibit strong inertia and local trend dependence
- XGBoost outperforms ARIMA within stable regimes
- Large forecast errors coincide with structural breaks and policy-driven shocks
- Adding crude oil features improves residual behavior by capturing cost-push pressure
- FX and oil act as secondary regime modifiers, not primary drivers
- Residuals are heavy-tailed, which is expected for commodity prices
- SHAP analysis confirms:
    - Lagged price and rolling means dominate predictions
    - Macro variables condition the regime rather than drive prices directly

## Dependencies
Main libraries used:
- `pandas`
- `numpy`
- `matplotlib`
- `statsmodels`
- `xgboost`
- `scikit-learn`
- `shap`
