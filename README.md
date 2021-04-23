# Forex Price Predictor
Forex is a centralized marketplace for foreign currency exchanges. It is the de facto place for trading between different currency pairs that results in trillions of dollars of trade each day. However, due to the volatility of the market and its dependence on multiple factors such as interest rates, inflation rates, etc. of each pair, it is extremely difficult to predict the behavior of the market.

In this study, we have developed a Forex price predictor for the EUR/USD currency pair. The prediction of the closing price of the market can be significantly improved by incorporating news sentiment analysis and some technical/statistical indicators that forex traders use in their daily routine. We have incorporated these extra features into a Long Short Term Memory (LSTM) model using mean squared error (MSE) as a loss function to predict the closing price of the next day.

## Files
This project consists of the following three files:

### transformation.ipynb: 
This file performs data transformation and feature engineering on the Forex price data. It generates additional features such as high_open, open_low, total_pips, return_1, return_5, RSI, Bollinger Bands, MACD, EVM, ROC, Force Index, etc. The transformed data is saved to a CSV file called transformed_data.csv.

### sentiment_analysis.ipynb: 
This file performs sentiment analysis on news articles related to the Forex market. It tokenizes and stems the text, calculates subjectivity and polarity scores, and uses the VADER sentiment analyzer. The sentiment analysis results are merged with the transformed Forex price data to create a merged dataset saved as merged_data_extra.csv.

### FLF-LSTM Different Activations.ipynb: 
This file implements a Long Short Term Memory (LSTM) model for predicting Forex prices. It trains multiple LSTM models with different activation functions and evaluates their performance using mean squared error (MSE) and R2 scores. It also plots the training and validation loss, as well as the predicted prices. The code uses various datasets with different combinations of columns, such as raw data, additional features, news titles, news articles, and correlated columns.

## Usage
To use this Forex price predictor, follow these steps:

Run transformation.ipynb to transform the raw Forex price data and generate additional features. The transformed data will be saved as transformed_data.csv.

Run sentiment_analysis.ipynb to perform sentiment analysis on the news articles related to the Forex market. This script will tokenize and stem the text, calculate subjectivity and polarity scores, and merge the sentiment analysis results with the transformed Forex price data. The merged data will be saved as merged_data_extra.csv.

Finally, run FLF-LSTM Different Activations.ipynb to train LSTM models with different activation functions and evaluate their performance. The script will split the dataset into training and testing sets, train the models, evaluate them using MSE and R2 scores, and plot the training and validation losses as well as the predicted prices.

Results
The project evaluates different combinations of columns and activation functions to find the best performing model. The results are displayed in a table format, showing the columns used, the activation function, the loss (MSE), and the R2 score for each model.

Additionally, various plots are generated to visualize the training and validation losses, the best testing errors, the best testing R2 scores, and the predicted prices.

Please make sure you have the required input files (D.csv, eurusd_news.csv, transformed_data.csv) before running the code.