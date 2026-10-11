A reproducible data science pipeline that forecasts how mortgage affordability in New York City will evolve over the next 10 years, driven by inflation and median household income trends.

The project pulls public macroeconomic data — 30-year mortgage rates, CPI for the NY metro area, and median household income — from the FRED API (with Zillow home value data optional), then engineers a core metric called the Affordability Ratio: the share of monthly income a typical household would spend on a mortgage payment. This ratio is forecasted 10 years forward using a SARIMAX model with inflation and income as exogenous regressors, validated with walk-forward (expanding window) testing rather than a random train/test split, since random splits leak future information into time-series models.

Key features:

End-to-end pipeline: data ingestion → preprocessing → modeling → evaluation, each as a standalone script
Runs without an API key: falls back to bundled sample data so the pipeline works out of the box
Interactive dashboard: a Streamlit app lets users explore historical and forecasted affordability trends, or plug in their own income and target home price for a personalized projection
Rigorous validation: walk-forward testing with MAE/MAPE metrics, documented assumptions, and a limitations section covering data granularity and model constraints
CI pipeline: GitHub Actions runs tests automatically on every push

Tech stack: Python, pandas, statsmodels (SARIMAX), scikit-learn, Streamlit, FRED API.
