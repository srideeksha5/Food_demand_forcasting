# Food Demand Forecasting

An end-to-end machine learning solution to forecast food demand, helping meal delivery services manage inventory and staffing efficiently.

##  Project Overview

A food delivery company with multiple fulfillment centers needs accurate demand forecasts (e.g., weekly demand for meal-center pairs) to minimize waste from perishable inventory and avoid stockouts. This project transforms a time-series forecasting problem into regression and builds a predictive pipeline using advanced feature engineering and CatBoost modeling.

##  Key Steps & Techniques

### 1. **Data Transformation**  
- Applied log-transformations to address right-skewed distributions in `num_orders`, `base_price`, and `checkout_price`.  
- Created lag features (lags of 10–12 weeks) and exponentially weighted means to capture trends.

### 2. **Feature Engineering**  
- Engineered features like `checkout_price - base_price`, lag differences, and rolling statistics.  
- Focused on regularized model behavior to prevent overfitting.

### 3. **Cross-Validation Strategy**  
- Used the last 10 weeks (weeks 136–145) for validation to mimic the forecasting window (weeks 146–155).

### 4. **Modeling**  
- Trained a **CatBoost regressor**, achieving RMSLE ≈ 0.54.  
- Baseline (no feature engineering) produced RMSLE ≈ 1.58—highlighting the value of engineered features.

### 5. **Insights & Lessons**  
- Rolling mean/median over longer windows (26–104 weeks) and geographic features had low predictive power.  
- Suggested future improvements:
  - Advanced encoding: target, frequency, hashed categories  
  - Additional models (XGBoost, LightGBM, Prophet, ARIMA) or ensembling strategies  
  - Further hyperparameter tuning for model robustness

##  How to Use

1. Clone this repository and navigate to the project folder.  
2. Open `food_demand_forecast.ipynb` or `FDF_catboost.ipynb` in Jupyter.  
3. Run the notebooks to replicate data preprocessing, modeling, and evaluation.

##  Your Contributions (Optional)

- Use time-series models like **Prophet** or **ARIMA** for comparison.  
- Incorporate external data like weather, holidays, or promotions to enhance forecast accuracy.  
- Deploy as a web app (Flask/Streamlit) with chart visualizations and date-based forecasting inputs.

---

* This README is personalized for my usage—forked, cleaned, and enhanced for clarity and presentation.*
