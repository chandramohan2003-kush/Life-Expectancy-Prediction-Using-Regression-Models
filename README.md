
# Life Expectancy Prediction using Regression Models

## Project Overview

This project aims to predict life expectancy using various health, demographic and socioeconomic indicators from the WHO Life Expectancy Dataset.

The main objective is to understand the factors associated with life expectancy and compare the predictive performance of different statistical and machine learning models.

---

## Dataset

- **Dataset:** WHO Life Expectancy Dataset
- **Total Observations:** 2,938
- **Total Columns:** 22
- **Countries:** 193
- **Time Period:** 2000–2015
- **Target Variable:** Life Expectancy (in years)

The dataset includes various indicators related to:

- Healthcare and immunization
- Mortality and diseases
- Economic development
- Education and lifestyle
- Demographic characteristics

---

## Project Objectives

- Identify important factors associated with life expectancy.
- Perform exploratory data analysis and data preprocessing.
- Build an interpretable statistical regression model.
- Evaluate regression assumptions using statistical diagnostic tests.
- Compare linear and non-linear regression models.
- Identify the best-performing predictive model.

---

## Project Workflow

### 1. Data Cleaning and Preprocessing

- Checked and handled duplicate observations.
- Handled missing values using group-wise mean and median imputation.
- Encoded categorical variables.
- Applied log transformations to selected skewed features.
- Performed feature selection to reduce multicollinearity.
- Standardized numerical predictors for linear and regularized regression models.

### 2. Exploratory Data Analysis (EDA)

- Analyzed the distribution of numerical variables.
- Identified outliers and skewed features.
- Explored relationships between predictors and life expectancy.
- Performed correlation analysis.
- Examined multicollinearity using Variance Inflation Factor (VIF).
- Identified potential non-linear relationships in the data.

### 3. Ordinary Least Squares (OLS) Regression

OLS regression was implemented as a baseline model to understand the relationship between predictors and life expectancy.

The analysis included:

- Regression coefficient estimation
- Statistical significance of predictors
- Overall model significance
- Residual analysis
- R² and Adjusted R²

### 4. Model Diagnostics

The following diagnostic tests were performed to evaluate the regression model:

| Diagnostic Test | Purpose |
|---|---|
| Shapiro-Wilk Test | Residual normality |
| Breusch-Pagan Test | Heteroscedasticity |
| White Test | Heteroscedasticity |
| Variance Inflation Factor | Multicollinearity |

HC3 robust standard errors were used to improve statistical inference in the presence of heteroscedasticity.

### 5. Model Training and Hyperparameter Tuning

The following regression models were implemented and compared:

- Ordinary Least Squares (OLS) Regression
- Ridge Regression (L2 Regularization)
- Lasso Regression (L1 Regularization)
- Random Forest Regression

GridSearchCV with 5-fold cross-validation was used for hyperparameter tuning.

Random Forest was introduced to capture complex non-linear relationships and interactions among predictors.

---

## Model Evaluation

The models were evaluated using the following performance metrics:

- R² Score
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)

### Model Performance Comparison

| Model | Train R² | Test R² | Test RMSE | Test MAE |
|---|---:|---:|---:|---:|
| OLS Regression | 0.7726 | 0.7823 | 4.3397 | 3.3544 |
| Ridge Regression | 0.7726 | 0.7818 | 4.3440 | 3.3590 |
| Lasso Regression | 0.7722 | 0.7825 | 4.3375 | 3.3511 |
| **Random Forest** | **0.9905** | **0.9384** | **2.3089** | **1.6664** |

### Best Performing Model: Random Forest

- **Test R²:** 0.9384
- **Test RMSE:** 2.3089 years
- **Test MAE:** 1.6664 years
- **RMSE Reduction:** Approximately 47% compared to OLS regression.

### Best Hyperparameters

| Hyperparameter | Value |
|---|---|
| n_estimators | 300 |
| max_depth | None |
| max_features | sqrt |
| min_samples_split | 2 |

---
---

## Author

**Chandramohan Kushwah**

M.Sc. Statistics | IIT Kanpur

[GitHub Profile](https://github.com/chandramohan2003-kush)
