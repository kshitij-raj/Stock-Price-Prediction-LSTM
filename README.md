# Stock Prices Prediction using Keras LSTM Model

In this project, I extracted the Google stock prices data from https://api.tiingo.com/ for the time period of 5 years (October 2016 - October 2021). The main objective for the project is to predict the prices of Google stock 30 days in the future based off of the current Close price. I used Long Short-Term Memory (LSTM). LSTMs are widely used for sequence prediction problems and have proven to be extremely effective. The reason they work so well is that LSTM can store past important information and forget the information that is not.

## Data Preparation
I created a new data frame containing only the target variable - Closing stock price and converted it into an array to train the model. For this project, traning dataset had 70% of values. With time series data, the sequence of values is important. The LSTM network expects the input data to be provided in 3D array structure: [samples, time steps, features]. Currently, the data is in the form: [samples, features] I transformed the train and test input data into the expected structure using numpy.reshape().

## Model Building
A Long Short-Term Model was built using Keras which had 50 units, 3 hidden layers and a dense layer (output) to predict the normalized closing stock price.

![Model Summary](https://github.com/kshitij-raj/Stock-Price-Prediction-LSTM/blob/main/PNG_Files/ModelSummary.png)



The model was compile using the mean squared error as loss function and to reduce the loss or to optimize the algorithm, I used the Adam optimizer.

![Model Loss Score](https://github.com/kshitij-raj/Stock-Price-Prediction-LSTM/blob/main/PNG_Files/ModelLoss.png)


The model was fit and passed to the training features and a test data set was created to get predictions.

![Model Prediction](https://github.com/kshitij-raj/Stock-Price-Prediction-LSTM/blob/main/PNG_Files/ModelPrediction.png)


Lastly forecast the stock price of the 30 days.

![Model Forecast](https://github.com/kshitij-raj/Stock-Price-Prediction-LSTM/blob/main/PNG_Files/ModelForcast.png)
