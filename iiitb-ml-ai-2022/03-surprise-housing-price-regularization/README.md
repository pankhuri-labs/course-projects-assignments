# Surprise Housing: House Price Prediction with Ridge and Lasso

**Course:** Executive PG Programme in ML & AI, IIIT Bangalore · **Type:** Individual assignment · **Year:** 2022

## Problem
A US housing company entering the Australian market buys houses below value and resells them. It needs a model that predicts house prices and explains which variables drive them.

## Approach
- Domain-informed null handling across 80 attributes (for example, a missing fireplace or garage value means "none", not unknown).
- Removed near-constant categorical columns, engineered house age, encoded ordinal quality ratings and created dummies (243 features).
- Baseline linear regression with RFE and VIF, then Ridge and Lasso tuned with 5-fold GridSearchCV.
- Compared coefficients across models and re-modelled after removing the top five predictors to test robustness.

## Results
- Optimal regularisation: **Ridge λ = 2, Lasso λ = 0.001**.
- **Test R² ≈ 0.77 to 0.78** (train ≈ 0.79), with a small train/test gap and therefore little overfitting.
- Strongest predictors include overall quality, neighbourhood (Stone Brook, Crawford, NoRidge) and building type (townhouse, negative).

## Tools
Python, pandas, scikit-learn (Ridge, Lasso, RFE, GridSearchCV), statsmodels, Seaborn

## Files
- [`surprise_housing_ridge_lasso.ipynb`](surprise_housing_ridge_lasso.ipynb)

Originally published at [pankhurimishra81/Surprise-Housing-](https://github.com/pankhurimishra81/Surprise-Housing-).
