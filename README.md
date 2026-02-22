# Household Energy Forecasting - XGBoost

# Overview
This project forecasts hourly household energy consumption using a predictive model trained on 80% of the data and 
tested on 20%. The dataset is processed so that all kW values are converted to 'kWh' per hour (unit), reflecting real energy usage.

The test set provides a representative sample, meaning if the model performs well here, it is expected to generalize to the full dataset.  

## Key Insights & Model Interpretation

1. Accurate Peak Capture
   - High consumption outliers (top 2%): Actual 3.17–5.63 kWh, Predicted 3.17–5.65 kWh  
   - Model slightly overestimates peaks (+0.02 kWh), showing it robustly captures extreme spikes.

2. Low Residuals / Error
   - RMSE = 0.228 kWh; 90% of normal consumption falls within 0–3.15 kWh  
   - Small residuals confirm the model is highly reliable for hourly forecasting, with well-calibrated predictions.

3. Balanced Predictions
   - Predicted min/max closely matches actual min/max (0.16–5.65 kWh vs 0.20–5.63 kWh)  
   - Indicates no systematic bias, suitable for operational deployment.

4. Feature Engineering Contribution
   - Temporal features (lags, rolling mean, sine/cosine) capture hourly, daily, and seasonal patterns, including morning/evening peaks  
   - Demonstrates the model’s ability to adapt to complex consumption behaviors.

5. Production-Ready & Business-Relevant
   - Total energy across dataset: 37,284 kWh (~2,237,025 kW)  
   - Forecasts can be translated into business metrics, e.g., cost per unit of energy, enabling **planning and budgeting decisions**  
   - Model is saved as `.pkl` and ready for deployment.


## Tools & Python Packages Used

- Python 3.12.7
- pandas– data manipulation
- numpy – numerical operations
- matplotlib & seaborn– plotting & visualization
- scikit-learn – train/test split, metrics
- xgboost – predictive model
- joblib – saving/loading the trained model
