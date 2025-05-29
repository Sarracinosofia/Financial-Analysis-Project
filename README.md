# 📊 Financial Analysis of Tech Companies (2020–2024)

This data science project performs a multi-stage analysis of the stock performance of five major U.S. technology companies — Apple (AAPL), Microsoft (MSFT), Amazon (AMZN), Tesla (TSLA), and Alphabet (GOOGL) — over the period 2020 to 2024.

---

## 📌 Project Goals

- Analyze historical stock price performance
- Evaluate risk-return metrics and inter-stock relationships
- Engineer technical indicators and detect market anomalies
- Prepare a clean dataset for future predictive modeling

---

## 🚀 Tools Used

- Python (Jupyter Notebook)
- pandas, NumPy, yfinance
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

### 🔹 [Stage 2 – Technical Analysis](./2nd_Analysis)

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

## 🔜 Stage 3 – (Coming Soon)

> Predictive modeling using supervised learning:
- Target: price direction, volatility regime, or anomaly prediction
- Models: logistic regression, random forest, XGBoost
- Feature importance analysis and backtesting

---

