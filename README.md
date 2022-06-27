# dayzero-python-problem

***Note***: Please do not put your solution in a public repository (GitHub, etc.). We are sending this to multiple candidates and do not want anyone to have an unfair advantage.

The python assessment contains two tasks that would cover candidate's overall knowledge on Python language, Design Patterns and ability to write clean and testable code.


# Description

Day Zero School is building its analytics solution that would provide its customer daily insights of stock market. You are hired as a Software Developer and asked to build an Initial MVP/POC that would be used by our sales team to demo the solution to our customers.

The product team and the architecture team after numerous meetings decided that solution to be delivered can be basically broken into two tasks that are to be delivered by you. The tasks are as follows:


### Task 1

Create a service that would collect the stock market data for given stock ticker/symbol/ISIN/CUSIP. For a given list of stock ticker, collect the date, high, low and close price for each day and store in a database. The job should run at least once a day.

A list of Tickers are provided in the following file [ticker_symbols.txt](/ticker_symbols.txt). Use these tickers for task 1.

##### DEV NOTES
- Create a Python service that would run as a Daemon, CLI or CRON job to achieve the above task.
- Use any freely available API service which can provide the stock market data like Alpha Vantage, Yahoo Finance, Google Finance or Quandl. Find more in the important resources section.
- The Python service should store the data in a database of your choice, i.e. SQLite, MySQL or PostgreSQL.
- It's advised but not compulsory to leverage the use of folling Python modules, libraries and frameworks Pandas, SQLAlchemy, logging, pytest, flake8.
- Write appropriate unittests and make sure tests covers positive and negative scenarios.


### Task 2

Create an API service using which our customers can get performance metrics for the stocks. 

The API should contain three endpoints/routes/paths:

- /get_top_gainers
  
  The endpoint will return the top 10 stocks whose price increased as compared to the previous day.
  
  
  This should be the response JSON structure:

  ```
  [
    {
      "rank": 2,
      "ticker": "MSFT",
      "change_percent": 10
    },
    {
      "rank": 1,
      "ticker": "GOOGL",
      "change_percent": 15
    },
    {
      "rank": 3,
      "ticker": "META",
      "change_percent": 5
    }
  ]
  ```
  
- /get_top_losers
  
  The endpoint will return the top 10 stocks whose price decreased as compared to the previous day.

  This should be the response JSON structure:

  ```
  [
    {
      "rank": 2,
      "ticker": "MSFT",
      "change_percent": -10
    },
    {
      "rank": 1,
      "ticker": "GOOGL",
      "change_percent": -15
    },
    {
      "rank": 3,
      "ticker": "META",
      "change_percent": -5
    }
  ]
  ```

- /generate_weekly_report
  
  The endpoint will return all the stocks with weekly high, low and average price. Ideally, the CSV files should contain the following columns STOCK, WEEKLY HIGH, WEEKLY LOW and AVERAGE
  
  This should be the response JSON structure:

  ```
  [
    {
      "ticker": "MSFT",
      "high": 10,
      "low": 20,
      "average": 11.9
    },
    {
      "ticker": "GOOGL",
      "high": 20,
      "low": 9,
      "average": 7.8
    },
    {
      "ticker": "META",
      "high": 55,
      "low": 22,
      "average": 19.11
    }
  ]
  ```

##### DEV NOTES
- Create a Python service that would run as a web service and expose the following APIs to achieve the above task.
- When the endpoints are called, the API should read data from the database and do computations if required and then return a response.
- The response should be in JSON format.
- It's advised but not compulsory to leverage the use of following Python modules, libraries and frameworks Flask, Tornado, Pandas, SQLAlchemy, logging, pytest, flake8.
- Write appropriate unittests and make sure tests covers positive and negative scenarios.


# Table structure

Through out the code you should used the following table structure to add, retrieve stock data.

The columns should be of the following datatype:

id: UUID or String type
DATE: Date in dd/mm/yyyy format
STOCK NAME: String
TICKER: String
HIGH: Numeric
LOW: Numberic


### stock_data table

```
+--------------------------------------------------------------------------------------------------------+
|                 id                   |    DATE    | STOCK NAME            | TICKER |  HIGH   |   LOW   |
+--------------------------------------------------------------------------------------------------------+
| 162035a6-8197-4721-8c56-f4a27f518523 | 22/03/2022 | Google LLC            | GOOGL  | 2371.59 | 2303.59 |
| 162035a6-8197-4721-8c56-f4a27f518523 | 22/03/2022 | Meta Platforms Inc    | META   | 2371.59 | 2303.59 |
| 162035a6-8197-4721-8c56-f4a27f518523 | 22/03/2022 | Microsoft Corporation | MSFT   | 2371.59 | 2303.59 |
+--------------------------------------------------------------------------------------------------------+
```

Notes: 
- What are stock high and low ? https://analyzingalpha.com/open-high-low-close-stocks
- What is a stock symbol and ticker ? https://www.investopedia.com/terms/s/stocksymbol.asp


# Submission

- Candidates should submit the code with appropriate documenting how to set up and run the code locally.
- Explaining their approach.
- Any issues that they think were encountered.
- How the application can be improved.


# Submission++

If the candidates are able to complete the above tasks in time, they can work on these tasks. The candidate will only be evaluated on the tasks mentioned above, but we encourage work on these as it would help up evaluate if there is a tie.

- How to scale the application if the number of customers increased.
- Dockerizing the application.
- How to authenticate and authorize users who will be using the application.


# How candidates will be evaluated
- How well the code is written i.e. code readability, use of design patterns, code packaging and repos structure, styling and linting.
- Test coverage of the code.
- Logging important information.
- Documenting the application details.
- Maintaining clean git commit history.


# Important resources:

- Code structure and packaging: https://docs.python-guide.org/writing/structure/
- Python REST API Tutorial: Building a Flask REST API: https://www.youtube.com/watch?v=GMppyAPbLYk
- Flask Tutorial #7: Using SQLAlchemy Database: https://www.youtube.com/watch?v=uZnp21fu8TQ
- Styling and linting: https://flake8.pycqa.org/en/latest/
- Google Python Style Guide: https://google.github.io/styleguide/pyguide.html
- Stock market APIs: https://www.alphavantage.co/documentation/, https://www.alphavantage.co/
- Stock market APIs: https://www.yahoofinanceapi.com/tutorial
- Stock market APIs: https://www.learndatasci.com/tutorials/python-finance-part-yahoo-finance-api-pandas-matplotlib/

