#  Sales Prediction Report

##  Project Overview
This project aimed to analyze historical sales data and build a regression model that predicts sales revenue based on key business features. The goal was to identify which factors influence revenue and build a reliable predictive model for future planning.

---

##  Dataset Description

- **Source**: [https://www.kaggle.com/kyanyoga/sample-sales-data]  
- **Rows**: ~2,823 
- **Columns after cleaning**:  
  `QUANTITYORDERED`, `PRICEEACH`, `ORDERLINENUMBER`, `SALES`, `ORDERDATE`, `STATUS`,  
  `QTR_ID`, `MONTH_ID`, `YEAR_ID`, `PRODUCTLINE`, `MSRP`, `PRODUCTCODE`,  
  `CUSTOMERNAME`, `ADDRESSLINE1`, `CITY`, `COUNTRY`, `DEALSIZE`

###  Cleaning Performed
- Removed columns with missing or irrelevant values
- Handled encoding issues during CSV read
- Verified no missing values remained

---

##  Feature Engineering

### Features used for model:
- `QUANTITYORDERED`  
- `PRICEEACH`  
- `ORDERLINENUMBER`  
- `MONTH_ID`  
- `YEAR_ID`  
- `MSRP`  
- One-hot encoded variables:
  - `STATUS`, `PRODUCTLINE`, `DEALSIZE`, `COUNTRY`

Target Variable: `SALES`

---

##  Model Development

### Models Trained:
- **Linear Regression** (Baseline model)
- **Random Forest Regressor** (Main model)

### Train-Test Split:
- 80% training, 20% testing
- Used `train_test_split` with a random seed for reproducibility

---

##  Evaluation Metrics

| Metric        | Value (Random Forest) |
|---------------|------------------------|
| R² Score      | ~0.9232857627258035        |
| RMSE          | 578.661575870331 |
| MAE           | 272.17282318584085 |

The Random Forest outperformed the baseline linear regression in all metrics.

---

##  Feature Importance

Top 5 most important features (Random Forest):

1. `PRICEEACH`
2. `QUANTITYORDERED`
3. `MONTH_ID`
4. `PRODUCTLINE_[X]`
5. `DEALSIZE_Medium`

> This suggests pricing and product demand strongly influence revenue.

---

##  Conclusion & Recommendations

- Pricing and volume of orders are the most critical revenue drivers.
- Medium-sized deals generate the most income.
- Sales show monthly seasonality—useful for planning inventory.

### 📌 Future Work
- Try model tuning (GridSearchCV)
- Deploy as a Streamlit dashboard
- Add time-series forecasting (e.g. Prophet or ARIMA)
- Incorporate customer-level behavioral features

---

## 🛠️ Tools Used
- Python (Pandas, Seaborn, Scikit-learn)
- Jupyter Notebook
- Visual Studio Code


