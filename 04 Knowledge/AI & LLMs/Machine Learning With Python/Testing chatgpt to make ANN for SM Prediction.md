---
tags: [ai, machine-learning, python]
---

2024-10-17 00:11

Status: #baby 

Tags: [[AI]] [[Research]] [[Stock Market]]

# Testing chatgpt to make ANN for SM Prediction

Day 1: 17-10-2024
Program:

import yfinance as yf

import pandas as pd

import numpy as np

from sklearn.model_selection import train_test_split

from sklearn.preprocessing import MinMaxScaler

from tensorflow.keras.models import Sequential

from tensorflow.keras.layers import Dense, LSTM

import matplotlib.pyplot as plt

  

# Function to download stock data from Yahoo Finance

def get_stock_data(stock_symbol, start_date='2020-01-01', end_date='2024-12-31'):

stock_data = yf.download(stock_symbol, start=start_date, end=end_date)

return stock_data

  

# Function to calculate stock metrics

def calculate_stock_metrics(stock_data):

# 1. High minus Low price (H-L)

stock_data['H-L'] = stock_data['High'] - stock_data['Low']

# 2. Close minus Open price (O-C)

stock_data['O-C'] = stock_data['Close'] - stock_data['Open']

# 3. 7-day moving average (7 DAYS MA)

stock_data['7 DAYS MA'] = stock_data['Close'].rolling(window=7).mean()

# 4. 14-day moving average (14 DAYS MA)

stock_data['14 DAYS MA'] = stock_data['Close'].rolling(window=14).mean()

# 5. 21-day moving average (21 DAYS MA)

stock_data['21 DAYS MA'] = stock_data['Close'].rolling(window=21).mean()

# 6. 7-day standard deviation (7 DAYS STD DEV)

stock_data['7 DAYS STD DEV'] = stock_data['Close'].rolling(window=7).std()

return stock_data

  

# Function to save DataFrame to CSV

def save_to_csv(stock_data, stock_symbol):

filename = f"{stock_symbol}_stock_metrics.csv"

stock_data.to_csv(filename)

print(f"Data saved to {filename}")

  

# Function to load and preprocess stock data

def load_data(stock_symbol):

# Load the data generated from the variables program

filename = f"{stock_symbol}_stock_metrics.csv"

stock_data = pd.read_csv(filename, index_col='Date', parse_dates=True)

# Fill any missing values

stock_data.fillna(method='ffill', inplace=True)

stock_data.dropna(inplace=True) # Ensure no NaN values remain

return stock_data

  

# Function to create time series data for predicting next day's stock prices at hourly intervals

def prepare_data(stock_data, forecast_hours=24):

X = stock_data[[1]].values

y = stock_data['Close'].values.reshape(-1, 1)

# Normalize both features (X) and target (y)

scaler_X = MinMaxScaler(feature_range=(0, 1))

X_scaled = scaler_X.fit_transform(X)

scaler_y = MinMaxScaler(feature_range=(0, 1))

y_scaled = scaler_y.fit_transform(y)

# Create time series data

X_train = []

y_train = []

for i in range(forecast_hours, len(stock_data)):

X_train.append(X_scaled[i - forecast_hours:i])

y_train.append(y_scaled[i])

X_train, y_train = np.array(X_train), np.array(y_train)

return X_train, y_train, scaler_y

  

# Function to build the ANN model

def create_ann_model(input_shape):

model = Sequential()

  

# Input and hidden layers

model.add(LSTM(units=64, return_sequences=True, input_shape=(input_shape[1], input_shape[2])))

model.add(LSTM(units=32, return_sequences=False))

  

# Output layer for predicting stock price

model.add(Dense(units=1, activation='linear'))

# Compile the model

model.compile(optimizer='adam', loss='mean_squared_error')

return model

  

# Function to plot the predictions vs actual values

def plot_predictions(y_test, y_pred):

plt.figure(figsize=(10, 5))

plt.plot(y_test, color='blue', label='Actual Stock Price')

plt.plot(y_pred, color='red', label='Predicted Stock Price')

plt.title('Stock Price Prediction')

plt.xlabel('Time (in hours)')

plt.ylabel('Stock Price')

plt.legend()

plt.show()

  

# Main function to integrate the entire process

def main():

# Step 1: User inputs stock symbol and end date

stock_symbol = input("Enter stock symbol (e.g., AAPL for Apple): ")

end_date = input("Enter end date (YYYY-MM-DD): ")

start_date = '2000-01-01' # Fixed start date for now

# Step 2: Fetch stock data from Yahoo Finance

stock_data = get_stock_data(stock_symbol, start_date, end_date)

# Step 3: Calculate stock metrics

stock_data_with_metrics = calculate_stock_metrics(stock_data)

# Step 4: Save metrics to CSV

save_to_csv(stock_data_with_metrics, stock_symbol)

# Step 5: Load data and prepare for ANN

stock_data_prepared = load_data(stock_symbol)

# Step 6: Prepare time series data (now returns scaler for inverse transform)

X, y, scaler_y = prepare_data(stock_data_prepared, forecast_hours=24)

# Step 7: Split data into training and test sets

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Step 8: Create and train the ANN model

model = create_ann_model(X_train.shape)

model.fit(X_train, y_train, epochs=50, batch_size=32, validation_split=0.2)

# Step 9: Predict stock prices on the test set

y_pred_scaled = model.predict(X_test)

# Inverse transform predictions to original scale

y_pred = scaler_y.inverse_transform(y_pred_scaled)

y_test_original = scaler_y.inverse_transform(y_test)

# Save the actual vs predicted values to a CSV file

output_df = pd.DataFrame({

'Actual Price': y_test_original.flatten(),

'Predicted Price': y_pred.flatten()

})

  

output_filename = f"{stock_symbol}_predictions.csv"

output_df.to_csv(output_filename, index=False)

print(f"Predictions saved to {output_filename}")

  

if __name__ == "__main__":

main()



# Program returns lot of values never right predictions



# References

