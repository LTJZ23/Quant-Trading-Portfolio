# Project: Options Arbitrage Backtester

## Overview
This project backtests an options arbitrage strategy using historical SPY options data. It compares Black-Scholes theoretical prices with market prices to find arbitrage opportunities.

- **Objective:** Identify and test arbitrage opportunities in SPY options.
- **Data:** SPY options (2023) + SPY stock price data from Yahoo Finance.

## Key Features
- Loads and processes historical SPY options data.
- Calculates 30-day historical volatility.
- Computes Black-Scholes option prices.
- Identifies mispriced call/put options.
- Backtests a trading strategy using `Backtesting.py`.

## How It Works
1. **Load Data:** Reads SPY options data (`.parquet`) + SPY stock prices.
2. **Filter Expirations:** Uses the 12th closest expiry date.
3. **Calculate Volatility:** Computes 30-day historical volatility.
4. **Black-Scholes Pricing:** Estimates theoretical call/put prices.
5. **Identify Arbitrage:** Compares market vs. theoretical prices.
6. **Backtest Strategy:** Trades based on predefined mispricing rules.

## Requirements
- Python 3.x
- Install dependencies:
  ```sh
  pip install numpy pandas yfinance scipy backtesting

## Data Source
- DSPY Option Chain Data (2023) - https://www.optionsdx.com/product/spx-option-chain/