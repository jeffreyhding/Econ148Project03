# Econ 148 Project 3

## State Unemployment Insurance Claims Forecasting

Forecast weekly initial unemployment insurance claims for three to five US states using FRED’s state-level claims series (e.g., CAICLAIMS, TXICLAIMS, NYICLAIMS, FLICLAIMS, MIICLAIMS), accessed via fredapi with a free API key. Augment with state-level Google Trends data for unemployment-related search terms, pulled via the pytrends package and cached to CSV for reproducibility. Baseline: ARIMA or OLS with lagged claims and seasonal dummies. ML comparison: gradient boosting (XGBoost or LightGBM) or a small LSTM. Groups must explicitly address how they handle the COVID structural break, and should pick states with contrasting labor market structures (e.g., a tech-heavy state, a manufacturing state, a tourism-dependent state) to compare model performance across contexts.
