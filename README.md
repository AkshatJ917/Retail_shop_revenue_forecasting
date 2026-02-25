# 📈 Revenue Forecasting — Online Retail Store

> **An end-to-end Time Series Forecasting project using ARIMA and SARIMA on the Online Retail II dataset (1M+ transactions).**

---

## 📖 Overview

Forecasting future revenue helps businesses plan inventory, staffing, and budgets more effectively. This project builds a complete **time series forecasting pipeline** — from raw transaction data to a final **SARIMA model achieving 19.32% MAPE** — with clear seasonal revenue predictions for early 2012.

---

## 🔄 Workflow

```
🧹 Data Cleaning
      ↓
📅 Monthly Revenue Aggregation
      ↓
📊 Time Series Visualization
      ↓
🧪 ADF Stationarity Test
      ↓
📉 ACF & PACF Analysis
      ↓
🤖 ARIMA Model (Baseline)
      ↓
🔍 Residual Diagnostics
      ↓
⬆️  SARIMA Upgrade (Seasonal)
      ↓
📏 Evaluation: MAE, RMSE, MAPE
      ↓
🔮 Forecast Jan–Mar 2012
```

---

## 🤖 Model Comparison

| Model | MAPE | MAE | RMSE |
|:---|:---:|:---:|:---:|
| **ARIMA(1,0,0)** | 37.46% | £396,527 | £405,132 |
| ⭐ **SARIMA(1,0,0)(1,0,0)[12]** | **19.32%** | **£202,579** | **£204,157** |

> 🏆 **SARIMA reduced error by ~50%** by capturing the yearly holiday season pattern!

---

## 🔮 Final Forecast (Jan–Mar 2012)

| Month | Forecasted Revenue | 95% Confidence Range |
|:---|:---:|:---|
| **December 2011** | £736,554 | £381,496 – £1,091,611 |
| **January 2012** | £703,259 | £222,321 – £1,184,196 |
| **February 2012** | £595,424 | £30,492 – £1,160,356 |

> 📉 Post-holiday cooldown trend predicted correctly — consistent with real retail seasonality!

---

## 📊 Key Insights

- 🎄 **Strong yearly seasonality** — Revenue peaks every **October/November** (holiday shopping) and drops in early Q1
- ❌ **Plain ARIMA failed** to capture seasonal spikes — MAPE of 37.46%
- ✅ **SARIMA fixed it** — the `ar.S.L12` term learned from the same month last year
- ⚠️ **Data limitation** — Only 24 months available; more data would narrow confidence intervals significantly
- 🧹 **December 2011 removed** — Incomplete month data was causing artificial errors in evaluation

---

## 🛠️ Tech Stack

| Tool | Purpose |
|:---|:---|
| `Python` | Core language |
| `Pandas & NumPy` | Data processing |
| `Statsmodels` | ARIMA & SARIMA models |
| `pmdarima` | auto_arima model selection |
| `Scikit-learn` | Evaluation metrics |
| `Matplotlib` | Visualizations |

---

## **Conclusion** — Revenue Forecasting Project
This project successfully built an end-to-end revenue forecasting pipeline for an online retail store using the Online Retail II dataset. After cleaning and aggregating over 1 million transactions into a monthly time series, the ADF test confirmed stationarity and ACF/PACF plots guided model selection. The baseline **ARIMA(1,0,0)** model achieved a **MAPE** of **37.46%** but struggled to capture the **strong yearly holiday season spikes**. Upgrading to **SARIMA(1,0,0)(1,0,0)[12]** — which explicitly models the **12-month seasonal cycle** — reduced the **MAPE** to **19.32%**, cutting errors by **nearly 50%**. The final model **correctly predicted a post-holiday revenue cooldown** for early 2012, demonstrating that for retail data, handling seasonality is the single most impactful improvement a forecasting model can make.
