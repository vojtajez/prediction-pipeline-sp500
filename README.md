# S&P 500 Prediction Pipeline

An automated data pipeline that fetches S&P 500 market data, calculates technical indicators, and generates daily price movement predictions using machine learning models.

## Features

- **Automated Data Collection**: Fetches daily market data for all S&P 500 components from Yahoo Finance (via `finfetcher`).
- **Technical Analysis**: Calculates indicators like RSI, MACD, Bollinger Bands, ATR, and more using `pandas-ta`.
- **Machine Learning**: Implements a classification model (Decision Tree) to predict daily returns.
- **Database Integration**: Stores historical market data, predictions, and model evaluations in a PostgreSQL database.
- **Daily Execution**: Configured with GitHub Actions to run every day at 00:00 UTC.
- **Evaluation Loop**: Automatically evaluates previous predictions as new market data becomes available.

## Prerequisites

- Python 3.10+
- PostgreSQL database
- (Optional) GitHub account for automated daily runs

## Usage

To run the pipeline manually:

```bash
python main.py
```

The pipeline will:
1. Fetch the latest list of S&P 500 tickers.
2. For each ticker, fetch historical data and calculate technical features.
3. Save new market data to the database.
4. Evaluate any pending predictions from previous days.
5. Generate and save new predictions for the next trading day.
