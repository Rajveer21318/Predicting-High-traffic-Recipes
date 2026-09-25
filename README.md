# Predicting High-Traffic Recipes

An end-to-end data science project analysing recipe and website traffic data to identify recipes likely to generate high traffic when featured on the homepage. The project combines statistical analysis, machine learning and Power BI to translate data into a business-focused recommendation for recipe selection.

## Business Problem

Tasty Bytes wanted to identify recipes that were more likely to generate high website traffic when promoted on the homepage.

The business challenge was to improve the selection of recipes for promotion while reducing the likelihood of selecting recipes that would underperform.

The analysis therefore focused on two questions:

- Which recipe characteristics are associated with high website traffic?
- Can a machine learning model improve the reliability of identifying high-traffic recipes?

## Business Objective

The existing recipe dataset had a **60.1% high-traffic rate**.

The objective was to develop a classification model that could identify high-traffic recipes more reliably and translate its performance into a business-relevant metric.

**Primary business metric: Precision**

Precision was selected because it measures how often recipes predicted to be high traffic were actually high traffic. This is relevant when the model is used to support homepage or content-selection decisions.

## Dataset

The dataset contains information on 714 recipes, including:

- Nutritional information: calories, carbohydrates, sugar and protein
- Recipe category
- Number of servings
- Whether the recipe generated high traffic

## Project Workflow

### 1. Data Validation & Cleaning

Validated each feature before modelling:

- Checked numerical variables for missing values and outliers
- Removed extreme numerical outliers using the IQR rule
- Imputed remaining numerical missing values using the median
- Standardised inconsistent recipe categories
- Cleaned and converted serving values into an ordinal feature
- Converted the target variable into a binary classification variable
- Confirmed that no duplicate rows were present

### 2. Exploratory Data Analysis

Used Python and statistical testing to understand the factors associated with high website traffic.

Analysis included:

- Distribution analysis of nutritional variables
- High-traffic rates across recipe categories
- Correlation analysis between nutritional features
- Mann–Whitney U tests for continuous variables
- Chi-square tests for categorical variables

Key findings included:

- Recipe category was significantly associated with high traffic
- Calories and protein showed statistically significant differences between high- and low-traffic recipes
- Nutritional variables showed relatively weak correlations with one another

### 3. Machine Learning

This was treated as a **binary classification problem**.

Two models were developed:

**Baseline — Logistic Regression**

- Standardised numerical features
- One-hot encoded recipe categories
- Provided an interpretable baseline

**Comparison — Random Forest**

- Used the same underlying features
- Did not require feature scaling
- Hyperparameters were tuned using RandomizedSearchCV with 5-fold cross-validation

### 4. Model Evaluation

Both models achieved **80.42% accuracy** on the holdout test set.

| Model | Accuracy | Precision | ROC-AUC |
|---|---:|---:|---:|
| Logistic Regression | 80.42% | **82.22%** | **0.8815** |
| Random Forest | 80.42% | 80.85% | 0.8770 |

Logistic Regression achieved higher precision and ROC-AUC while providing a simpler and more interpretable model.

## Business Impact

The model results were translated into a business-focused performance measure rather than relying solely on technical model metrics.

The existing recipe mix had a **60.1% high-traffic rate**, compared with **82.22% precision** for Logistic Regression on the holdout test set.

This represents a **22.12 percentage-point improvement** in the proportion of selected recipes that were actually high traffic within the evaluation framework.

In practical terms, if the model were used as a screening tool for homepage recipe selection, the test-set results indicate that approximately **82 out of every 100 recipes predicted as high traffic were actually high traffic**, compared with approximately 60 out of every 100 under the existing recipe mix.

> This represents an evaluation result rather than a measured increase in website traffic, as the model was not deployed into production.

## Business Recommendations

### 1. Use Logistic Regression as the initial screening model

Logistic Regression achieved the highest precision and ROC-AUC of the two models while remaining relatively simple and interpretable.

### 2. Use model predictions to support homepage selection

The model could be used as a screening tool to help prioritise recipes with a higher predicted probability of generating high traffic.

### 3. Incorporate recipe category into content planning

Recipe category showed a significant relationship with high traffic, with some categories displaying substantially higher observed high-traffic rates.

These findings could be used alongside the model to inform future recipe planning and homepage selection.

### 4. Validate the business impact before full deployment

The next step would be to test the model on newly published recipes and monitor whether model-supported selections actually improve website engagement.

An A/B test could also be used to compare model-selected recipes with the existing selection process.

## Power BI Dashboard

A Power BI dashboard was developed to communicate the analysis and model results to a non-technical audience.

The dashboard presents:

- Overall high-traffic rate
- High-traffic rate by recipe category
- Model accuracy
- Model precision
- Model ROC-AUC

The dashboard provides a visual link between the underlying analysis and the business decision, allowing stakeholders to compare recipe categories and understand the performance of the predictive models.

[![Power BI Dashboard Preview](Images/High%20Traffic%20PowerBI%20SS.png)](https://app.powerbi.com/view?r=eyJrIjoiMmQ1ZjIxNmItYzY1YS00MmU3LWEzZGUtMjExNmEyNWQyYWQwIiwidCI6IjFlMjUwZmE5LTQ5MTctNGNmYi1hMWRkLWE2YWE0YzRiNjJmNyJ9)

## Key Takeaways

- **60.1%** of recipes in the dataset were classified as high traffic
- Logistic Regression achieved **82.22% precision**
- Logistic Regression achieved **0.8815 ROC-AUC**
- Model precision was **22.12 percentage points above the existing high-traffic rate**
- Recipe category was significantly associated with high traffic
- Power BI was used to communicate the findings and model performance in a business-focused format

## Technologies Used

- **Python** – data analysis and machine learning
- **Pandas & NumPy** – data cleaning and manipulation
- **Matplotlib & Seaborn** – exploratory data visualisation
- **SciPy & Pingouin** – statistical testing
- **Scikit-learn** – preprocessing, modelling, hyperparameter tuning and evaluation
- **Power BI** – business-focused data visualisation and communication
- **Git/GitHub** – version control and project documentation
