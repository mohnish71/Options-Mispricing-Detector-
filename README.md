# Options-Mispricing-Detector

This project analyse U.S. stocks and detects underpriced and overpriced options using the Black-Scholes pricing model along with Implied Volatility (IV) and Historical Volatility (HV) spread analysis. 

Project Description

The Options Mispricing Detector is a Python-based system that:
	•	Calculates the theoretical fair value of stock options using the Black-Scholes pricing model.
	•	Computes and compares Implied Volatility (IV) and Historical Volatility (HV).
	•	Flags options as potentially undervalued or overvalued based on:
	•	Black-Scholes mispricing
	•	IV-HV spread analysis
	•	Incorporates position sizing logic based on the strength of mispricing, helping in creating a portfolio with better risk management.

Parameters 

-Stocks : The strategy currently focuses on TSLA, NVDA, AAPL, and MSFT. These are highly liquid stocks with active options markets.
-Risk-Free Rate : Set at 5% (0.05) to match US Treasury rates.
-IV-HV Spread Threshold : A minimum difference of 50% (0.5) between implied volatility (IV) and historical volatility (HV). 
-Mispricing Margin : Only options where the theoretical price exceeds the market price by at least $4.00 are considered. 
-Minimum Option Price: Options priced below $1.00 are excluded to avoid illiquid, low-quality contracts.
-Maximum Expiry: Options expiring within 180 days are considered.

Key Concepts and Methodology
 • Black-Scholes Model: A mathematical model used to calculate the theoretical value of European-style options based on inputs like underlying price, strike price, time to expiry, risk-free interest rate, and volatility.
	•	Implied Volatility (IV): The market’s forecast of a likely movement in an asset’s price. Higher IV generally increases an option’s premium.
	•	Historical Volatility (HV): A measure of how much the stock price fluctuated in the past (e.g., 30-day rolling standard deviation of returns).
	•	IV-HV Spread Logic:
	•	If Implied Volatility (IV) is significantly higher than Historical Volatility (HV), the market is overpricing risk.
	•	If IV is much lower than HV, the market is underpricing risk.
	•	Our system identifies options where the spread between IV and HV supports the mispricing detected via Black-Scholes.
	•	Position Sizing:
	•	Based on the magnitude of underpricing detected, a basic sizing formula was used to allocate higher portfolio weight to options with stronger signals.
	•	This ensures that more conviction is placed on trades that show deeper mispricings.

Technologies Used 
	•	Python
	•	Jupyter Notebook
	•	yfinance (for historical options and stock data)
	•	scipy (for Black-Scholes functions)
	•	numpy
	•	pandas
	•	matplotlib (for visualization)


How It Works (High-Level Steps)
	1.	Fetch data:
	•	Pull underlying stock price, historical volatility, and options chain data using yfinance.
	2.	Calculate Black-Scholes Theoretical Price:
	•	Using inputs from the market and assumed risk-free rate.
	3.	Compare Theoretical vs Market Price:
	•	Identify if the option is underpriced or overpriced.
	4.	Calculate IV-HV Spread:
	•	Check if IV-HV spread confirms the Black-Scholes signal.
	5.	Signal Generation:
	•	Only trigger a buy/sell signal if both Black-Scholes mispricing and IV-HV spread confirm the same direction.
	6.	Portfolio Sizing:
	•	Allocate portfolio weights based on the strength of underpricing detected.
	7.	Visualization:
	•	Plot mispricing signals over time to visually assess model behavior.

Upon detecting a mispricing, the system applies a position sizing strategy using delta hedging and calculates estimated returns on a $1 million portfolio.

This project was built as part of a personal initiative to better understand options valuation, volatility arbitrage, and quantitative trading systems.

Currently working on integrating a live backtesting engine to simulate real-market execution, making the detector suitable for practical, real-time trading strategies.

Author : Mohnish Gautam

