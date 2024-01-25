# Module 5 Challenge - Financial Planning

## Overview


In this project a prototype application is developed to demo for the Chief Technology Officer (CTO) of a hypothetical credit union. The application, presented in the form of a Jupyter Notebook, will aid in a variety of financial planning assessment activities for the credit union members including the following:

* Assessment of monthly personal finances
* Forecasting of portfolio efficacy based on:
  * Cryptocurrency performance
  * Stock performance
  * Bond performance

## Technical Details

The notebook will load the following libraries and dependencies.

```python
import os
import requests
import pandas as pd
from dotenv import load_dotenv
import alpaca_trade_api as tradeapi
from MCForecastTools import MCSimulation
import json
import warnings
warnings.filterwarnings('ignore')

%matplotlib inline
```

The administrator of the program will need to place their personal environment variable `.env` file, containing their API keys, into the root directory as well as replace the `"my.env"` portion of the code listed below with their particular filename. 

```python
load_dotenv("my.env")
```
Two APIs will be utilized to pull market pricing data.

* Alpaca Markets API for SPDR S&P 500 ETF Trust `SPY` and iShares Core US Aggregate Bond ETF `AGG` for pricing and historical performance.
* Alternative Free Crypto API for Bitcoin `BTC` and Ethereum `ETH` for pricing and historical performance


## Financial Analysis and Forecasting

The program calculates the current value of the crypto and equity holdings of the individual. The crypto/shares composition will be charted. An assessment of whether the individual has adequate savings to satisfy the need for a baseline emergency fund (3 x monthly income) is made. 

Five hundred Monte Carlo simulations will be conducted utilizing 5 years of data to forecast 30-, 10-, and 5-year cumulative returns. The results will be charted as a line plot as well as a distribution plot. A retirement analysis will be presented based on the findings for the three holding periods and conclusions will be drawn based on 95% certainty. 

## Sources

The following sources were consulted in the completion of this project. 

* [Free Crypto API Documentation](https://alternative.me/crypto/api/)
* [AlpacaDOCS](https://alpaca.markets/docs/)
* [pandas.Pydata.org API Reference](https://pandas.pydata.org/docs/reference/index.html)
* UCB FinTech Bootcamp instructor-led coding exercises