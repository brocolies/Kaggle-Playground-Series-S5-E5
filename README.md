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

	0.	Importance of initial data exploration and pipeline planning
At first, I skipped building a high-level overview of the problem and jumped into feature interpretation. Later, I realized that key features like gender significantly affected numeric columns, forcing me to revise earlier steps.
From this, I learned the importance of sketching out the full pipeline and structure before starting detailed work.
	1.	Target transformation using QuantileTransformer
Learned to map target values to a normal distribution using QuantileTransformer(output_distribution='normal'). This helps stabilize variance and align with model assumptions. Crucially, only transform() is applied to validation/test sets (to preserve generalization), and inverse_transform() is used after prediction to restore the original scale.
	2.	EDA is not just interpretation—it’s decision-making
Rather than passively reading charts, EDA requires actively designing how to process the data. This shift in perspective helped me better control how features are treated during preprocessing.
	3.	Outliers and skewed values are not always ‘bad’
Instead of removing extreme values outright, I learned it’s often more effective to flag them as indicators. This provides the model with contextual signals, preserving information rather than discarding it.

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
