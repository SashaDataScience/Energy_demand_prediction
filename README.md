# Energy Demand Forecasting

Forecasting electricity demand using historical energy consumption data and time-series / machine learning methods.

## Overview

This project explores methods for forecasting energy demand based on historical electricity consumption patterns.

The main objective is to investigate how different forecasting approaches perform on time-dependent energy demand data and to identify the factors that contribute to accurate forecasts.

The project focuses on:

* Exploratory data analysis of energy demand
* Time-series patterns and seasonality
* Feature engineering
* Forecasting model development
* Model evaluation
* Comparison of forecasting approaches

## Project Structure

```text
energy-demand-forecasting/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── energy_demand_analysis.ipynb
│
├── src/
│   └── ...
│
├── README.md
└── requirements.txt
```

## Dataset

The analysis uses two historical datasets covering the Baltic countries: Estonia, Latvia, and Lithuania.

### 1. Hourly electricity market data — Syspower

Hourly electricity market data are provided in **Central European Time (CET)**.

| Variable           | Unit  | Estonia              | Latvia               | Lithuania            |
| ------------------ | ----- | -------------------- | -------------------- | -------------------- |
| Electricity demand | GWh   | `CNPEE`              | `CNPLV`              | `CNPLT`              |
| Wind generation    | MWh   | `PROEEWINDON_ENTSOE` | `PROLVWINDON_ENTSOE` | `PROLTWINDON_ENTSOE` |
| Solar generation   | MWh   | `PROEESOL_ENTSOE`    | `PROLVSOL_ENTSOE`    | `PROLTSOL_ENTSOE`    |
| Day-ahead price    | €/MWh | `SPOTEE`             | `SPOTLV`             | `SPOTLT`             |

### 2. Historical weather data

Historical weather data are provided in **Coordinated Universal Time (UTC)**. Weather variables represent **country-wide averages**.

| Variable          | Description                         | Unit |
| ----------------- | ----------------------------------- | ---- |
| `t2m`             | Temperature at 2 m above sea level  | °C   |
| `tp`              | Total precipitation                 | m    |
| `solar_w_m`       | Solar radiation                     | W/m² |
| `wind_speed_10m`  | Wind speed at 10 m above sea level  | m/s  |
| `wind_speed_100m` | Wind speed at 100 m above sea level | m/s  |

> **Time zones:** The electricity market data are provided in CET, while the weather data are provided in UTC. The time zones are taken into account when combining the datasets.


## Exploratory Data Analysis

The analysis investigates the main characteristics of electricity demand, including:

* Trend over time
* Daily demand patterns
* Weekly seasonality
* Annual/seasonal effects
* Distribution of demand
* Autocorrelation
* Relationships between time-related features and demand

## Forecasting Methods

The project investigates several forecasting approaches.

### Baseline

A simple baseline model is used to establish a reference level of forecasting performance.

### Linear Regression

Linear regression is used as a machine-learning baseline with engineered temporal features.

Potential features include:

* Hour
* Day of week
* Month
* Lagged demand
* Rolling averages
* Seasonal indicators

### ARIMA / SARIMA

ARIMA models are considered for modelling the temporal structure of energy demand.

SARIMA extends ARIMA by explicitly modelling seasonal patterns, making it potentially useful for energy-demand data where recurring patterns are present.

### Machine Learning Models

Additional machine-learning approaches can be evaluated against the statistical forecasting models.

> Models will be added as the project develops.

## Evaluation

Forecasting performance is evaluated using metrics appropriate for continuous demand prediction.

The main evaluation metrics include:

* MAE — Mean Absolute Error
* RMSE — Root Mean Squared Error
* MAPE — Mean Absolute Percentage Error

Because this is a time-series problem, the data is split chronologically rather than randomly to avoid data leakage from the future into the training set.

## Results

Model performance will be compared using a dedicated test period representing unseen future observations.

| Model             | MAE | RMSE | MAPE |
| ----------------- | --: | ---: | ---: |
| Baseline          | TBD |  TBD |  TBD |
| Linear Regression | TBD |  TBD |  TBD |
| ARIMA             | TBD |  TBD |  TBD |
| SARIMA            | TBD |  TBD |  TBD |

The final results and interpretation will be updated as the analysis progresses.

## Key Questions

The project investigates questions such as:

* How predictable is electricity demand from historical observations?
* How important are daily and weekly seasonal patterns?
* Does explicitly modelling seasonality improve forecasting performance?
* How do statistical time-series models compare with machine-learning approaches?
* Which approach provides a useful balance between forecasting accuracy and model complexity?

## Future Improvements

Potential next steps include:

* Hyperparameter optimisation
* More advanced feature engineering
* Weather variables such as temperature and precipitation
* Holiday and calendar information
* Gradient boosting models
* More advanced time-series models
* Rolling / walk-forward validation
* Forecast uncertainty estimation
* Model deployment through an API
* Containerisation with Docker
* Automated model retraining and monitoring

## Technologies

* Python
* pandas
* NumPy
* matplotlib
* scikit-learn
* statsmodels
* Jupyter Notebook
* Git / GitHub

## Status

🚧 **Work in progress**

The project is currently focused on exploratory analysis and establishing baseline forecasting approaches. Additional models, evaluation and deployment components will be added progressively.
