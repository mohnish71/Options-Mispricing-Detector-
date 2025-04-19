# Options misprice detection and delta neutral strategy simulator

Overview

This project builds a system to detect underpriced call options based on the Black-Scholes model and historical volatility spreads.
Upon finding mispriced options, it simulates buying the call option and delta-hedging by shorting the underlying stock to maintain market neutrality.

The strategy was simulated using a $1,000,000 portfolio, generating an estimated return of 8.25% as of April 18, 2025.

Highlights :

1. Collects options data using yfinance.
2. Calculate theoretical call option prices using the Black-Scholes model.
3. Compare theoretical prices with market prices from Yahoo Finance API.
4. Select options where market price < theoretical price with defined parameters.
5. Volatility Spread Condition 
6. Validate trades only when Implied Volatility (IV) is less than Historical Volatility (HV) over the last 30 trading days, supporting the mispricing hypothesis.
7. Active Risk Management - Compute delta of the bought call option using Black-Scholes Greeks.
8. Automatic risk managed position sizing usimg 1 Million Dollars of assumed capital. 

For full explnation of trading strategy please refer to Technical_strategy.md file in this repository. 

Tech Stack : 

Python 
Numpy
Pandas
Matplotlib
yfinance (market data)
SciPy (for Black-Scholes model)

Work in Progress

1. Automating live options data collection using Polygon.io API to backtest this strategy.
2. Enhancing backtesting with transaction costs, and margin requirements.
3. Expanding to put options.
4. Building a live trading simulator for paper trading and further validation.

Author : Mohnish Gautam

