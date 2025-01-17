# The US VS China Trade War
## Data Story website

https://rhitamam.github.io/

## Members:
* Antoine Escoyez
* Rhita Mamou
* Mohamed Allouch
* Marcel Moran Calderon

## Abstract
The US-China trade war began in July 2018, eventually leading to tariffs on some US$550 billion of Chinese goods and US$185 billion of US goods [1]. We wish to analyze the US VS China trade war in order to build our data story around  the one million dollar question : which comes first, the price or the sentiment? Indeed, since those two countries have such an influence on the world economy, we can assume that every single political tension related in the press is susceptible to have some repercussions on assets [2]. The end goal would be to perform interesting analyzes about stock prices correlation with announcements in the US press and even causation if applicable. We refine our ideas in the research questions section. Quotebank dataset [3] can be used to extract sentiment from its great amount of quotes which cover the trade war period. We plan to use enhanced daily data about significant assets as our stock variation reference [4, 5].


[1] South China Morning Post. 2021. Timeline of the US-China trade war since July 2018. [online] Available at: <https://www.scmp.com/economy/china-economy/article/3146489/us-china-trade-war-timeline-key-dates-and-events-july-2018> [Accessed 12 November 2021].

[2] Wto.org. 2021. WTO | An economic analysis of the US-China trade conflict [online] Available at: <https://www.wto.org/english/res_e/reser_e/ersd202004_e.htm> [Accessed 12 November 2021].

[3] Dl.acm.org. 2021. Quotebank | Proceedings of the 14th ACM International Conference on Web Search and Data Mining. [online] Available at: <https://dl.acm.org/doi/10.1145/3437963.3441760> [Accessed 12 November 2021].

[4] Services, W., 2021. Wharton Research Data Services. [online] WRDS. Available at: <https://wrds-www.wharton.upenn.edu> [Accessed 12 November 2021].

[5] Finance.yahoo.com. 2021. Yahoo is part of the Yahoo family of brands. [online] Available at: <https://finance.yahoo.com> [Accessed 12 November 2021].


## Research questions	
* Is the stock market affected by quotations or the opposite?
* Does the news only relate recent variations of the stock market when these variations have already been officially published?
* Are we able to predict a specific stock market using sentiment analysis on newspaper quotes?
* Can we quantify the time window within which a quote can influence the stock market ? (We suppose here that sentiment influence must vanish when time is passing).
* What is the correlation between media quotations and stock prices behavior under a specific model?
* Are they red flags in quotes that are better predictors than sentiment analysis ?
* Which assets are more affected by sentiment if applicable?


## Proposed Additional Datasets

### Stock market dataset

Our project relies on the availability of data which describe the stock market evolution. We will be using stock data from yahoo finance. Its API provides real time low latency data of stock market, crypto currencies, and currency exchange. We can get reliable, threaded, and Pythonic ways to download historical market data. We can adjust the frequency of data extraction up to the minutes. For our project, our frequency will be an hour as we can distinguish the impact of market sentiment at such a rate and we are not obliged to dig deeper in data. 
Assets will be diversified to cover all fields like petroleum, metals, fossil energy, agriculture ... 
so that we can seek the effect of the general sentiment on various fields.

| Date          | Open          | High          | Low           |  Close       | Volume     | Dividends  | Stock Splits    | Log returns    |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | -------------- | ------------   |
| 2018-02-02 12:00:00 | 60.200|60.748|60.099|60.369|510313|0|0|- 0.02065650718972446|

## Methods

*We first need to perform data collection:*
### Quotebank
Using Quotebank, we want first to isolate every quotation which is related to China. For that purpose we used the NLTK library to get a set of synonyms and antonyms for the word ‘china’. In addition, we will apply extra filtering to focus on quotations related to trade war, especially because in 2019 we might have to deal with a huge quantity of quotations related to the COVID-19 sanitary crisis. It is important to clarify that some quotation related to trade might be missed because of the filtering, but from the analysis done in the dataset we could observe how the trade war topic still holds

### Stock market dataset

Stock market dataset and financial data in general are noisy data because of the high frequency of extraction. Extra treatment is necessary to extract meaningful insights from it. Our first treatment is to compute the log price return of an asset.

*Then we need to create proper features to perform our analyses for each research question:*

### Capture news and stock behaviour temporality

We plan to use first daily data from the stock market then refine the frequency to see if news only comes after variations. Using red flags in quotes we can assess the simultaneity of quoted information and stock variations. We will try to quantify the short term memory of news sentiment on stock variations by using quotes from a designed time window before the stock variation.

### Capture quote sentiment
We can perform several types of sentiment analysis, rule-based NLP (textblob, vader) and machine learning models such as one shot bart model

### Capture stock market variation
The raw data from stock market is irrelevant and we need to rather capture variation and index value to capture the market trends for which we try to discover correlation and causation through log price return.



## Proposed timeline & organization within the team


| Task          | Expected commited hours          | ID Task          |Deadline          |
| ------------- | ------------- | ------------- | ------------- |
| Data steps: baseline daily stock data / higher frequency stock data| 5h | #1|25.11.2021|
| Feature steps for quotes: rule-based NLP / context aware NLP / custom TensorHub model / red flags / short term memory assessment| 5h| #2|25.11.2021|
| Performance steps: measure correlation, prediction score, assets variations proportional to frequency in quotes >> for each configuration | 5h| #3|25.11.2021|
| Extra steps: inverse prediction of sentiment using stock variation, which assets are more sensible to sentiment, which information sources have the more influence| 5h| #4|06.12.2021|
| Visualization  | 10h| #5|10.12.2021|
| Github README final update | 2h| #6|16.12.2021|
| Training Model for detecting flags| 6h| #7|02.12.2021|
| Writting data story and preparing final presentation | 4h| #8|16.12.2021|
| Running tests and tabulating final results| 10h| #9|10.12.2021|
| Crawling data | 10h| #10|25.11.2021|


**Table of assigments**
| Names          | ID Task          | 
| ------------- |  ------------- | 
|Antoine Escoyez|#1 #2 #3|
|Rhita Mamou|#6 #9 #5|
|Mohamed Allouch|#7 #8|
|Marcel Moran Calderon|#10 #4|

## Contact
* mohamed.allouch@epfl.ch
* antoine.escoyez@epfl.ch
* rhita.mamou@epfl.ch
* marcel.morancalderon@epfl.ch
