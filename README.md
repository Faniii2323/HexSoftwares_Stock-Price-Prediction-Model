# HexSoftwares_Stock-Price-Prediction-Model
Task 2,  Project 01 Stock Price Prediction


# Stock Price Prediction Model using Machine Learning and Deep Learning Algorithms

## Project Overview

This project was developed as part of the **HexSoftwares Machine Learning Internship**.  
The objective of this project is to predict the **next trading day's closing stock price** using historical stock market data.

The dataset contains stock market features such as opening price, high price, low price, last traded price, closing price, total trade quantity, and turnover. The project applies both **Machine Learning** and **Deep Learning** models to compare their performance for stock price forecasting.

---

## Dataset

The project uses the dataset:

`NSE-Tata_Global_Beverages_Limited.csv`

### Dataset Features

The dataset contains the following columns:

| Column | Description |
|---|---|
| Date | Trading date |
| Open | Opening stock price |
| High | Highest stock price of the day |
| Low | Lowest stock price of the day |
| Last | Last traded stock price |
| Close | Closing stock price |
| Total Trade Quantity | Total number of shares traded |
| Turnover (Lacs) | Total turnover value in lacs |

### Dataset Summary

- Total rows: **1,235**
- Total columns: **8**
- Date range: **2013-10-08 to 2018-10-08**
- Missing values: **0**
- Duplicate rows: **0**

---

## Target Variable

The project predicts the next trading day's closing price.

A new target column is created:

```python
Next_Close = Close.shift(-1)
```

So the model learns from today's market data and predicts the next day's closing price.

---

## Exploratory Data Analysis- EDA

The notebook includes visual analysis of:

- Closing price trend over time
- Opening price trend over time
- High and low price trend
- Trading volume trend
- Turnover trend
- Close price distribution
- Correlation heatmap
- Moving average visualization

---

## Feature Engineering

Several new features were created to improve prediction performance:

| Feature | Description |
|---|---|
| Next_Close | Next day closing price |
| Price_Change | Difference between close and open price |
| Daily_Return_Percent | Daily return percentage |
| MA_7 | 7-day moving average |
| MA_14 | 14-day moving average |
| MA_30 | 30-day moving average |
| Close_lag_1 | Previous 1-day close price |
| Close_lag_2 | Previous 2-day close price |
| Close_lag_3 | Previous 3-day close price |
| Close_lag_7 | Previous 7-day close price |

After feature engineering, the final dataset contained:

- Rows: **1,205**
- Features used for training: **16**

---

## Data Splitting

Because stock data is time-series data, the notebook uses **chronological splitting**, not random splitting.

- First 80% data: Training set
- Last 20% data: Testing set

Training date range:

`2013-11-20 to 2017-10-16`

Testing date range:

`2017-10-17 to 2018-10-05`

---

## Models Used

### Machine Learning Models

1. Linear Regression
2. Random Forest Regressor
3. Support Vector Regressor
4. XGBoost Regressor
5. LightGBM Regressor

### Deep Learning Models

6. LSTM
7. GRU

---

## Evaluation Metrics

The models were evaluated using:

- MAE: Mean Absolute Error
- MSE: Mean Squared Error
- RMSE: Root Mean Squared Error
- R2 Score

---

## Model Performance

| Model | MAE | MSE | RMSE | R2 Score |
|---|---:|---:|---:|---:|
| Linear Regression | 4.3832 | 35.1218 | 5.9264 | 0.9533 |
| GRU | 21.6861 | 571.4744 | 23.9055 | 0.1648 |
| LSTM | 35.7426 | 1540.4392 | 39.2484 | -1.2514 |
| LightGBM Regressor | 54.3131 | 3682.4853 | 60.6835 | -3.8955 |
| Random Forest Regressor | 57.4769 | 4051.4413 | 63.6509 | -4.3860 |
| XGBoost Regressor | 59.0815 | 4229.2845 | 65.0329 | -4.6224 |
| Support Vector Regressor | 79.6074 | 8193.6445 | 90.5188 | -9.8926 |

---

## Best Performing Model

The best-performing model was:

**Linear Regression**

It achieved:

- MAE: **4.3832**
- RMSE: **5.9264**
- R2 Score: **0.9533**

This means Linear Regression gave the most accurate results on the test data in this notebook.

---

## Future Price Prediction Result

The notebook also includes a simple next-day price prediction system.

Example result from the notebook:

| Item | Value |
|---|---:|
| Current Close Price | 209.20 |
| Predicted Next Close Price | 209.93 |
| Expected Change | 0.73 |
| Expected Change Percentage | 0.35% |
| Prediction | Stock price may increase |

---

## Saved Outputs

The notebook saves important files in the `stock_prediction_outputs` folder:

- Best ML model
- Standard scaler
- Deep learning scalers
- Feature columns
- LSTM model
- GRU model
- Model performance comparison CSV
- Prediction results CSV

---



## Project Conclusion

This project successfully builds a stock price prediction system using historical stock market data. It applies both Machine Learning and Deep Learning techniques to predict the next day closing price.

Among all implemented models, **Linear Regression** achieved the best performance with the lowest RMSE and highest R2 Score.

The project demonstrates how historical financial indicators, moving averages, lag features, regression models, and neural networks can be used for stock price forecasting.

---

## Author

Fani2323
HexSoftware Internship Project
Computer Science
