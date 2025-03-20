# Project 5: Volatility Arbitrage - Delta Neutral Trading Strategy

## Overview
This project implements a delta-neutral volatility arbitrage strategy using options data for SPY (S&P 500 ETF). It compares Historical Volatility (HV) to Implied Volatility (IV) to identify mispriced options, then suggests trades with Take Profit (TP) and Stop Loss (SL) levels.

- **Objective**: Exploit differences between HV and IV for profit while maintaining delta neutrality.
- **Data**: Fetches stock and options data from Yahoo Finance via `yfinance`.
- **Key Features**:
  - Calculates HV and Annual Drift from historical prices.
  - Uses Newton-Raphson method to derive IV from option prices.
  - Sets TP at option prices when HV shifts by ±2% (absolute) and SL at 70% (longs) or 130% (shorts) of entry price.

## How It Works
1. Downloads SPY closing prices and ATM options data.
2. Computes 30-day HV and 252-day Annual Drift.
3. Estimates IV using Black-Scholes and Newton-Raphson iteration.
4. Identifies arbitrage opportunities when |HV - IV| > 10%.
5. Prints trade recommendations with TP/SL levels and stock hedging requirements.

## Requirements
- Python 3.x
- Libraries: `numpy`, `pandas`, `yfinance`, `scipy`

Install dependencies:
pip install numpy pandas yfinance scipy