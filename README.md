# 🧠 Predict Calories from Biometric Data

> A regression challenge to predict calories burned using biometric and activity records.  
> Participated as part of Kaggle Playground Series S5E5.

---

## 🔍 Problem Overview

- **Task:** Predict total calories consumed
- **Type:** Supervised regression
- **Metric:** RMSLE (Root Mean Squared Log Error)
- **Dataset:** 750k training / 250k test samples

---

## 🧑‍💻 What I Learned

This project was not just about modeling — it was about structuring my ML thinking. I learned:

1. **Data Distribution Matters**  
   → Skewed target distributions can distort predictions; log-transforming helped align the loss function.

2. **Model Choice vs. Metric**  
   → RMSLE penalizes under-predictions more — an insight that influenced feature scaling and outlier treatment.

3. **Feature Engineering is King**  
   → Creating features like `EnergyProxy` (Intensity × Duration) had measurable impact.

4. **Practical XGBoost Usage**  
   → Early stopping, `eval_set`, and using validation fold properly allowed stable training.

5. **Organizing a Kaggle Pipeline**  
   → End-to-end flow from EDA → feature engineering → validation → inference → submission is now repeatable.

---

## 🧪 Experiment Summary

| Model         | CV Method        | RMSLE (val) | Notes                             |
|---------------|------------------|--------------|------------------------------------|
| XGBoostRegressor | train/test split (80:20) | 0.0629       | baseline model                     |
| Ridge          | train/test split | 0.074        | poor fit due to linear assumption |
| XGBoost tuned  | 5-Fold CV        | 0.058 (CV)   | better generalization              |

---

## 🔬 Key Features

| Feature       | Description                              |
|---------------|------------------------------------------|
| `BMI`         | Weight / Height²                         |
| `Intensity`   | Proxy for activity strength (HR + Temp)  |
| `EnergyProxy` | Duration × Intensity                     |

---

## 🚀 Room for Improvement

- Refine feature selection by importance or SHAP values
- Switch to full K-Fold validation pipeline
- Experiment with ensembling (Voting / Stacking)
- Better handling of outliers & target clipping

---

## 📎 Notes for Future Me

- Start from data distribution understanding, not from modeling.
- Never skip log-transform checks for regression metrics like RMSLE.
- Think: "If I had to redo this in 1 hour, what could I reuse or automate?"

---

## 🔗 Competition Link

[👉 View on Kaggle](https://www.kaggle.com/competitions/your-competition)
