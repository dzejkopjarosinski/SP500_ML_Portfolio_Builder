# SP500_ML_Portfolio_Builder
This project is a random forest algorithm used to select the best stocks from SP500 index to create out of them index with the same risk tolerance but more promissing upsite potential.

## Data
The biggest issue with the financial classifiers is lack of publicly available free data. For that purpose I scraped the data from the old version of yahoo finance website that allowed to view into financial statements back to the 2003. 

There are 4 datasets that I prepared beforehand :
* Keystats - Dataset with different features of SP500 stocks EV/EBITDA, Total Debt/Equity etc.
* Stock_prices - Prices of individual SP500 stocks (SP500 stock prices downloaded from yahoofinance API)
* sp500_price - The price of the whole SP500 index.


