# Technical Indicator-Based Portfolio Strategy

This project implements and evaluates simple technical indicator-based trading strategies (SMA, EMA, RSI, MACD, Bollinger Bands) to construct quarterly rebalanced portfolios. 

The strategies are benchmarked against the SPY ETF over the period from **May 2022 to May 2025**.

## Objectives

- Build a backtesting framework for quarterly rebalanced portfolios.
- Generate trading signals using different technical indicators.
- Evaluate portfolio performance relative to the SPY benchmark.

## Strategy Summary

- **Indicators used**:  
  - Simple Moving Average (SMA)  
  - Exponential Moving Average (EMA)  
  - Relative Strength Index (RSI)  
  - Moving Average Convergence Divergence (MACD)  
  - Bollinger Bands (BB)

- **Signal Logic**:  
  - Generate buy/sell/hold signals based on indicator-specific logic.  
  - Adjust portfolio weights by ±3% per stock each quarter depending on the signal.  
  - Normalise weights to sum to 1 on each rebalance date.

- **Rebalance Frequency**:  
  - Quarterly, on the **3rd Friday of March, June, September, and December** to align with S&P's rebalancing dates.

## Key Findings (May 2022 – July 2025)

- From **May 2022 to May 2024**, **MACD** and **Bollinger Bands** outperformed the SPY benchmark in cumulative returns.
- After **May 2024**, the **SPY benchmark began to outperform all strategies**.
- Among all indicators:
  - **MACD** showed the most consistent outperformance early on but converged with SPY after mid-2024.
  - **Bollinger Bands** remained the **second-best** performing strategy.
  - **SMA**, **EMA**, and **RSI** trailed behind in cumulative return.
- As expected, **no single technical indicator consistently outperforms** across all market regimes.

## Visualisation

Cumulative returns of all indicator strategies compared to SPY:
- Please refer to Visualisations in https://github.com/samsea18/ta-analysis/blob/main/ta-analysis/notebooks/POC%20Script.ipynb 

## Future Work

- Package POC into kedro application.
- API development on top of kedro application.
- Incorporate more advanced indicators (e.g. ATR, Stochastic Oscillator).
- Combine signals using ensemble or voting logic.
- Explore machine learning classifiers trained on technical indicators.
- Include short positions, transaction costs and slippage in the backtest.
