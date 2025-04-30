# Data-science-projects
**Customer Churn Prediction:**
## Problem Statement
Our goal is to predict customer turnover (also known as customer attrition) for a company. High turnover rates compromise revenue and sustainability. Identifying customers likely to leave enables proactive retention strategies, safeguarding income.
## Data Collection
The data consists of various customer attributes, including:
- Credit Score
- Age
- Gender
- Tenure (how long they've been with the company)
- Balance (amount in their account)
- Estimated Salary
- A binary indicator of churn labeled "Exited" (1 for churned, 0 for not churned)
## Machine Learning Task
This project presents a binary classification problem using supervised learning. The model classifies customers into two groups based on the "Exited" target variable to predict whether they will stay with the company or leave.
## Dataset Source
[Dataset Link](https://www.kaggle.com/datasets/willianoliveiragibin/customer-churn)
## Data Loading and Exploration
```python import pandas as pd

df = pd.read_csv('/path/to/your/dataset.csv')
print(df.head())
## Key Steps
- **Data Quality Assessment**: Checking for missing values, outliers, and categorical data inconsistencies.
- **Exploratory Data Analysis**: Visualizing distribution and churn rates.
- **Data Preprocessing**: Cleaning data, feature engineering, and splitting the dataset into training and validation sets.
- **Model Training**: Using models like Random Forest, Logistic Regression, and Gradient Boosting.
## Model Evaluation
Metrics used for assessment include:
- Accuracy
- ROC AUC Score
- Confusion Matrix
- Classification Report
## Final Discussion
The final model will offer insights into customer behavior and help in implementing action strategies to reduce churn.
## Conclusion
The customer churn predictive model provides an actionable framework for businesses to enhance customer retention strategies. 
