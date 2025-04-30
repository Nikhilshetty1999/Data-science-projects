**1.Customer Churn Prediction:**

## Problem Statement
Customer churn (or attrition) occurs when customers stop interacting with a company. High churn rates can severely impact revenue and business sustainability. Predicting which customers are likely to leave enables companies to implement targeted retention strategies to reduce churn and protect income.
## Data Collection
The dataset includes customer attributes such as credit score, geography, gender, age, tenure with the company, account balance, and estimated salary. The target variable is `Exited`, a binary indicator where 1 means the customer left and 0 means they stayed.
**Dataset Source:**  
[Kaggle: Customer Churn Dataset](https://www.kaggle.com/datasets/willianoliveiragibin/customer-churn)
## Machine Learning Task
This is a **binary classification** problem aiming to predict whether a customer will churn (`Exited=1`) or not (`Exited=0`) based on their attributes.
## 1) Data Loading and Exploration

- Loaded data using Pandas.
- Explored dataset shape, datatypes, and missing values.
- Analyzed churn distribution: ~20% customers churned, ~80% stayed (class imbalance).
- Visualized numerical feature distributions and detected outliers.
- Removed outliers from the `Age` feature to improve data quality.

## 2) Data Preprocessing and Feature Engineering

- Dropped irrelevant columns: `RowNumber`, `CustomerId`, `Surname`.
- Split data into features (`X`) and target (`y`).
- Identified categorical and numerical features.
- Applied One-Hot Encoding for categorical variables.
- Scaled numerical features using `StandardScaler`.

## 3) Train-Test Split

- Split data into training (80%) and validation (20%) sets using stratified sampling to maintain class distribution.


## 4) Model Training and Hyperparameter Tuning

- Built a pipeline combining preprocessing and a `RandomForestClassifier`.
- Performed hyperparameter tuning with `GridSearchCV` over parameters like `n_estimators`, `max_depth`, `min_samples_split`, and `min_samples_leaf`.
- Selected the best model based on ROC AUC score.


## 5) Model Evaluation

- Compared Random Forest against Logistic Regression and Gradient Boosting.
- Metrics used: Accuracy and ROC AUC.
- Random Forest achieved the best performance.
- Generated classification report and confusion matrix for validation set.


## 6) Results Summary

| Model               | Accuracy | ROC AUC |
|---------------------|----------|---------|
| Random Forest       | 0.8600   | 0.7500  |
| Gradient Boosting   | 0.8510   | 0.7380  |
| Logistic Regression | 0.8120   | 0.6750  |

**Confusion Matrix (Random Forest):**

|               | Predicted Not Churned | Predicted Churned |
|---------------|-----------------------|-------------------|
| Actual Not Churned | 1554                  | 39                |
| Actual Churned     | 319                   | 88                |

---

## 7) Final Discussion

- The Random Forest model effectively predicts customer churn despite class imbalance.
- Hyperparameter tuning improved model performance.
- Removing outliers from `Age` enhanced data quality.
- Limitations include lack of temporal data and limited interpretability.
- Future work: incorporate time-series features, use explainability tools (e.g., SHAP), and explore advanced models.

---

## 8) Recommendations

- Use the model to identify high-risk customers and target retention campaigns.
- Regularly retrain the model with new data to adapt to changing customer behavior.
- Implement explainability methods to understand key churn drivers.

