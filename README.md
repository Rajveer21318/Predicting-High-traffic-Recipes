# Recipe Population Prediction
An end-to-end data science project that analyses recipe and website traffic data to predict whether a recipe will generate high traffic when featured on the homepage.
Business Problem

## Business Problem
Tasty Bytes wanted to identify recipes that are likely to drive high traffic and increase subscriptions while minimising the risk of promoting unpopular recipes.

## Dataset

The dataset contains recipe information, including:

- Nutritional information (calories, carbohydrates, sugar, protein)
- Recipe category
- Number of servings
- Whether the recipe generated high traffic

## Project Workflow

### Data validation and cleaning
- Handled missing values and outliers
- Corrected inconsistent categories and serving values
- Prepared features for modelling

### Exploratory Data Analysis
- Analysed feature distributions and traffic patterns
- Investigated relationships between nutritional variables
- Performed statistical hypothesis testing

### Machine Learning
- Baseline model: Logistic Regression
- Comparison model: Random Forest Classifier
- Hyperparameter tuning using RandomizedSearchCV

### Model Evaluation
- Accuracy: 80.42%
- Logistic Regression ROC-AUC: 0.8815
- Random Forest ROC-AUC: 0.8770
- Logistic Regression Precision: 82.22%
- Random Forest Precision: 80.85%

## Key Findings
- Recipe category was the strongest predictor of website traffic.
- Calories and protein showed statistically significant differences between high- and low-traffic recipes.
- Logistic Regression slightly outperformed Random Forest while being simpler and more interpretable.

## Recommendation

Deploy the Logistic Regression model for homepage recipe selection. The model correctly identifies high-traffic recipes with approximately 82% precision and provides a lightweight, interpretable solution for supporting business decisions.

## Technologies Used
- Python
- Pandas & NumPy – data cleaning, manipulation, and numerical analysis
- Matplotlib & Seaborn – data visualisation
- SciPy & Pingouin – statistical analysis and hypothesis testing
- Scikit-learn – data preprocessing, imputation, model development, hyperparameter tuning, and evaluation
