---
title: "Basic twitter scraping and analyzing tweets sentiment"
mathjax: true
layout: post
categories: media
---






{{ post.excerpt }}







## Problem definition 

In modern world, social media has became cornerstone of our lives, we spend humongous ammount of time online. This means while we are online we leave a lot of data on the social sites, like Facebook, Instagram, etc. This data is particulary useful to nearly every corporation in the world, especially in advertising. Now if we wanted to know how do users feel about particular subject, we would want to read their posts regarding them, so best place would be twitter where people leave their opinions very often. That is why twitter is the social media of choice for sentiment anaysis. We will extract two variables from users tweets, polarity and subjectivity. These two variables have use in many models for research and bussiness purposes. 



## Libraries





Since this is done in python, we essentially need 3 libraries:
SNSScrape
TextBlob
WordCloud
For clarity sake we define the libraries like this:





![libs](/assets/images/ss1.png)





## Data collection





Now the next step would be data collection. Since we are scraping, we need to define maximum number of tweets, and parameters on what tweets do we scrape. We have options like choosing specific user or searching by term, plus there is option of time window in which we do search.





![collection](/assets/images/ss2.png)





In our case we will collect data about bitcoin in defined time window. After we get the list, we need to convert the list into pandas data frame.





## Cleaning the data


Since we want to analyze the data collected, the most important step is the cleaning the data. We need to remove links, special characters, etc.

![cleaning](/assets/images/ss3.png)


Also, it would be advisable when scraping data to also filter spam tweets. In this example the spam filter is very basic, but it is possible to put any keyword into spam filter to make it better.


## Analysis

Since the data is collected and cleaned, we can go to analyze the tweets. This is achieved by TextBlob library.
Here is example how it is done:

![analyze](/assets/images/ss4.png)

And if we follow the example, we get two new rows in data frame subjectivity and polarity.

![results](/assets/images/ss5.png)

This data is useful, if we need to build models based on sentiment of twitter users about some topic, for example if we want to predict crypto prices, or any other application. Even in the business perspective twitter sentiment analysis allows you to keep track of what's being said about the products or services on social media, and can help detect angry customers or negative mentions before they they escalate. There are a lot of benefits of analyzing data like this, so this is valuable to almost any bigger public firm in the world.



