# Project: Options Arbitrage Backtester

## Overview
This project implements an options arbitrage backtesting strategy using historical SPY options data. It compares Black-Scholes theoretical prices with market prices to identify arbitrage opportunities and tests a trading strategy based on these mispricings.

- **Objective:** Identify and backtest arbitrage opportunities in SPY options using historical volatility and Black-Scholes pricing.
- **Data:** Uses SPY options data (2023) and SPY stock price data from Yahoo Finance via `yfinance`.

## Key Features
- Loads and processes historical SPY options data.
- Calculates historical volatility from SPY stock prices.
- Computes Black-Scholes option prices using historical volatility.
- Identifies call and put option mispricings relative to Black-Scholes prices.
- Implements a trading strategy with entry/exit rules based on mispricing thresholds.
- Uses the `Backtesting.py` framework to simulate historical performance.

## How It Works
1. **Load Data:** Reads SPY options data from a `.parquet` file and SPY stock prices from Yahoo Finance.
2. **Filter Expirations:** Selects the 12th closest expiry date for consistency.
3. **Calculate Volatility:** Computes 30-day historical volatility from SPY stock prices.
4. **Black-Scholes Pricing:** Estimates theoretical call/put prices based on historical volatility.
5. **Identify Arbitrage:** Compares market option prices to theoretical Black-Scholes values.
6. **Backtest Strategy:** Executes trades based on predefined thresholds and evaluates performance.

## Requirements
- Python 3.x
- Libraries: `numpy`, `pandas`, `yfinance`, `scipy`, `backtesting`
- Install dependencies:
  ```sh
  pip install numpy pandas yfinance scipy backtesting
  ```

## Integration into GitHub Portfolio
This project is part of my [Quant-Trading-Portfolio](https://github.com/LTJZ23/Quant-Trading-Portfolio), contributing to research on options pricing inefficiencies and systematic trading strategies.
