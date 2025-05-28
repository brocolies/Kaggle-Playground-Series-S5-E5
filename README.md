# Predict Calories from Biometric Data

> A regression challenge to predict calories burned using biometric and activity records.  
> Participated as part of Kaggle Playground Series S5E5.

---

## Problem Overview

- **Task:** Predict total calories consumed  
- **Type:** Supervised regression  
- **Metric:** RMSLE (Root Mean Squared Log Error)  
- **Dataset:** 750k training / 250k test samples  

---

## What I Learned

0. **Plan the pipeline before diving into details**  
   Early in the process, I skipped comprehensive data exploration and started directly with feature analysis. Later, I realized that key variables like `gender` heavily influenced numerical columns, requiring me to restart some parts.  
   → From now on, I will always begin by sketching a clear pipeline and outlining how features relate before implementing.

1. **Target transformation using `QuantileTransformer`**  
   I used `QuantileTransformer(output_distribution='normal')` to normalize the target variable.  
   - Helps stabilize variance and meet model assumptions  
   - Apply `fit_transform()` only to train  
   - Use `transform()` for validation/test  
   - Must use `inverse_transform()` after prediction to revert to original scale  

2. **EDA is about making decisions, not just reading charts**  
   I learned to stop passively “observing” data and instead actively design how to handle each feature.  
   - Decide: What should be dropped?  
   - Decide: What should be combined, transformed, or used as-is?

3. **Outliers and skewness aren't always bad**  
   Instead of dropping extreme values, I learned to create indicator variables that inform the model.  
   This preserves useful information and enhances model robustness without hiding complexity.

---

## Experiment Summary

| Model            | Validation Method   | RMSLE (val) | Notes                             |
|------------------|---------------------|-------------|------------------------------------|
| XGBoost baseline | 80/20 split         | 0.0626      | Initial model without tuning       |
| XGBoost (tuned)  | 5-Fold CV           | 0.059       | Improved generalization            |

---

## Key Features

| Feature       | Description                              |
|---------------|------------------------------------------|
| `Intensity`   | Proxy for activity strength (HR + Temp)  |
| `EnergyProxy` | Duration × Intensity                     |

---

## Room for Improvement

- Refine feature selection using SHAP values or model-based importance
- Replace simple holdout with full K-Fold CV
- Experiment with ensembling: Voting or Stacking
- Enhance treatment of outliers and explore better clipping strategies

---

## Notes for Future Me

- Always begin with a clear understanding of data distribution and structure
- Use log-scale or transformation checks early when RMSLE is the metric
- Automate and modularize reusable pipeline steps—optimize for repeatability

---

## Competition Link

[🔗 View on Kaggle](https://www.kaggle.com/competitions/your-competition)
