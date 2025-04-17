# Options-Mispricing-Detector

This project analyse U.S. stocks and detects underpriced and overpriced options using the Black-Scholes pricing model along with Implied Volatility (IV) and Historical Volatility (HV) spread analysis. 

Stocks : The strategy currently focuses on TSLA, NVDA, AAPL, and MSFT. These are highly liquid stocks with active options markets.

Risk-Free Rate : Set at 5% (0.05) to match US Treasury rates.

IV-HV Spread Threshold : A minimum difference of 50% (0.5) between implied volatility (IV) and historical volatility (HV). 

Mispricing Margin : Only options where the theoretical price exceeds the market price by at least $4.00 are considered. 

Minimum Option Price: Options priced below $1.00 are excluded to avoid illiquid, low-quality contracts.

Maximum Expiry: Options expiring within 180 days are considered.

Upon detecting a mispricing, the system applies a position sizing strategy using delta hedging and calculates estimated returns on a $1 million portfolio.

Currently, I am working on adding a live backtest on this strategy to make this detector actually implementable in live markets. 


