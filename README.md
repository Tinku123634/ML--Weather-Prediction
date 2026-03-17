# Implementation of Random Forest Algorithm for Weather Prediction
## AIM:
To write a program to predict daily temperature , PM2.5 pollution level and Energy based on environmental sensor data using Random Forest Algorithm.

## Problem Statement and Dataset

Problem Statement:
To develop a model using the Random Forest Algorithm to predict temperature, PM2.5 level, and energy consumption based on environmental sensor data like humidity, wind speed, and pressure.
Dataset:
The dataset contains environmental parameters such as:Humidity,Wind Speed,Pressure,Temperature,PM2.5,Energy Format: CSV file (weather_data.csv) Type: Numerical data

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import required Python libraries.
2.Load the weather dataset and preprocess the data.
3.Select features (hum, co2, illumination, pressure, pm2_5, pm10, wind_speed) and target (tem).
4.Split the dataset and train the Linear Regression model.
5.Predict the temperature and evaluate the model performance.

## Program:
```
/*
Program to implement the Random Forest Algorithm to predict daily temperature , PM2.5 pollution level and Energy based on environmental sensor data.
Developed by: S.Tinku
RegisterNumber: 25006607


import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

df = pd.read_csv("weather-station-eee-block_2024_07_13.csv")

df['time'] = pd.to_datetime(df['time'])

df = df.fillna(df.mean(numeric_only=True))

X = df[['hum','co2','illumination','pressure','pm2_5','pm10','wind_speed']]
y = df['tem']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = LinearRegression()
model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("R2 Score:", r2_score(y_test, y_pred))
print("MSE:", mean_squared_error(y_test, y_pred))

plt.scatter(y_test, y_pred)
plt.xlabel("Actual Temperature")
plt.ylabel("Predicted Temperature")
plt.title("Actual vs Predicted Temperature")
plt.show()

*/
```

## Output:

<img width="813" height="564" alt="Screenshot 2026-03-17 083511" src="https://github.com/user-attachments/assets/4d5a507d-cfbf-4015-b443-aca47f5c981e" />

## Result:

The Linear Regression model was successfully trained to predict temperature (tem) using weather parameters. The model performance was evaluated using R² Score and Mean Squared Error (MSE), and the Actual vs Predicted Temperature graph was generated.

