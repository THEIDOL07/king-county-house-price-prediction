King County House Price Prediction

This project predicts residential house sale prices in King County, USA (including Seattle) from property features such as square footage, bedrooms, bathrooms, floors, waterfront view, and construction grade. The dataset covers homes sold between May 2014 and May 2015. It is framed as a real-estate investment problem, where the goal is to estimate a house’s market price from its attributes.

What I did

Data wrangling: dropped irrelevant columns (id, index column) and filled missing values in bedrooms and bathrooms with the column mean.
Exploratory analysis: counted houses by number of floors, compared price outliers for waterfront vs. non-waterfront homes with boxplots, and checked how sqft_above relates to price with a regression plot. I also ranked features by correlation with price.
Model development: built a simple linear regression on sqft_living, then a multiple linear regression on 11 features, then a pipeline of StandardScaler → PolynomialFeatures → LinearRegression.
Model evaluation: split the data 85/15 into training and test sets, then trained a Ridge regression (alpha = 0.1), and a second-order polynomial Ridge regression, scoring both on the held-out test set.

Key results

sqft_living alone: R² = 0.4929
Multiple linear regression (11 features): R² = 0.6577
Polynomial pipeline (scale → polynomial → linear): R² = 0.7512
Ridge regression (test set): R² = 0.6479
Polynomial Ridge (test set): R² = 0.7003

Tools: Python, pandas, NumPy, Matplotlib, seaborn, scikit-learn, Jupyter Notebook

Dataset: House Sales in King County, USA (Kaggle)
