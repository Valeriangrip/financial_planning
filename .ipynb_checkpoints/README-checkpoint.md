# Unit 5 - Financial Planning

## Requirements
The purpose of this assignment is to demonstrate the use of API's (Alpaca and Free Crypto) , in addition with the MCForecastTools toolkit.
The main tasks include pulling data from online databases, formatting into json, then determine the closing price and finally calculating
your amount of shares. This will also be run through an if else statement to determine whether or not your shares are sufficient for savings.
A nice pie chart will also show.

The second part of the assignment is similar to the above forementioned, but in addition of running a monte carlo simulation with the fetched
data. A custom weight ratio of the bonds will be considered with for the next 30 years , including cumulative daily returns, distribution of
final cumulative returns, and a method to calculate the upper and lower confidence intervals. The optional section was selected for 10 years.

## Approach
Using the starter code, and materials from the activities from class, I began looking at sample code and appended it to my work knowing that 
those were the right steps for the instructions. Example, using Unit 5 Class 5, Activity 3, financial forecast, was a template and skeleton
step by step all the way to monte carlo simulation and plotting.

## Code Snippets & Outputs
```
1.2 BTC, 5.3 ETH, 200 AGG 50 SPY
# Use alpaca.get_barset with dataframe to pull stock data, and requests.get() to pull crypto data
btc_request = requests.get(btc_url).json()
btc_price=btc_request['data']['1']['quotes']['CAD']['price']

df_portfolio = alpaca.get_barset(
    tickers,
    timeframe,
    start = start_date,
    end = end_date,
    limit=1000
).df

run calculations to get this pie chart
```
![Crypto vs Shares Chart (/pie.png)



```
Setup a monte carlo simulation for 30 years
MC_dist = MCSimulation(
    df_stock_data,
    weights = [.6,.4],
    num_simulation = 500,
    num_trading_days = 252*30
)
```
![Crypto vs Shares Chart (/cum.png)
