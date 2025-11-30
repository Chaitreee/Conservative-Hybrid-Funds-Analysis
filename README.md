# Conservative Hybrid Mutual Funds – EDA & Machine Learning Project

This project performs **Exploratory Data Analysis (EDA)**, **Feature Engineering**, **Regression Modeling**, **Classification Modeling**, and **NAV Time-Series Forecasting** for Conservative Hybrid Mutual Funds in India.

The analysis is based on three datasets:

- **analytics.csv** – scheme-level performance, return & risk metrics  
- **nav_values.csv** – historical NAV time-series data  
- **portfolio_assets.csv** – portfolio composition & CRISIL ratings  


## Project Objectives

### ✔ 1. Data Cleaning & Preprocessing
- Standardized column names  
- Fixed missing or invalid values  
- Transformed NAV wide-format → long-format  
- Forward-filled NAV for time-series continuity  
- Made datasets ML-ready (numeric + categorical features)


## 2. Exploratory Data Analysis (EDA)

Performed detailed analysis across all funds, covering:

- Return analysis: 1Y, 3Y, 5Y, 10Y  
- SIP return analysis (3Y, 5Y, 10Y)  
- Risk metrics: Sharpe, Sortino, Beta, Alpha, Std Deviation  
- AUM trends & category distributions  
- Correlation heatmaps  
- Portfolio diversification & asset allocation  
- NAV movement trends over time  

### **Key Insights:**
- Longer-term returns show moderate positive correlation  
- Sharpe & Sortino strongly relate to Return Grade  
- Conservative Hybrid Funds have stable NAV movements  
- Portfolios show strong debt allocation with low volatility characteristics


## 3. Feature Engineering

### For Regression:
- Numeric feature scaling  
- One-hot encoding for categorical fields  
- Selected key performance metrics  

### For NAV Time-Series:
Created predictive features:
- **Lag features** (1, 3, 7, 14, 30, 60 days)  
- **Rolling means & standard deviations**  
- **Day-of-week & Day-of-month** seasonal variables  


## 4. Machine Learning Models

### **A) Regression (Predict 1-Year Return — analytics.csv)**  
Models implemented:
- Ridge Regression  
- Lasso Regression  
- Random Forest Regressor  

**Goal:** Identify which quantitative & qualitative factors best predict annual returns.


### **B) Time-Series Forecasting (NAV Prediction — nav_values.csv)**  
Models implemented:
- Random Forest Regressor (with lag features)  
- Ridge Regression
- Lasso Regression

NAV forecasting includes:
- Full NAV history used as input  
- Rolling and lag-based feature engineering  
- Smooth forward-fill handling for missing NAV days  



##  Key Results

### Regression:
- Ridge & Lasso outperform linear regression due to regularization  
- Sharpe Ratio, Sortino Ratio & Information Ratio are top predictors  

### Time-Series:
- NAV predictions are stable and accurate for short horizons  
- Lag + rolling feature engineering improves performance significantly  



##  Tech Stack

- **Language:** Python  
- **Libraries:**  
  `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `scipy`, `statsmodels`

---

##  How to Run

### Clone Repository:
```bash
git clone https://github.com/yourusername/hybrid-fund-eda.git
cd hybrid-fund-eda
