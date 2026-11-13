# BoomBikes: Bike-Sharing Demand Prediction

**Course:** Executive PG Programme in ML & AI, IIIT Bangalore · **Type:** Individual assignment · **Year:** 2022

## Problem
A US bike-sharing provider wants to know which factors drive daily rental demand, so it can plan for recovery after the pandemic.

## Approach
- Data quality checks, including fixing inconsistent season and weekday encoding and imputing a zero humidity value.
- EDA and correlation analysis of weather, calendar and seasonal variables against total rentals (`cnt`).
- Dummy encoding, train/test split and Min-Max scaling.
- Multiple linear regression using a mixed approach: RFE for coarse selection, then manual elimination by p-value and VIF.
- Residual analysis to validate normality, homoscedasticity and independence of errors.

## Results
- Final model: **adjusted R² 0.834 on training data** and **R² ≈ 0.82 on test data**, with all p-values below 0.05 and VIFs below 5.
- Top demand drivers: temperature (positive, coefficient 0.40), year (positive, 0.24), light rain or snow (negative, 0.30) and wind speed (negative, 0.16).

## Tools
Python, pandas, scikit-learn, statsmodels, Matplotlib, Seaborn

## Files
- [`bike_sharing_regression.ipynb`](bike_sharing_regression.ipynb)

Originally published at [pankhurimishra81/Bike-Sharing-](https://github.com/pankhurimishra81/Bike-Sharing-).
