# Options misprice detection and delta neutral strategy simulator

Overview

This project builds a system to identify underpriced call options using the Black-Scholes model and historical volatility spreads. Upon detecting a potential mispricing, it simulates buying the call option and delta-hedging the position with the underlying stock to remain market-neutral. The goal is to exploit pricing inefficiencies while minimizing market risk.

This strategy was simulated using a $1,000,000 portfolio, generating an estimated return of approximately 8.25% as of April 18th, 2025. 

Highlights :

1. Options Mispricing Detection:
2. Calculate theoretical call option prices using the Black-Scholes model.
3. Compare theoretical prices with market prices from Yahoo Finance API.
4. Select options where market price < 90% of theoretical price.
5. Volatility Spread Condition:
6. Validate trades only when Implied Volatility (IV) is less than Historical Volatility (HV) over the last 30 trading days, supporting the mispricing hypothesis.
7. Active Risk Management - Compute delta of the bought call option using Black-Scholes Greeks.

Tech Stack : 
Python 
Numpy
Pandas
Matplotlib
yfinance (market data)
SciPy (for Black-Scholes model)

Trading Strategy :

Step 1: Scan available call options via yfinance.

Step 2: Calculate theoretical price using Black-Scholes (with risk_free_rate = 5%). Find options where theoretical Price ≥ 4 × Market Price (mispricing_margin)

Step 3: Make sure Implied Volatility (IV) is at least 50% lower than Historical Volatility (HV) 

Step 4: Further filter: Only consider options with a price > $1 and IV < 5.0 (500%). 

Step 5: Only consider options that expire within 180 days.

Step 6: Once all conditions match, buy the call option.
	
Step 7: Short (sell) delta × underlying shares to make the position delta-neutral.

Step 6: Hold and adjust hedges if needed during holding period.

Results : Assuming, these mispriced options converge to their theoritical prices, we calculate estimated PnL which as of April 18th, 2025 is estimated 8.25%. 

Work in Progress

1. Automating live options data collection using Polygon.io API to backtest this strategy.
2. Enhancing backtesting with transaction costs, and margin requirements.
3. Expanding to put options.
4. Building a live trading simulator for paper trading and further validation.
