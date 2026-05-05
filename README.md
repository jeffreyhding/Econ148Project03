# Econ 148 Project 3

---

## Assignment Description

### Track A Option 3: State Unemployment Insurance Claims Forecasting

Forecast weekly initial unemployment insurance claims for three to five US states using FRED’s state-level claims series (e.g., CAICLAIMS, TXICLAIMS, NYICLAIMS, FLICLAIMS, MIICLAIMS), accessed via `fredapi` with a free API key. Augment with state-level Google Trends data for unemployment-related search terms, pulled via the `pytrends` package and cached to CSV for reproducibility. 

**Baseline:** ARIMA or OLS with lagged claims and seasonal dummies. 

**ML comparison:** gradient boosting (XGBoost or LightGBM) or a small LSTM. Groups must explicitly address how they handle the COVID structural break, and should pick states with contrasting labor market structures (e.g., a tech-heavy state, a manufacturing state, a tourism-dependent state) to compare model performance across contexts.

---

## Project Summary

For this project, we forecast weekly initial unemployment insurance claims for four states with contrasting labor market structures: California, New York, Indiana, and Hawaii. We use FRED state-level claims series as the main outcome data and augment the analysis with Google Trends search interest for unemployment-related terms: "unemployment", "unemployment benefits", "file for unemployment", "unemployment office", and "apply for unemployment".

Our baseline model is ARIMA, which provides a simple time-series benchmark using only past claims values. We then compare this baseline against SARIMAX models that include engineered time-series features such as Fourier seasonality terms, COVID-period indicators, and Google Trends data. We also compared against LightGBM models using lagged claims and rolling averages.

To address the COVID structural break, we include explicitly-defined COVID-period indicators in the SARIMAX feature set and allow machine learning models to learn from lagged and rolling post-COVID patterns. We evaluate model performance separately by state and select a final model for each state rather than assuming that one model performs best everywhere.

The final notebook includes, for all four states: exploratory data analysis, feature construction, model tuning, model comparison, and future forecasts for select models.

---

## Reproducibility

If you would like to run our code yourself, clone this repository using GitHub Desktop or download it as a ZIP file, then open it in your IDE of choice.

Our finalized Jupyter notebook is located at `Final/Econ148Proj03.ipynb`. You will need the files in `Final/Data` to run the notebook. The files in `Final/Model_Cache` and `Final/CAICLAIMS_Model_Cache` allow you to bypass the model parameter tuning grid searches, which can take several hours to run.

A rendered PDF version of the notebook is located at `Final/Econ148Proj03.pdf`.
