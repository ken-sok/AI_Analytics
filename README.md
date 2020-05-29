# Stock Market Analysis

Table of contents
(to be filled at the end)

### Description of Idea 

Idea: Using last week's stock prices, help a put option buyer predict the price(s) they should pay to the seller. 
In the research, each record (row) is data for a week. Each record also has the percentage of return that stock has in the following week (percent_change_next_weeks_price). Ideally, I want to determine which stock will drop price the most in the following week, then use the results to inform the put option buyer which stocks, and price to settle on. In other words, the main aim is to maximize is percent_change_next_weeks_price.

Goal: predict stocks that will drop price the most & determine maximum strike price (break even) that “put option” buyers should pay for(using next week as deadline). 

### Technical understanding of a put option: 
    - Option contracts let the holder choose to buy or sell the underlying instrument at a price agreed beforehand with a time limit. In essence, What are they selling? The ability/right to do business with their seller at the price they want at a specific time. 

    - Holding a put option gives the right to sell. Thus, the lower the price of underlying security the better. That means the option buyer can sell the underlying security at a much higher price to the market price to the put option seller. 
    - In Australia, an equity options contract represents 100 shares of the underlying
    security. 

    - If the option holder chooses to exercise their option, the underlying security will be purchased or sold at pre-specified price included in the option 

    - The option price (or premium) is quoted on a per share basis

    - Scale option for the future: Put options are traded on various underlying assets, including stocks, currencies, bonds, commodities, futures, and indexes. The model can also be converted for call options buyer and seller, and put option sellers. 

    Profit on put option = Max(X-ST,0) - P 

    ST = Stock price at expiration
    X = Exercise (or strike) price of the option
    P = Put option price (or premium) 

    At-the-money(no loss) is when ST = X
    In the money(profit to be made) = ST<X 
    So we want X>=ST. 



### Dataset information: 
    -number of instances: 750
    -number of attributes: 16
    -date: 23/10/2014
    -tasks: classification & clustering
    -area: business

    +Attribute Information:

    -quarter: the yearly quarter (1 = Jan-Mar; 2 = Apr=Jun).
    -stock: the stock symbol 
    -date: the last business day of the work (this is typically a Friday)
    -open: the price of the stock at the beginning of the week
    -high: the highest price of the stock during the week
    -low: the lowest price of the stock during the week
    -close: the price of the stock at the end of the week
    -volume: the number of shares of stock that traded hands in the week
    -percent_change_price: the percentage change in price throughout the week
    -percent_chagne_volume_over_last_wek: the percentage change in the number of shares of stock that traded hands for this week compared to the previous week
    -previous_weeks_volume: the number of shares of stock that traded hands in the previous week
    -next_weeks_open: the opening price of the stock in the following week
    -next_weeks_close: the closing price of the stock in the following week
    -percent_change_next_weeks_price: the percentage change in price of the stock in the following week -days_to_next_dividend: the number of days until the next dividend
    -percent_return_next_dividend: the percentage of return on the next dividend

    +Training data vs Test data:

    -In (Brown, Pelosi & Dirska, 2013) quarter 1 (Jan-Mar) data was used for training and quarter 2 (Apr-Jun) data for testing.

    -Interesting data points:
    If you use quarter 2 data for testing, you will notice something interesting in the week ending 5/27/2011 every Dow Jones Index stock lost money.

### Setup & dependencies
- miniconda (https://realpython.com/python-windows-machine-learning-setup/)
- vscode

## Steps to train & test model: 
-understanding basics of put option
-examine & clean up data  
-select most significant attributes & determine label attribute(percent_change_next_weeks_price)
(added later)

### can be improved

-validation set with more data

### Adapted from: 

https://archive.ics.uci.edu/ml/datasets/Dow+Jones+Index#

Brown, M. S., Pelosi, M. & Dirska, H. (2013). Dynamic-radius Species-conserving Genetic Algorithm for
the Financial Forecasting of Dow Jones Index Stocks. Machine Learning and Data Mining in Pattern
Recognition, 7988, 27-41.