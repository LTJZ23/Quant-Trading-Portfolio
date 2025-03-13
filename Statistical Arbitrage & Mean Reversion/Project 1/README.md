Mean Reversion Pairs Trading Strategy

📌 Overview
This project contains a backtesting framework for a Mean Reversion Pairs Trading Strategy using historical stock price data. The strategy assumes that the spread between two correlated stocks follows a mean-reverting process, and trades are executed when the spread deviates significantly from its mean.

🏗 Strategy Breakdown
1. Data Collection
Download daily closing prices for two correlated stocks (e.g., JPM and BAC) using yfinance.
Clean and preprocess data by handling missing values.

2. Hedge Ratio & Cointegration Test
Calculate the hedge ratio (β) using Ordinary Least Squares (OLS) regression.
Check if the residual spread is stationary (cointegration test via Augmented Dickey-Fuller test).

3. Mean Reversion Model
Compute the rolling hedge ratio with a 100-day window.
Define the spread: Spread = Price_A - β * Price_B.
Calculate a Z-score to standardize the spread and identify trading signals.

4. Trading Logic
Entry Signal:
Buy the spread (long Stock A, short Stock B) when Z-score < -2.
Sell the spread (short Stock A, long Stock B) when Z-score > 2.

Exit Signal:
Close the position when the Z-score returns within -0.5 to 0.5.

Risk Management:
Stop-loss at 3% of initial capital.
Transaction costs of 0.1% per trade.

5. Performance Metrics
Sharpe Ratio
Win Rate (%)
Maximum Drawdown (%)
Final Profit & Loss (PNL)

📊 Visualization
Scatter Plot of stock prices with OLS regression line.
Residuals Plot to confirm spread stationarity.

🔧 Requirements
Install dependencies using:
pip install numpy pandas yfinance statsmodels matplotlib

🚀 Usage
Run the Python script to execute the backtest:

📌 Future Enhancements
Implement risk on portfolio position sizing based for more realistic trading entry sizes. 
Add rolling Z-score for adaptive signal detection.


📊 Sample Output
[*********************100%***********************]  2 of 2 completed
Before cleaning: 0 NaNs in BAC
After cleaning: 2516 rows remaining
✅ JPM : Non-Stationary (p-value : 0.9082)
✅ BAC : Non-Stationary (p-value : 0.5792)
❌ Stocks are Not Cointegrated | (p-value :0.9531)

🟢 Enter LONG Spread at 21.43 on 2014-05-28  | JPM : 41.28 | BAC:  12.13 | Z Score : -8.13
🚀 EXIT trade at 16.57 on 2014-10-20 | JPM: 42.74, BAC: 13.08 | PNL: -0.57 | Z Score : -0.41
🔴 Enter SHORT Spread at 27.68 on 2015-03-30  | JPM : 46.30 | BAC:  12.56 | Z Score : 2.15

Final PNL : 19.21 | Sharpe Ratio : 0.19 | Max DD : -0.02% | WinRate : 54.17%

