# 🌫️ Urban Air Pollution Forecasting

> Predictive analytics for environmental public health decision-making — XGBoost model achieving **34% RMSE improvement** over statistical baseline.

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python)
![XGBoost](https://img.shields.io/badge/XGBoost-ML-orange?style=flat-square)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?style=flat-square)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)

---

## 📌 Business Problem

Urban authorities relied on a static monthly reporting model with a **5–7 day lag**, forcing reactive rather than proactive public health decisions. High-pollution events were identified only after they occurred, exposing communities to avoidable health risks.

**Business need:** Reliable 24–72 hour AQI forecasts to enable timely public health alerts and proactive resource allocation.

---

## 🎯 Project Objective

Build and benchmark multiple forecasting models to predict Air Quality Index (AQI) levels 24–72 hours in advance, and deliver findings via an interactive Power BI dashboard for non-technical stakeholders.

---

## 📊 Key Results

| Metric | Value |
|---|---|
| Best Model | XGBoost |
| RMSE (XGBoost) | **11.2** |
| RMSE (ARIMA Baseline) | 17.0 |
| Improvement over Baseline | **34%** |
| Directional Accuracy | **91%** |
| Forecast Lead Time | **72 hours** |
| Earlier Alert Capability | **48 hours** vs old system |

---

## 🛠️ Tools & Technologies

| Category | Tools |
|---|---|
| Language | Python 3.10 |
| ML Models | XGBoost, Random Forest, ARIMA (Statsmodels) |
| Data Processing | Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn, Power BI |
| Environment | Jupyter Notebook |

---

## 🔄 Approach

### 1. Requirements Gathering
- Conducted stakeholder analysis to identify key environmental KPIs
- Translated policy goals into measurable technical specifications covering 100% of priority user stories

### 2. Data Collection & Cleaning
- Sourced 3 years of hourly AQI measurements across multiple monitoring stations
- Resolved **12% missing values** via time-series interpolation
- Validated data integrity before downstream modelling

### 3. Exploratory Data Analysis (EDA)
- Decomposed time-series into trend, seasonality, and residual components
- Built correlation heatmaps — identified temperature and wind speed as top predictors
- Discovered significant weekday vs. weekend AQI patterns enabling differentiated advisories

### 4. Feature Engineering
- Lag features (1h, 6h, 24h, 48h)
- Rolling averages (6h, 12h, 24h windows)
- Temporal features (hour of day, day of week, month, season)
- Meteorological features (temperature, wind speed, humidity)
- Pollutant features (NO2, PM2.5)

### 5. Model Development & Benchmarking
- **ARIMA** — statistical baseline using auto-selected (p,d,q) parameters
- **Random Forest** — ensemble method with 100 estimators, max_depth=10
- **XGBoost** — gradient boosting with learning_rate=0.05, n_estimators=300
- Evaluated using 80/20 train-test split with time-series cross-validation

### 6. Model Evaluation
- Primary metric: **RMSE** (aligned to operational threshold of <15 AQI units)
- Secondary metrics: MAE, Directional Accuracy
- XGBoost selected as production model

### 7. Dashboard Delivery
- Built Power BI dashboard with live AQI forecasts, risk-band KPI cards, and historical trends
- Designed for non-technical urban planners and public health communicators
- Delivered executive brief summarising findings and business recommendations

---

## 📈 Feature Importance (XGBoost)

| Rank | Feature | Importance Score |
|---|---|---|
| 1 | Temperature (°C) | 0.31 |
| 2 | Wind Speed (km/h) | 0.24 |
| 3 | Humidity (%) | 0.18 |
| 4 | NO2 (μg/m³) | 0.13 |
| 5 | PM2.5 (μg/m³) | 0.09 |
| 6 | Hour of Day | 0.05 |

---

## 💼 Business Impact

- Forecast accuracy enables public health alerts up to **48 hours earlier** than the previous system
- Reduces reactive emergency spending by supporting proactive resource deployment
- Reusable model framework — scalable across multiple monitoring stations and cities
- Power BI dashboard reduces report preparation time by ~4 hours/week

---

## 📁 Project Structure

```
air-pollution-forecasting/
├── data/
│   └── aqi_daily_data.xlsx          # Cleaned dataset (sample)
├── notebooks/
│   ├── 01_eda.ipynb                 # Exploratory data analysis
│   ├── 02_feature_engineering.ipynb # Feature creation
│   └── 03_model_benchmarking.ipynb  # ARIMA vs RF vs XGBoost
├── dashboard/
│   └── AQI_Dashboard_PowerBI.xlsx   # Power BI data source
└── README.md
```

---

## 👤 Author

**Vinit Agrawal** — Business Analyst  
Master of Business Analytics, Kaplan Business School, Adelaide  
[LinkedIn](https://www.linkedin.com/in/vinit-agrawal-analyst/) · [Portfolio](https://vinit-agrawal.github.io)
