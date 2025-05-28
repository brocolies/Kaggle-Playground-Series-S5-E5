# 🏆 Kaggle Playground Series - Season X Episode Y

> **Problem Type:** Regression  
> **Goal:** Predict calories consumption based on biometric and activity data  
> **Evaluation Metric:** RMSLE  
> **Dataset Size:** 750k rows (train), 250k rows (test)

---

## 📁 File Structure

| File                  | Description                     |
|-----------------------|---------------------------------|
| `train.csv`           | Training data                   |
| `test.csv`            | Test data                       |
| `sample_submission.csv` | Sample submission format       |
| `PredictCal2.ipynb`   | Main analysis notebook          |
| `submission.csv`      | Final submission file           |

---

## 💡 Key Learnings

In this project, I gained the following insights:

- Efficient handling of large tabular data (~750k rows) using pandas.
- Importance of exploring feature distribution (e.g., skewness, log transformation).
- RMSLE penalizes underestimation more heavily than RMSE, which influences model strategy.
- Leveraging `XGBoostRegressor` with early stopping and basic hyperparameter tuning.
- Designing preprocessing pipelines that are robust and test-compatible.

> ✍️ Use this section to reflect on what you learned, what worked well, and what could be improved in future projects.

---

## 🔎 Key Feature Engineering

| Feature Name  | Description                                            |
|---------------|--------------------------------------------------------|
| `BMI`         | Body Mass Index calculated from height and weight     |
| `Intensity`   | Activity intensity derived from heart rate and temp   |
| `EnergyProxy` | Estimated energy consumption = Duration × Intensity   |

---

## 📊 Model Details

| Item              | Value                                       |
|-------------------|---------------------------------------------|
| Model Used        | XGBoost                                     |
| Hyperparameters   | `learning_rate=0.05`, `max_depth=6`, `n_estimators=1000` |
| Evaluation Metric | RMSLE                                       |
| Validation Split  | `train_test_split` with 80:20 split         |

---

## ✅ Result Summary

| Stage             | Score    |
|-------------------|----------|
| Local Validation  | 0.0629   |
| Kaggle Public LB  | 0.57409  |

---

## 🚀 To Be Improved

- [ ] Feature selection and removal based on importance
- [ ] Cross-validation for more robust evaluation
- [ ] Try model ensembling (Stacking / Voting)
- [ ] Improve feature scaling and handle outliers more precisely

---

## 📌 Notes

- All code was written and tested in a Jupyter Notebook.
- The final submission is a CSV with `id` and predicted `Calories`.
- Competition link: [https://www.kaggle.com/competitions/your-competition](https://www.kaggle.com/competitions/your-competition)
