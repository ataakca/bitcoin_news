# Capstone: Predicting Bitcoin Movements by Analyzing the News

by: Ata Akca



### Problem statement

---

Financial asset movements are hard to predict, making day trading a challenging business to make money on. Price movements depend on many different factors at the same time, from news to stocks, from SEC filings to labor force declarations. Additionally, the movements are based on real time, following quick changes and volatility. For reasons, I have been aware and following Bitcoin since the year 2013 thanks to my friend Matias Faure. Since then, Bitcoin has got me thinking about what the underlying reason is for an asset to have such sudden rises and falls. After making brief research on my Capstone Project, my friend Steve from CoinBase told me that it would be convenient if they had a tool to analyze news and predict the outcome. Detecting any news that causes sudden shocks world-wide, hits the financial markets would make it easier to take precautions for a company who is handling assets as such. Therefore my problem statement was created: "Predicting Bitcoin Movements by Analyzing the News"

### Executive Summary

---


To find a solution to this problem, an external research on Bitcoin and its technical features were made. Afterwards, many different news sources were observed to find the optimal one for scraping. All of the news back to beginning of January were scraped.

The optimal solution appeared to be creating a binary classification of daily changes in Bitcoin prices. Therefore all of the news were vectorized by using Google's 100B+ Lexicon. Every row of the dataframe that was pushed into the model is a mean vectorized value of aggregated news that belong to the date.

RNN Model was used to predict the movement of Bitcoin.

**Description of data:** News scraped from New York Times. The types and columns of the data was explained further in data dictionary section. 

The filters were:
- News from 01-01-2017 to 02-28-2020
- Articles only
- World news only

Bitcoin data was requested from alphavantage.co, they are Daily Bitcoin Opening and Closing prices.

**Size:** 
- News: 18677 rows and 5 columns.
- Bitcoin: 926 rows and 11 columns.

**Sources:**
- [News Data](./Datasets/backup_data.csv)
- [Aggregated News](./Datasets/aggregated_news.csv)
- [Vectorized Articles](./Datasets/vectorized_articles.csv)
- [Vectorized Titles](./Datasets/vectorized_titles.csv)
- [Bitcoin Daily Price Movements](./Datasets/currency_daily_BTC_USD.csv)

### Conclusions and Recommendations

---

The best testing accuracy score achieved from the RNN Model was 0.542, making this model not very feasible in terms of making money out of trading. Scores were inconclusive due to several reasons:
- The news gathered were mostly world news, not directly related to Bitcoin, Cryptocurrencies or Financial markets in general.
- Google Lexicon used in this project didn't include the word 'Bitcoin' or 'Cryptocurrency' therefore the vectors were not used to their highest potential.
- Only one modeling method was used, therefore they can not be compared to another score.

Recommendations:
- Gathering more finance/bitcoin/cryptocurrency related news
- Using clustering and Density analysis on categories, to find out about daily distribution of where in the world the news belong to
- Detecting sudden shocks and worldwide news
- Adding new features that are purely bitcoin related (halving and mining difficulty statistics)
- Testing the model with new untrained news to discover new improvements according to recent news
- Adding or finding a lexicon that has the vector bitcoin in it
- Handling vectors in different manners


### Contents

---

- [Data Scraping](./Code/1_data_scraping.ipynb)
- [Data Cleaning and EDA](./Code/2_data_cleaning_and_eda.ipynb)
- [Further EDA and Frequency Distributions](./Code/3_further_eda_tokenization_frequency_distributions.ipynb)
- [Articles/Titles/Words Vectorized](./Code/4_Word2Vec_Model.ipynb)
- [RNN Modeling](./Code/5_RNN_Model.ipynb)



### Data Dictionary

---

|Column Name|Type|Description|
|---|---|---|
|date|datetime64|Date of the news published|
|category|object|Part of the World the corresponding news belong to|
|title|object|Title of the news|
|article|object|Short summary of the news|
|author|object|The author/source of the news|


### References

---


- https://www.investopedia.com/terms/b/blockchain.asp

- https://www.investopedia.com/terms/b/bitcoin.asp

- https://www.nytimes.com
