# Customer Default Prediction

## Overview

This project predicts whether a credit card customer will default on their payment in the next month using machine learning techniques.

The objective is to help financial institutions identify high-risk customers early, enabling better credit risk management and reducing potential financial losses.

## Problem Statement

Credit card defaults can lead to significant losses for banks and financial institutions. By analyzing customer demographics, credit limits, billing information, payment history, and repayment behavior, we aim to build a predictive model that estimates the probability of customer default.

This is a **binary classification problem** where:

* **0** → No Default
* **1** → Default

## Dataset

**Dataset:** Default of Credit Card Clients Dataset

* Number of records: 30,000
* Number of features: 25 original features
* Target variable: `default.payment.next.month`

### Feature Categories

* **Demographic Information:** SEX, EDUCATION, MARRIAGE, AGE
* **Financial Information:** LIMIT_BAL
* **Repayment History:** PAY_0 to PAY_6
* **Bill Statements:** BILL_AMT1 to BILL_AMT6
* **Previous Payments:** PAY_AMT1 to PAY_AMT6

## Project Workflow

1. Data Loading and Understanding
2. Exploratory Data Analysis (EDA)
3. Data Cleaning
4. Feature Engineering
5. Data Preprocessing
6. Model Building
7. Model Evaluation
8. Feature Importance Analysis
9. Business Insights

## Data Preprocessing

* Removed the `ID` column
* Handled undocumented categories in `EDUCATION` and `MARRIAGE`
* Created new features:

  * `TOTAL_PAYMENT`
  * `TOTAL_BILL`
  * `PAYMENT_RATIO`
* Applied train-test split with stratification
* Standardized features for Logistic Regression

## Models Evaluated

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier
* Gradient Boosting Classifier

## Results

| Model               | Accuracy   | Precision  | Recall     | F1 Score   | ROC-AUC   |
| ------------------- | ---------- | ---------- | ---------- | ---------- | --------- |
| Logistic Regression | 80.85%     | 69.18%     | 24.19%     | 35.85%     | 0.708     |
| Decision Tree       | 72.40%     | 38.37%     | 40.92%     | 39.61%     | 0.611     |
| Random Forest       | 81.37%     | 64.10%     | 35.80%     | 45.94%     | 0.758     |
| Gradient Boosting   | **81.87%** | **66.62%** | **36.10%** | **46.82%** | **0.781** |

### Best Model

**Gradient Boosting** achieved the best overall performance with:

* Accuracy: 81.87%
* F1 Score: 46.82%
* ROC-AUC: 0.781

## Key Insights

* Recent repayment history (`PAY_0`) was the strongest predictor of default risk.
* Customers with repeated payment delays were significantly more likely to default.
* Financial behavior was more predictive than demographic characteristics.
* Engineered features such as `PAYMENT_RATIO` improved model performance.

## Future Improvements

* Handle class imbalance using SMOTE or class weights
* Optimize classification threshold to improve recall
* Experiment with advanced boosting algorithms such as XGBoost and CatBoost
* Deploy the model using Streamlit or FastAPI

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab

## Repository Structure

```text
Customer_Default_Prediction/
│
├── Customer_Default_Prediction.ipynb
├── README.md
├── requirements.txt
├── images/
└── data/
```

## Author

Akshat Singh Amera
