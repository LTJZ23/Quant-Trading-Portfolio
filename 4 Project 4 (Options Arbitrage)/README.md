# Options Arbitrage Tracker
A Python script to track arbitrage opportunities in TSLA options using Black-Scholes and Geometric Brownian Motion (GBM) models.

## Status
Version 0.1 - Work in Progress. Currently a live tracker; backtesting to be added later.

## Features
- Fetches TSLA stock and options data via yFinance.
- Calculates theoretical prices using Black-Scholes and GBM (Monte Carlo simulation).
- Generates BUY/SELL signals if market price differs from theoretical by >20%.
- Sets stop-loss (SL) at 30% below (buy) or above (sell) entry price.
- Logs trade signals to `Trade_Log.csv`.

## Requirements
- Python 3.x
- Libraries: `numpy`, `pandas`, `yfinance`, `scipy`

## Setup
1. Install dependencies:
   pip install numpy pandas yfinance scipy