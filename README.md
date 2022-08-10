# LSTM Stock Predictor

![](https://github.com/sarahm44/lstm-stock-predictor/blob/main/images/deep-learning.jpg)

## Table of Contents

- [Overview](#overview)
- [Tasks Completed for Each Notebook](#tasks-completed-for-each-notebook)
  * [Prepare the Data for Training and Testing](#prepare-the-data-for-training-and-testing)
  * [Build and Train Custom LSTM RNNs](#build-and-train-custom-lstm-rnns)
  * [Evaluating the Performance of Each Model](#evaluating-the-performance-of-each-model)
    + [Closing Prices Model](#closing-prices-model)
    + [FNG Model](#fng-model)
    + [Conclusions](#conclusions)

## Overview

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the [Crypto Fear and Greed Index (FNG)](https://alternative.me/crypto/fear-and-greed-index/) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. 

In this repository I built and evaluated deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

I used deep learning recurrent neural networks to model Bitcoin closing prices. One model used the FNG indicators to predict the closing price while the second model used a window of closing prices to predict the nth closing price.

The two relevant notebooks are:

* [Closing Prices Notebook](https://github.com/sarahm44/lstm-stock-predictor/blob/main/lstm_stock_predictor_closing.ipynb)
* [FNG Notebook](https://github.com/sarahm44/unit-14-assignment/blob/main/lstm_stock_predictor_fng.ipynb)

I completed the following tasks:

1. Prepared the data for training and testing
2. Built and trained custom LSTM RNNs
3. Evaluated the performance of each model

## Tasks Completed for Each Notebook

In both notebooks [Closing Prices Notebook](https://github.com/sarahm44/lstm-stock-predictor/blob/main/lstm_stock_predictor_closing.ipynb) and [FNG Notebook](https://github.com/sarahm44/unit-14-assignment/blob/main/lstm_stock_predictor_fng.ipynb), I built and trained a custom LSTM RNN that uses a 10 day window of Bitcoin fear and greed index values, or closing prices, to predict the 11th day closing price.

### Prepare the Data for Training and Testing

In this section, I prepared the training and testing data for the model. The model uses a rolling 10 day window to predict the 11th day closing price.

I completed the following:

1. Used the window_data function to generate the X and y values for the model
2. Split the data into 70% training and 30% testing
3. Applied the MinMaxScaler to the X and y values
4. Reshaped the X_train and X_test data for the model

### Build and Train Custom LSTM RNNs

In this section, I designed a custom LSTM RNN and fit (train) it using the training data.

I completed the following:

1. Defined the model architecture
2. Compiled the model
3. Fit the model to the training data

In each Jupyter Notebook, I created the same custom LSTM RNN architecture. In one notebook, I fit the data using the FNG values. In the second notebook, I fit the data using only closing prices.

I used the same parameters and training steps for each model, in order to compare each model accurately.

### Evaluating the Performance of Each Model

Finally, use the testing data to evaluate each model and compare the performance.

#### Closing Prices Model

See a DataFrame of real and predicted values for the Closing Prices model:

![](https://github.com/sarahm44/lstm-stock-predictor/blob/main/images/closing_df.png)

See a graph of the real vs predicted values for the Closing Prices model:

![](https://github.com/sarahm44/lstm-stock-predictor/blob/main/images/closing_graph.png)

#### FNG Model

See a DataFrame of real and predicted values for the FNG model:

![](https://github.com/sarahm44/lstm-stock-predictor/blob/main/images/fng_df.png)

See a graph of the real vs predicted values for the FNG model:

![](https://github.com/sarahm44/lstm-stock-predictor/blob/main/images/fng_graph.png)

#### Conclusions

As indicated by the graphs and dataframes above, the LSTM RNN which uses closing price data has the lowest loss, and tracks the actual values best over time.
