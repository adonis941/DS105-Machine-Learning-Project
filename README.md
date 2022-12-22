# Future Price Prediction of Bitcoin & Ethereum Prices using LSTM Networks

This project aims to predict the prices of Bitcoin and Ethereum for the next 6 months after the present day, taken as 22 Nov 2022. The initial dataset was downloaded from Kaggle, however,it was found that only data up till Jul 2021 was present. The rest of the data was collected from Yahoo! Finance. The predictions made in this project may be helpful to amateur retail investors new to cryptocurrency investing in getting a preliminary sense of the possible investment prospects of Bitcoin and Ethereum

Data was read into a pandas Dataframe and data cleaning was performed by checking for missing values and duplicated rows. 'Date' column was also converted from string into a datetime object and preliminary data visualization was perfromed using matplotlib.

Data was then split into training and test sets, normalized using sklearn MinMaxScaler and converted to numpy arrays as a pre-requisite to fitting into an LSTM model. Training and test sets were further pre-processed such that 60 days of historical data will be used to predict the next day price and reshaped into a 3D numpy array to train an LSTM model.

Setting up of the LSTM network was performed using tensorflow keras library. A Sequential LSTM model was used as sequential time series data is being dealt with here. LSTM model was trained with Root-Mean-Squared-Error(RMSE) chosen as the evaluation metric. Resulting predictions were visualized using matplotlib to validate the accuracy of the model.

For future price predictions, a moving 60 days window was created to continue predicting prices on dates where no data was available yet. On such dates, predicted prices will be taken as real world data and used as part of the 60 days data to predict the next day forward. The predicted prices for the next 187 days up till 1 June 2023 were plotted using matplotlib to visualize the preliminary sentiment of both cryptocurrencies.

It should be noted that in the real world, there are other factors at play which influence cryptocurrency prices including prevailing economic conditions, economic policies enacted by major world powers as well as public sentiment towards cryptocurrencies. Investing based on predictions made based purely on time & historical price trends is highly risky and is highly discouraged. However, it may be used as a preliminary gauge on which way the prices may be leaning towards.

The LSTM model used in this project was also found to have an error of 15-20% between predictions and real world data. Further fine-tuning of the hyperparameters may yield a more accurate model, otherwise a rough manual compensation may be required to have a more accurate prediction.


