# ETL Data Collection and Analysis of Yahoo Finance Data

In this project, I will collect Yahoo finance data using RapidAPi 
The following will outline the key steps needed to extract the data

---
* Determine what is the purpose of the project
* What will be the fields to be collected?
* How will it be collected, what necessary method or technology will be applied in the process?
* How will the data collected be modelled
* What methods and techniques will be used to clean, transform, check the data quality and remove irregularities in the data?
* How will the data be stored, will it be partitioned before storage?
* What results did you get from the process?
* How can you improve the project, what can be done to make it better?
* What challenges did you encounter in the project?

---

## Purpose of project:

This project is done for the completion of Udacity Data Engineer Nanodegree program. The goal is to apply all the necessary skills acquired during the program and build an unguided project. In this project, I will analyse the trend of some currencies and stocks finaincial markets. I will be using RapidAPI to get the data needed for this project. Some of the currencies pair I am interested in are GBPAUD,GBPJPY and GBPUSA, while the stocks are AAPL, AMZN and IBM. I am more interested in know how price of stocks changes at a particular range. For stocks, I would like to know how much gains the stocks made. Although data from Yahoo finance is relatively old, I know the query can be adjusted to allow records from recent time. In conclusion, the number of records will be over 1 million as required in the program. 

## Data 
The data to be collected will include currencies, gainers, losers and most-active stocks, historical data of stocks and time-range data of the currencies. I will also get summary of each stock which will contain information such as country, phone, sector, earnings, and financial chart. The  currencies data will contain intervals of 1min, 5min, 1day and 1week and range of 5d, 1mo, 6mo and 1yr respectively. The following will detail how the schema to store the data will be designed for easy access and retrieval of the data. 

---

*** 
   Discuss how the data will be stored.

There will be 10 currencies and 30 stocks. The stocks will be divided into gainers, losers and most-actives. The goal is to collect historical data of the stocks which will include 1 year of records such as the high and low price of the stock, and time of the data. I will also collect the summary of the stocks which will include summaryProfile and earnings. To begin, I will get the currencies data with the four ranges using the endpoint 'market/get-spark'. Then I will check the gainers, losers and most-active stocks in GB market region using the endpoint "market/v2/get-movers". Using the symbols collected, it will be passed to the endpoint "stock/v3/get-historical-data"  to get the historical data of the stocks. It will also be passed to "stock/v2/get-summary" to get summary and eraning of the stocks. To design the schema, I will consider a number of things. 
