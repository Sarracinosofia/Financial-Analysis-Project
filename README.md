# 📊 Financial Analysis of Tech Companies (2020–2024)


This data science project performs a multi-stage analysis of the stock performance of five major U.S. technology companies — Apple (AAPL), Microsoft (MSFT), Amazon (AMZN), Tesla (TSLA), and Alphabet (GOOGL) — over the period 2020 to 2024.

## 📌 Project Goals

- Analyze historical stock price performance
- Evaluate risk-return metrics and inter-stock relationships
- Engineer technical indicators and detect market anomalies
- Prepare a clean dataset for future predictive modeling

---

## 🚀 Tools Used

- Python (Jupyter Notebook)
- Pandas, NumPy, yfinance
- Matplotlib, Seaborn
- Technical indicator logic built from scratch (no pre-built libraries)

---

## 🧭 Project Structure

### 🔹 [Stage 1 – Exploratory Data Analysis](./1st_Analysis)

> Understand historical performance, daily returns, volatility, correlation, and Sharpe ratio.

**Key outputs:**
- Volatility heatmaps
- Rolling return plots
- Pairwise correlation visualizations
- Sharpe ratio comparison

---

### 🔹 [Stage 2 – Technical Analysis](./2_Technical_Analysis)

> Engineer time-based technical indicators and identify periods of market anomalies.

**Technical Indicators:**
- SMA/EMA (10, 20, 50, 100, 200 days)
- RSI (14-day)
- MACD (12, 26, 9)
- Bollinger Bands (SMA 20 ± 2σ)
- Rolling volatility
- Lagged features
- Anomaly detection (returns, RSI, volatility)

**Outputs:**
- Indicator plots per stock
- Anomaly graphs
- Final dataset for modeling: `df_model_ready.csv`

---

## ✅ Current Outcome

A well-documented, multi-step financial analysis pipeline producing a **structured dataset** enriched with engineered features — ready for machine learning in the next stage.

---

## 🔹 [Stage 3 – Predictive modeling](./3_MLprep)

> Train and evaluate regression models to predict next-day stock returns based on technical indicators.

**Models Used:**
- Linear Regression
- Random Forest Regressor
- XGBoost Regressor

**Target variable:**
- `target_1d` = (Close_t+1 / Close_t) - 1 → next-day return

**Key tasks:**
- Time-based train/test split (80% train, 20% test)
- Model training per stock
- Evaluation using:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)
  - R² Score
- Feature importance visualization (Random Forest & XGBoost)

**Outputs:**
- Model performance charts
- Saved models: `outputs/trained_models/`
- Metric comparison: `outputs/models/comparison_results_clean.csv`
- Feature importance plots: `outputs/graphs/models/`

> While results showed low predictive power (low R²), this phase helped consolidate modeling techniques and opened avenues for future improvements such as feature optimization or alternative targets.
