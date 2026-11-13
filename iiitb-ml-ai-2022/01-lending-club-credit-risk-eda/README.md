# Lending Club: Credit Risk Exploratory Data Analysis

**Course:** Executive PG Programme in ML & AI, IIIT Bangalore · **Type:** Group case study · **Year:** 2021

## Problem
A consumer lending company wants to understand which applicant and loan attributes drive loan default ("Charged Off"), so it can reduce credit loss when approving loans.

## Approach
- Grouped ~110 raw attributes into applicant details, credit history and loan details, then kept only those relevant to default.
- Dropped joint-application and single-value columns, profiled missing values and removed income and loan-amount outliers.
- Univariate analysis of loan amount, income, interest rate and loan volume over time.
- Segmented and bivariate analysis of each attribute against `loan_status` (Fully Paid vs Charged Off), plus a correlation study.

## Key findings
- Typical loans are 5,000 to 15,000; typical applicant income is 41,000 to 83,000; typical interest rate is 8% to 14%.
- Applicants living in rented property make up most charged-off loans.
- Higher income correlates with lower interest rates; debt-to-income is negatively correlated with the other risk attributes.
- "Verified" income status unexpectedly appears among defaulters, a signal flagged for further review of the verification process.

## Tools
Python, pandas, NumPy, Matplotlib, Seaborn

## Files
- [`lending_club_eda.ipynb`](lending_club_eda.ipynb): full analysis
- [`Data_Dictionary.xlsx`](Data_Dictionary.xlsx): attribute definitions

Originally published at [pankhurimishra81/Lending-Club-Case-Study](https://github.com/pankhurimishra81/Lending-Club-Case-Study).
