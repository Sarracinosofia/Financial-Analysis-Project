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

---

### 🔹 [Stage 4 – Modeling Improvement](./4_Modeling_Improvement)

> Refine predictive modeling through advanced feature engineering, model tuning, and interpretability analysis.

**Key improvements:**
- Engineered additional features including multiple momentum indicators (momentum_3, momentum_7, momentum_14 and their scaled versions), rolling volatility, MACD histogram/signal, and expanded lag features.
- Applied hyperparameter tuning for Random Forest and XGBoost regressors, optimizing model performance for each stock.
- Integrated classification tasks (Logistic Regression, Random Forest Classifier, XGBoost Classifier) for predicting price direction.
- Performed model interpretability analysis using feature importance and SHAP values to identify the most influential predictors—momentum-based features proved dominant.
- Conducted a comparative analysis of model performance: XGBoost achieved the lowest error metrics and highest R² scores among regression models; classification accuracy and F1 scores exceeded 98% across all models.
- Documented project limitations (e.g., lack of fundamental/sentiment data, market regime sensitivity) and provided recommendations for further improvement.

**Outputs:**
- Cleaned and well-commented final notebook: [`4_Modeling_Improvement.ipynb`](./4_Modeling_Improvement/4_Modeling_Improvement.ipynb)
- SHAP summary plots and feature importance visualizations
- Final evaluation and conclusions section

> This stage demonstrates how iterative feature engineering and model optimization can substantially improve predictive power and explainability in financial time series modeling, even within the constraints of purely technical datasets.

---

### ✅ Final thoughts & learnings

This project demonstrates the application of end-to-end data science techniques to financial market analysis. Through the use of engineered technical indicators and machine learning models, it was possible to extract insights, detect anomalies, and predict short-term price movements across five major tech stocks.

📌 **Top-performing model:**  
XGBoost Regressor delivered the strongest performance in regression tasks with an **R² of 0.86**, outperforming Random Forest across all error metrics. In classification, all models surpassed **98% accuracy**, with XGBoost and Random Forest leading the scores.

📈 **Most predictable stock:**  
Apple (AAPL) showed the most stable behavior and best model performance, while Tesla (TSLA) proved the most volatile and difficult to predict. The other stocks (MSFT, AMZN, GOOGL) showed intermediate predictability.

📊 **Most influential features:**  
Momentum indicators (especially 3-day and 7-day), Bollinger Bands, and rolling volatility were among the top predictors. RSI had low impact in this setup.

**Limitations:**  
- Purely technical analysis (no fundamentals or news data).  
- Data limited to 2020–2024.  
- No trading costs or portfolio simulation included.  
- Predictive power may vary in other market conditions.

**Next steps:**  
- Integrate sentiment, fundamentals, or macroeconomic indicators.  
- Backtest realistic trading strategies.  
- Explore LSTM, Transformer-based models for sequential patterns.  
- Deploy a lightweight dashboard or alert system.

This project stands as a complete showcase of applied data science in finance — with structured notebooks, clear visuals, model evaluation, and documented insights.

