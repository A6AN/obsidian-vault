---
tags: [machine-learning, source]
---

2024-10-16 23:58

Status: #baby

Tags: [[Research]] [[AI]] [[Stock Market]] 

# Stock Closing Price Prediction using Machine Learning Techniques

Traditionally, two main approaches have been proposed for predicting the stock price of an organisation. Technical analysis method uses historical price of stocks like closing and opening price, volume traded, adjacent close values etc. of the stock for predicting the future price of the stock. The second type of analysis is qualitative, which is performed on the basis of external factors like company profile, market situation, political and economic factors, textual information in the form of financial new articles, social media and even blogs by economic analyst.  Now a days, advanced intelligent techniques based on either technical or fundamental analysis are used for predicting stock prices. Particularly, for stock market analysis, the data size is huge and also non-linear.
Most of the previous work in this area use classical algorithms like linear regression , Random Walk Theory (RWT) , Moving Average Convergence / Divergence (MACD) and also using some linear models like Autore-gressive Moving Average (ARMA), Autoregressive Integrated Moving Average (ARIMA) , for predicting stock prices. Recent work shows that stock market prediction can be enhanced using machine learning. Techniques such as Support Vector Machine (SVM), Random Forest (RF) . Some techniques based on neural networks such as Artificial Neural Network (ANN), Convolutional Neural Network (CNN), Recurrent Neural Network (RNN) and deep neural networks like Long Short Term Memory (LSTM) also have shown promising results.
Statistics of the dataset

 Testing Dataset

Time Interval
Dataset  04/05/2009 – 04/05/2019 
Training Dataset 04/06/2009- 04/03/2017
Testing Dataset 04/04/2017 – 04/05/2019

Six new variables have been created for the prediction of stock closing price. These variables have been used to train the model. The new variables are as follows:
1. Stock High minus Low price (H-L)
2. Stock Close minus Open price (O-C)
3. Stock price’s seven days’ moving average (7 DAYS MA)
4. Stock price’s fourteen days’ moving average (14 DAYS MA)
5. Stock price’s twenty one days’ moving average (21 DAYS MA)
6. Stock price’s standard deviation for the past seven days (7 DAYS STD DEV)
# References

Stock Closing Price Prediction using Machine Learning Techniques
Mehar Vijha, Deeksha Chandolab, Vinay Anand Tikkiwalb, Arun Kumarc
