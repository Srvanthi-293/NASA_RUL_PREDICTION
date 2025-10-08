# NASA_RUL_PREDICTION

# 🚀 Remaining Useful Life (RUL) Prediction — NASA Turbofan Engine Degradation Dataset

This project predicts the **Remaining Useful Life (RUL)** of jet engines using machine learning models trained on the **NASA CMAPSS (Commercial Modular Aero-Propulsion System Simulation)** dataset.  
The dataset was obtained from **Kaggle** — [NASA Turbofan Engine Degradation Simulation Data Set](https://www.kaggle.com/datasets/behrad3d/nasa-cmaps).

---

## 📊 Project Overview

Jet engines degrade over time due to wear and tear.  
This project builds regression models to estimate how many operational cycles remain before an engine fails.

By predicting RUL, maintenance teams can:
- **Plan maintenance proactively** (before failure)
- **Reduce downtime**
- **Optimize spare parts inventory**
- **Extend equipment life**

---

## ⚙️ Workflow Summary

1. **Load the dataset** (`train_FD001.csv`)
2. **Preprocess and clean data**
   - Assign column names
   - Handle missing values
   - Compute Remaining Useful Life (RUL)
3. **Feature scaling** using `MinMaxScaler`
4. **Model training and evaluation**
   - Linear Regression
   - Decision Tree Regressor
   - Random Forest Regressor
5. **Evaluate models** with RMSE and R² metrics

---

Each row represents an engine cycle with 26 columns.

| Type | Features |
|------|-----------|
| Identification | `engine_id`, `cycle` |
| Operating Settings | `Altitude`, `Speed`, `Angle` |
| Sensor Readings | 21 condition-monitoring sensors |
| Target | Computed Remaining Useful Life (RUL) |

Example:

| engine_id | cycle | total_temp_at_fan_inlet | ... | RUL |
|------------|--------|--------------------------|-----|-----|
| 1 | 1 | 518.7 | ... | 191 |
| 1 | 100 | 532.1 | ... | 91 |
| 1 | 200 | 559.3 | ... | 0 |

---

## 🧩 Model Evaluation Results

| Model | RMSE ↓ | MSE ↓ | R² ↑ | Notes |
|--------|---------|--------|------|-------|
| **Linear Regression** | 44.30 | 1962.93 | 0.578 | Baseline linear model |
| **Random Forest** | 41.29 | 1704.79 | 0.834 | Best overall performer |
| **Decision Tree** | 61.52 | 3785.07 | 0.187 | Overfitting, lower accuracy |

✅ The **Random Forest Regressor** achieved the **best RUL prediction performance**, balancing accuracy and generalization.
