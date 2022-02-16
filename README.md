# Introduction
In this project, we are going to build a model to predict the stock prices of 25 large cap technology stocks. Based on how the predicted future price of the stock compares to the current price and a given investment horizon, we are going to determine whether a stock is a buy, hold or sell.

<br>

# Research Questions
1. What is the price of the stock on the first day of each quarter in 2020?
2. Given the predicted prices, what would be the rating of each stock every month from 2010 to 2019 if it is held until the first day of each quarter in 2020?
3. Given the predicted price, what would be the expected ROIs on investments made in the stock every month from 2010 to 2019 if it is held until the first day of each quarter in 2020?
4. Given the ROIs over time, discuss whether just buying and holding stocks proves to be more beneficial than actively trading stocks. 
5. What factors were most impactful in determining the future price of a stock? 
6. How reliably can we predict the future price of a stock with the past price data and financial statement data? 

<br>

# Dataset Description
We are going to use 2 datasets: [daily closing prices of NASDAQ & NYSE stocks since 1980](https://www.kaggle.com/qks1lver/nasdaq-and-nyse-stocks-histories), and financial statements from [SEC filings between 2010 and 2020](https://www.kaggle.com/finnhub/reported-financials). We will only consider the years 2010-2020. The data on years between 2010-2019 will be used to train our algorithms. The data for the year 2020 will be used as our test data. Our predictions will target the first day of each quarter during the year 2020. The datasets are taken from Kaggle.com, are already cleansed and in consumable CSV and JSON formats (respectively). No cleaning will be done. A parser will be built to grab fields-of-interest from the datasets into our solution.

<br>

# Algorithms
A regression supervised learning model will be used to predict the closing price, by finding the relationship between the independent variables "opening price, highest price and lowest price" and the dependent variable "closing price". The regression analysis will be implemented using Long Short-Term Memory (LSTM) and the Random Forest (RF) algorithms.

The LSTM is a recurrent neural network algorithm used in time series prediction, it increases the memory of RNN and addresses the vanishing gradient problem. The RF regression, on the other hand, uses the ensemble learning technique by running the training process on a number of decision trees in parallel, and the output of prediction is calculated by taking the mean of all decision trees outputs.

<br>

# Evaluation
The two models trained using the selected algorithms will be evaluated and compared. The models will predict closing prices on specific dates, and the following metrics will be used to evaluate them:
- Root mean squared error on prediction (RMSE)
- Normalized RMSE

A RMSE value close to zero would indicate a very good fit to the data. The model with lower RMSE value will be considered the better algorithm for this use case.
