# Sentiment-Based Product Recommendation System (Capstone)

**Course:** Executive PG Programme in ML & AI, IIIT Bangalore · **Type:** Capstone project, end to end with deployment · **Year:** 2022

## Problem
Ebuss, an e-commerce company, wants to improve product recommendations by combining what similar users bought with what customers actually say in their reviews.

## Approach
1. **Text processing and sentiment model:** cleaned and lemmatised about 30,000 product reviews, vectorised them with TF-IDF, handled class imbalance with SMOTE, and compared Logistic Regression, Naive Bayes, Random Forest and XGBoost (base and tuned).
2. **Recommendation engine:** built user-based and item-based collaborative filtering with adjusted cosine similarity, evaluated with RMSE, and kept the better one (user-based).
3. **Combined system:** take the top 20 products from the recommender, score their reviews with the sentiment model, and return the top 5 products by share of positive sentiment.
4. **Deployment:** a Flask web app (`app.py`, `model.py`, HTML template), served with Gunicorn on Heroku.

## Results
| Model | Accuracy | Sensitivity | Specificity |
|---|---|---|---|
| **Logistic Regression (chosen)** | **0.82** | **0.82** | **0.84** |
| Naive Bayes | 0.88 | 0.91 | 0.63 |
| Random Forest | 0.91 | 0.98 | 0.42 |

Logistic Regression was chosen because it is the most balanced: it is far better at catching negative reviews (specificity) than higher-accuracy models that mostly predict "positive". It is also lightweight to serve.

## Tools
Python, NLTK, spaCy, scikit-learn, imbalanced-learn, XGBoost, pandas, Flask, Gunicorn, Heroku

## Files
- [`sentiment_product_recommendation.ipynb`](sentiment_product_recommendation.ipynb): analysis and modelling
- [`app.py`](app.py), [`model.py`](model.py), [`templates/`](templates/), [`Procfile`](Procfile), [`requirements.txt`](requirements.txt): web app
- Note: the trained model pickles (`pickle/`) and the dataset are not in the repository, so the notebook must be run first to regenerate them. The original Heroku deployment is no longer live because Heroku ended its free tier.

Originally published at [pankhurimishra81/product-recommendation](https://github.com/pankhurimishra81/product-recommendation).
