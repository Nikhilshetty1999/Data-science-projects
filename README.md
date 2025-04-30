# Data-science-projects
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

**2. E_commerce_Business_Transaction**
Business Context
Our client is an online business selling a variety of products to international consumers. The goal of this research is to help the client better understand consumer behavior and generate more sales through data-driven decision making.
Dataset
The dataset consists of sales transaction records, including:
	•	`TransactionNo`: Transaction number per transaction
	•	`ProductName`: Name of product sold
	•	`Price`: Price of product
	•	`Quantity`: Quantity of product sold
	•	`CustomerNo`: Unique customer identifier
	•	`Date`: Date of transaction
	•	`Country`: Transaction country
Dataset Source:
Online Shop Business Dataset (Kaggle)
Project Objectives
This project aims to:
	1.	Optimize the client’s sales strategy
	2.	Improve customer retention
	3.	Manage inventory effectively
	4.	Maximize revenues by analyzing product trends and customer buying habits
Tools & Libraries
	•	Pandas, NumPy: Data manipulation and analysis
	•	Matplotlib, Seaborn: Data visualization
	•	Scikit-learn: Machine learning and preprocessing
	•	mlxtend: Association rule mining (Apriori algorithm)
Workflow Overview
1. Data Loading & Exploration
	•	Import and inspect the dataset
	•	Visualize distributions of key variables (price, quantity)
	•	Calculate revenue and analyze correlations
	•	Detect outliers using boxplots
	•	Analyze frequency of top products and countries
2. Data Cleaning
	•	Handle missing values and duplicates
	•	Address negative or zero values in price/quantity
	•	Standardize date and customer fields
3. Data Preprocessing
	•	Feature engineering: revenue, year, month, day, hour
	•	Prepare data for analysis and modeling
4. Data Visualization
	•	Visualize sales trends by year, month, day of week
	•	Analyze revenue distribution and top-selling products
	•	Compare average order value by country
	•	Identify monthly sales trends
5. Advanced Analysis
	•	Regression modeling: Predict revenue from price and quantity
	•	Customer loyalty analysis: Relationship between repeat purchases and total spend
	•	Market basket analysis: Identify product combinations frequently bought together
	•	Seasonal analysis: Discover seasonal sales patterns
	•	Price optimization: Find optimal price points for maximizing profit
	•	Marketing channel analysis: Compare customer acquisition cost (CAC) vs. customer lifetime value (CLV)
	•	Promotion impact: Evaluate effects of promotions on sales
	•	Best time for advertising: Identify peak days, weeks, and months for marketing
	•	Top-selling products: Highlight best-performing product categories
Key Insights
	•	Customer Loyalty: Repeat customers drive higher revenue; loyalty programs are recommended.
	•	Product Bundling: Certain product pairs are frequently bought together-bundle offers can boost sales.
	•	Seasonality: Sales peak in specific months and days-align marketing and inventory accordingly.
	•	Pricing: Optimal price points balance demand and profit; dynamic pricing strategies are valuable.
	•	Marketing Efficiency: Email and referral channels offer high CLV relative to CAC.
	•	Promotions: ‘Buy One Get One Free’ promotions significantly increase sales volume.
Recommendations
	1.	Implement customer loyalty programs to retain high-value customers.
	2.	Bundle top-selling product pairs to encourage cross-selling.
	3.	Optimize pricing strategies based on demand-profit analysis.
	4.	Schedule marketing campaigns during peak sales periods.
	5.	Allocate marketing budget to channels with the best CLV-to-CAC ratio.
Final Thoughts
This project demonstrates how data science and analytics can drive actionable business insights for e-commerce companies. For full code, visualizations, and detailed analysis, please see the notebooks in this repository.
