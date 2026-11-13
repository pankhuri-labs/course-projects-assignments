# Telecom Churn Prediction

**Course:** Executive PG Programme in ML & AI, IIIT Bangalore · **Type:** Case study · **Year:** 2022

## Problem
In a prepaid telecom market with 15 to 25% annual churn, the operator wants to predict which high-value customers are likely to churn and understand why, so it can retain them.

## Approach
- Filtered to high-value customers and derived the churn label from usage in the churn month.
- Investigated missing values (for example, a missing recharge date means no recharge) and imputed or dropped them accordingly.
- Feature derivation across good-phase vs action-phase months, scaling, and class-imbalance treatment with SMOTE.
- PCA for dimensionality reduction, then Logistic Regression and Random Forest tuned with GridSearchCV, selected on F1.
- A separate interpretable logistic regression (RFE + VIF) to identify churn drivers.

## Results
| Model | Accuracy | Precision | Recall | F1 |
|---|---|---|---|---|
| Logistic Regression (PCA, 30 components) | 0.79 | 0.78 | 0.80 | 0.79 |
| **Random Forest (max_depth 17)** | **0.92** | **0.94** | **0.91** | **0.92** |

- Random Forest was chosen: it raised test F1 from about 0.80 to 0.92 using half as many principal components.
- Average revenue per user (ARPU) and changes in recharge and usage between months were the strongest churn signals. This led to recommendations on recharge denominations and combined data-and-voice plans.

## Tools
Python, pandas, scikit-learn, imbalanced-learn (SMOTE), XGBoost, statsmodels, Seaborn

## Files
- [`telecom_churn.ipynb`](telecom_churn.ipynb)

Originally published at [pankhurimishra81/TelecomChun_Assignment](https://github.com/pankhurimishra81/TelecomChun_Assignment).
