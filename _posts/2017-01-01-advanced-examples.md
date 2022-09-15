---
title:  "Basic scraping and analyzing tweets sentiment"
mathjax: true
layout: post
categories: media
---

## Libraries

Since this is done in pythone, we essentially need 3 libraries:
SNSScrape
TextBlob
WordCloud

For clarity sake we define the libraries like this:

![libs](/assets/images/ss1.png)

## Data collection

Now the next step would be data collection. Since we are scraper, we need to define maximum number of tweets, and parameters on what tweets do we scrape. We have options like choosing specific user or searching by term, plus there is option of time window in which we do search. 

![collection](/assets/images/ss2.png)

In our case we will collect data about bitcoin in defined time window. After we get the list we need to convert the list into pandas dataframe. 

## Cleaning the data

Since we want to analyze the data collected, the most important step is the cleaning the data. We need to remove links, special characters etc.

![cleaning](/assets/images/ss3.png)


Also it would be advisable when scraping data to also filter spam tweets. In this example the spam filter is very basic, but it is possible to put any keyword into spam filter to make it better.



## Analysis

Since the data is collected and cleaned, we can go to analyzing the tweets. This is achieved by TextBlob library. 

Here is example how is it done:

![analyze](/assets/images/ss4.png)

And if we follow the example, we get two new rows in dataframe subjectivity and polarity.

![results](/assets/images/ss5.png)

This data is useful, if we need to build models based on sentiment of twitter users about some topic, for example if we want to predict crypto prices based on sentiment. 

