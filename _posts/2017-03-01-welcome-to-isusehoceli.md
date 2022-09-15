---
title: "Comparing LSTM, GRU, BILSTM for predicting crypto"
layout: post
---


## Problem definition
Making money on crypto is difficult and risky, but what if we could aleviate that issue. This is where predicting future values come into place. This is where recurrent neural networks come into picture, there are alot of studies that cover these algorithms and their performance, so they are well researched. Most used are LSTM, GRU and BILSTM, so of course question rises, which one is the superior to the others? 
This was one of the questions in my final thesis, which we got the answer to.

## Data collection and preprocessing
The first step was getting data and preprocessing it for fitting.
We got the data from binance, then since we decided to use univariate model, we removed every other column than the close value.



[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
