# 📈 Time Series Forecasting & Machine Learning on Stock Data

## 🚀 Project Overview
The primary goal of this project is to **compare the performance and behavior of different forecasting models** on financial time series data.

This project explores both:
- **Traditional statistical models (ARIMA, SARIMA)**
- **Modern machine learning models (Random Forest, Gradient Boosting, XGBoost, Voting Regressor)**

The workflow includes:
- Rigorous data preprocessing  
- Stationarity testing  
- Feature engineering  
- Multi-model implementation  
- Performance comparison  

The objective is to better understand **stock price dynamics and predictive patterns**.

---

## 📊 Dataset
The dataset consists of historical stock price data for **Google (GOOGL)**.

### Features include:
- **OHLC Data**: Open, High, Low, Close prices  
- **Volume**: Trading volume  
- **Returns**:
  - Daily returns  
  - Intraday returns  

---

## 🛠️ Tech Stack
- **Language**: Python  
- **Data Analysis**: Pandas, NumPy  
- **Visualization**: Matplotlib, Seaborn  
- **Statistical Modeling**: Statsmodels  
  - ADF Test  
  - ARIMAX  
  - SARIMAX  
- **Machine Learning**:  
  - Scikit-learn
  - Random Forest
  - XGBoost
  - Grafient Boosting

---

## 📈 Methodology

### 1. Exploratory Data Analysis (EDA)
- Visualized price trends and volatility  
- Identified patterns in stock movement  
- Built features to capture **market behavior**

### Feature Engineering:
- Lag features (previous time steps)
- Return features
- Rolling window statistics  
- Volatility-based features  

### Stationarity Testing:
- Applied **Augmented Dickey-Fuller (ADF) Test**  
- Ensured data suitability for statistical models  

---

### 2. Traditional Statistical Models

#### 🔹 ARIMAX (AutoRegressive Integrated Moving Average with exogenous variables)
- Captures **linear dependencies** in time series  
- Handles non-stationarity using differencing  

#### 🔹 SARIMAX (Seasonal ARIMA with exogenous variables)
- Extends ARIMA to model:
  - Seasonality  
  - Trend components  

---

### 3. Machine Learning Approaches

#### Feature Engineering for ML:
- `Volatility_ratio`  
- `Gap_Return`  
- Lag variables:
  - `Close_Return_lag1`  
  - `High_Return_lag6`  
- Rolling statistics (mean, std)
- etc

---

#### 🌲 Random Forest Regressor
- Ensemble learning method  
- Captures **non-linear relationships**  
- Robust to noise  

---

#### ⚡ XGBoost , Gradient Boosting
- Gradient boosting algorithm  
- High performance and efficiency  
- Provides **feature importance insights**  

---

## 🔑 Key Features & Insights

### 📌 Important Predictors Identified:
- **Short-term Momentum**:
  - Strong influence of 1-day lag features  
  - Intraday returns are highly predictive  

- **Volatility Metrics**:
  - 2-day, 5-day, and 10-day volatility ratios  
  - Key drivers of price fluctuations  

---

### 📊 Performance Comparison

| Model          | Strengths                                    |
|----------------|----------------------------------------------|
| ARIMA / SARIMA | Interpretable, handles trend & seasonality   |
| Random Forest  | Captures non-linear relationships            |
| XGBoost        | High accuracy, feature importance insights   |
| Gradient Boost | Better accuracy, feature importance insights |

---

