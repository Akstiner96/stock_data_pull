# Stock Data Pull Using Alpaca's API and AlphaVantage

### **What it does**

This is a reusable dotpy file that will import, clean, and present in DataFrame format, any stock data available from the Alpaca/AlphaVantage API.

### **Usage Notes**  

* User must have their own Alpaca API keys stored in a dotenv file in the same folder as the data_pull.py file.


* The [endpoint URL](https://paper-api.alpaca.markets) for key authentication is set to Alpaca's paper trading domain. Use of live trading will likely require an update to the 'base_url' parameter that is inside the 'load' function where api is defined.


* AlphaVantage is used because it provides more data categories than base Alpaca, however, its API call rate limit is far less than Alpaca. For this reason there is a sleep timer added to the 'data_pull' function that adds a minute of wait time after every 5 calls. Limit the 'tickers' list to 5 stocks to get an immediate output. 


* The 'data_clean' function is completely personal preference. Comment out lines or add to it to personalize the data output.  

* Alpaca only carries [data]('https://alpaca.markets/docs/api-documentation/api-v2/market-data/') of commodities traded on select exchanges. If an ETF or security is not available through Alpaca, the error '_That is not a proper ticker symbol_' will be raised. 