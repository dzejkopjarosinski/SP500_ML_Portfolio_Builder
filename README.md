# SP500_ML_Portfolio_Builder
This project is a random forest algorithm used to select the best stocks from SP500 index to create index out of them with the same risk tolerance but more promissing upsite potential.

## Data
The biggest issue with the financial classifiers is lack of publicly available free data. For that purpose I scraped the data from the old version of yahoo finance website that allowed to view into the financial statements back to the 2002.
Therefore model performance was limitted to years 2002-2014. 

There are 4 datasets that I prepared beforehand :
* Keystats - Dataset with different features of SP500 stocks EV/EBITDA, Total Debt/Equity etc.
* Stock_prices - Prices of individual SP500 stocks (SP500 stock prices downloaded from yahoofinance API)
* sp500_price - The price of the whole SP500 index.

The data needed synchronization due to different timestamps in particular datasets hence "Syncin Data" section was appliet in the notebook

Code

```python
training_data = keystats.set_index('Date')
training_data = training_data.sort_values(by=['Ticker', 'Date'])
training_data.dropna(axis=0, how='any', inplace=True)
features = training_data.columns[6:]

X_train = training_data[features].values

OUTPERFORMANCE = 10

y_train = [
  1 if stock_p_change - SP500_p_change >= OUTPERFORMANCE else 0
  for stock_p_change, SP500_p_change in zip(
      training_data["stock_p_change"], training_data["SP500_p_change"]
  )]
```
