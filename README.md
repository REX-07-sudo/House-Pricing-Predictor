# House Price Prediction Model

Welcome to the House Price Prediction repository! This project was developed as part of the Week 1 Internship Assignment (Assigned: 17/05/2026 | Submitted: 21/05/2026). 

The goal of this project is to build and evaluate machine learning regression models to predict real estate property values based on structural and logistical features, moving away from subjective guesswork to data-driven valuations.

---

## Problem Statement
Real estate buyers and sellers often rely on outdated comparisons to estimate property values. This project aims to:
1. Clean and prepare a real-world housing dataset.
2. Train a baseline Linear Regression model and an ensemble Random Forest Regressor.
3. Evaluate model accuracy using metrics like MAE, RMSE, and R² Score.
4. Uncover the property features that exert the strongest statistical influence on market price.

---

## Dataset Overview
The project utilizes the Housing Prices Dataset from Kaggle. 
* **Target Variable:** price (Continuous numerical value)
* **Features Included:** area, bedrooms, bathrooms, stories, mainroad, guestroom, basement, hotwaterheating, airconditioning, parking, prefarea, and furnishingstatus.

---

## Tools & Libraries Used
* **Language:** Python 3.x
* **Environment:** Jupyter Notebook (.ipynb)
* **Data Manipulation:** pandas, numpy
* **Machine Learning:** scikit-learn
* **Data Visualization:** matplotlib, seaborn

---

## Methodology & Tasks

### Task 1: Data Loading & Exploration
* Imported the raw Housing.csv into a Pandas DataFrame.
* Profiled the dataset dimensions, data types, and executed missing value checks (0 null values detected).

### Task 2: Data Cleaning & Preprocessing
* Removed structural duplicates to prevent model overfitting.
* Applied One-Hot Encoding with drop_first=True to convert categorical variables (such as furnishingstatus, airconditioning, basement) into numerical format while safely bypassing the multi-collinearity ("dummy variable trap").

### Task 3: Model Architecture & Evaluation
The dataset was partitioned into an 80% training / 20% testing split. Two separate algorithms were trained and pitted against each other:
1. **Linear Regression:** Fits an unyielding, flat hyperplane across all coordinates.
2. **Random Forest Regressor:** Geometrically carves the feature space into custom local zones (orthogonal boundaries), capturing complex non-linear nuances.

### Task 4: Visualizations
The code generates and saves three critical diagnostic charts to the charts/ folder:
* **chart1_price_distribution.png**: A histogram with a KDE overlay showing the right-skewed distribution of housing values.
* **chart2_correlation_heatmap.png**: A masked correlation matrix identifying linear strengths between variables.
* **chart3_actual_vs_predicted.png**: A scatter plot measuring model predictions against a perfect-fit diagonal line.

---

## Key Insights & Summary

* **Primary Value Drivers:** Total square footage (area), the number of bathrooms, and the presence of air conditioning emerged as the top statistical drivers of property value. 
* **Model Performance Summary:** The non-linear boundaries of the Random Forest Regressor comfortably outperformed the basic Linear Regression model, accounting for roughly 61% to 65% of the test set's price variance (R² Score).
* **Business Recommendation:** Real estate developers and house flippers should prioritize premium internal climate control upgrades (AC units) and open-concept space optimization over expensive multi-story expansions or basement digouts, as the former yield a substantially higher statistical ROI per dollar spent.

---

## Repository Structure

```text
├── HousePricePrediction_[YourName]/
│   ├── analysis.ipynb          # Full pipeline code with execution outputs
│   ├── Housing.csv             # The raw Kaggle source data
│   ├── summary.pdf             # One-page project executive summary
│   └── charts/                 # Auto-generated visualization outputs
│       ├── chart1_price_distribution.png
│       ├── chart2_correlation_heatmap.png
│       └── chart3_actual_vs_predicted.png
└── README.md                   # Project documentation (This file)
