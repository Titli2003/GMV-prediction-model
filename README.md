# Tata Steel Aashiyana GMV Forecasting Project

This project is developed to forecast Gross Merchandise Value (GMV) for Tata Steel's Aashiyana platform using time series modeling and regressors. It includes a complete data pipeline, feature engineering, model training with Prophet, and deployment via FastAPI.

## Project Overview

Tata Steel Aashiyana is an e-commerce platform for steel products. This project predicts future GMV based on historical sales, order behavior, and external factors (e.g., stock prices, economic events, etc.). The aim is to provide actionable insights for sales planning and business decisions.

## Tech Stack

- **Python 3.11.10**
- **Prophet** – Time series forecasting
- **FastAPI** – For API endpoints
- **Pandas & NumPy** – Data processing
- **Matplotlib** – Visualization
- **Joblib** – Model serialization
- **Scikit-learn** – Evaluation metrics
##  Key Files

| File | Description |
|------|-------------|
| `fastapi_app.py` | REST API with endpoints for updating features, making forecasts, and downloading results |
| `model.pk1` | Trained Prophet model |
| `last_row.csv` | Last row of lag features used for future predictions |
| `scaling_params.pk1` | Used for de-normalizing forecast values |
| `regressors_median.pk1` | Median values of regressors for use in forecasting |
| `cap_value.pk1` | Capacity value for Prophet’s growth model |
| `prediction_log.csv` | Saved forecast results |

## API Endpoints (FastAPI)

- `POST /update_features`: Updates model features with new data
- `GET /predict_gmv`: Returns forecasted GMV between specified dates
- `GET /download_forecast`: Returns saved forecast
- `GET /auto_update_and_predict`: Fetches latest data, updates features, and returns forecast

## Forecast Features

- Historical GMV trends
- Lag features: 1, 2, 3, 7, and 14-day lag
- Rolling average GMV (7 days)
- Regressors: Stock price, steel price, discount, war indicator, etc.
- Log transformation and scaling for better accuracy

## Insights Generated

- Daily and monthly GMV forecasts (₹ Crores)
- Best and worst performing days
- Top and bottom months in the forecast period
- Forecast accuracy (MAPE & % Accuracy)

## How to Run

1. Clone the repository
2. Install requirements:
   ```bash
   pip install -r requirements.txt
Developed as part of Tata Steel's internal data science initiative. Special thanks to the Aashiyana analytics team for dataset inputs and validation.
