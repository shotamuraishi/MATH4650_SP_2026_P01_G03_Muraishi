# Probabilistic Deep Learning — MATH 4650

## Linear Regression and Gradient Descent Project

### Project Overview

This project analyzes the relationship between socio-economic indicators and the  **murder rate across U.S. states** .
The dataset contains 50 observations (one per state) and includes predictors such as poverty rate, education level, unemployment, metropolitan population, and family structure.

The main objectives of the project are:

* Perform **exploratory data analysis (EDA)** and data preprocessing.
* Build a **machine learning pipeline** using scikit-learn.
* Implement  **Linear Regression using gradient descent from scratch** .
* Compare model performance using  **R² and RMSE metrics** .
* Evaluate the impact of  **different optimization strategies and hyperparameters** .


# Project Organization

This project follows the  **Cookiecutter Data Science structure** .

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Convenience commands (e.g., `make data`, `make train`)
├── README.md          <- Project documentation
├── data
│   ├── external       <- Data from third-party sources
│   ├── interim        <- Intermediate transformed data
│   ├── processed      <- Final datasets used for modeling
│   └── raw            <- Original dataset
│
├── docs               <- Documentation files
│
├── models             <- Trained models or predictions
│
├── notebooks
│   └── temp.ipynb     <- Main notebook containing analysis and modeling
│
├── pyproject.toml     <- Project configuration
│
├── references         <- Data dictionaries and background material
│
├── reports
│   └── figures        <- Generated visualizations used in reports
│
├── requirements.txt   <- Python dependencies
│
├── setup.cfg          <- Configuration for linting tools
│
└── module             <- Source code
    ├── __init__.py
    ├── config.py
    ├── dataset.py
    ├── features.py
    ├── modeling
    │   ├── predict.py
    │   └── train.py
    └── plots.py
```


# Model Comparison Table

Below are the **test-set metrics (or cross-validation mean)** reported from Sections 2–4.

| Model                                                         | Test R² | Test RMSE |
| ------------------------------------------------------------- | -------- | --------- |
| scikit-learn LinearRegression (50/50 train/test split)        | 0.3021   | 1.8506    |
| scikit-learn LinearRegression (3-fold CV mean)                | -0.7235  | 2.6562    |
| LinearRegressionGD — full-batch, η = 0.01                   | 0.1796   | 2.0065    |
| LinearRegressionGD — mini-batch, η = 0.01                   | 0.2506   | 1.9177    |
| LinearRegressionGD — mini-batch, optimal η (from Section 4) | -0.7072  | 2.8944    |



# Key Findings

* The **scikit-learn LinearRegression baseline** produced the best test performance.
* Gradient descent implementations showed slightly weaker results due to **sensitivity to hyperparameters** such as learning rate.
* **Mini-batch gradient descent performed better than full-batch** , likely due to stochasticity helping generalization.
* The gap between training and test performance suggests  **mild overfitting** , which is expected given the dataset contains only  **50 observations** .

# Future Improvements

Potential next steps include:

* Applying **regularization techniques** such as Ridge or Lasso regression.
* Using more advanced optimizers like  **Momentum or Adam** .
* Expanding the dataset with  **county-level crime data** .
* Testing  **non-linear models or polynomial regression** .

### Shota Muraishi

Completed **Sections 1–3** of the project:

* Data inspection and preprocessing
* Missing value analysis
* Correlation analysis and visualization
* Pair plots and heatmaps
* Outlier detection using box plots
* Initial data preparation and analysis writing

### Patrus Gurung

Completed **Sections 4–5** of the project:

* Implementation of **Linear Regression using Gradient Descent**
* Implementation of **Full-batch Gradient Descent**
* Implementation of **Mini-batch Gradient Descent**
* Learning-rate experimentation and tuning
* Model evaluation and comparison
* Final performance interpretation
