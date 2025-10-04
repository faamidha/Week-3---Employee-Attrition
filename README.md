# Week-3---Employee-Attrition
Employee Attrition Prediction
Project Overview
This project focuses on predicting employee attrition (turnover) using a provided HR dataset. The goal is to build machine learning models to accurately identify employees who are at a high risk of leaving the company. Early identification allows the Human Resources (HR) team to proactively intervene with retention strategies such as promotions, raises, or improved work-life balance initiatives.

The notebook explores the data, preprocesses features, handles class imbalance using SMOTE, trains several classification models, and evaluates their performance to identify key factors contributing to turnover.

Dataset
The dataset used is WA_Fn-UseC_-HR-Employee-Attrition.csv, which contains fictional, but realistic, employee data with 35 features.

Key characteristics:

Total Records: 1,470

Target Variable (Attrition): Highly imbalanced, with far more 'No' (retention) cases than 'Yes' (attrition) cases.

Feature Types: A mix of numerical (e.g., Age, MonthlyIncome) and categorical (e.g., JobRole, MaritalStatus) variables.

Project Structure and Workflow
Load the Dataset: Load the WA_Fn-UseC_-HR-Employee-Attrition.csv file into a Pandas DataFrame.

Exploratory Data Analysis (EDA):

Check the shape, data types, and non-null counts (df.shape, df.info()).

Examine the distribution of the target variable (Attrition) and key categorical features (JobRole, OverTime).

Visualize the relationship between key features and attrition (e.g., MonthlyIncome vs. Attrition boxplot and Attrition by Job Role countplot).

Data Preprocessing:

Encoding: The target variable Attrition is label encoded (Yes=1, No=0), and all other categorical features are One-Hot Encoded using pd.get_dummies().

Scaling: Numerical features are scaled using StandardScaler to normalize their range.

Handling Class Imbalance:

The Synthetic Minority Over-sampling Technique (SMOTE) is applied to the training data to balance the classes and improve the model's ability to predict the minority class (attrition).

Model Building & Training:

Three different classification models were initialized and trained on the SMOTE-resampled training data:

Logistic Regression (log_model)

Random Forest Classifier (rf_model)

XGBoost Classifier (xgb_model)

Model Evaluation:

Model performance is evaluated on the separate test set using standard classification metrics, with a focus on Precision, Recall, and F1-score, which are critical for an imbalanced classification problem like attrition prediction.

Results and Model Performance
The table below summarizes the performance metrics (specifically for the positive class, '1' - Attrition) on the test set:

Model	Accuracy	Precision	Recall	F1-Score
Logistic Regression	0.61	0.60	0.61	0.61
Random Forest	0.91	0.95	0.87	0.91
XGBoost	0.92	0.95	0.89	0.92

Key Findings
The Logistic Regression model performed poorly, suggesting a linear model is not sufficient for this problem.

Tree-based ensemble models (Random Forest and XGBoost) demonstrated significantly better performance, with XGBoost achieving the highest overall accuracy and F1-Score.

The high Recall scores (Random Forest: 0.87, XGBoost: 0.89) are particularly valuable, as they indicate the models are effective at correctly identifying employees who will leave.

Most Important Features
Feature Importance analysis (using the XGBoost model's results) reveals the strongest predictors of employee attrition:

OverTime (Yes/No)

MonthlyIncome

JobRole (Specific roles like Sales Executive and Laboratory Technician had high counts, as seen in the EDA)

TotalWorkingYears

YearsAtCompany

EnvironmentSatisfaction

Conclusion and HR Suggestions
The machine learning models developed in this project, particularly the XGBoost Classifier, provide a highly effective tool for predicting employee attrition.

Recommendations for the HR Team:

Targeted Intervention: Use the XGBoost model to regularly screen employees and identify those with a high probability of attrition.

Overtime Review: The OverTime feature is a top predictor; evaluate overtime policies and workload management, as excessive overtime is a strong indicator of an employee's intent to leave.

Compensation and Career Path: MonthlyIncome and JobRole are significant. Conduct market-rate salary reviews and ensure clear career progression paths, especially for employees in high-attrition roles.

Work Environment: The importance of EnvironmentSatisfaction suggests a need to improve the workplace, which could involve improving facilities, team dynamics, or resource availability.

Technologies Used
Python

Pandas (Data Manipulation)

NumPy (Numerical Operations)

Matplotlib / Seaborn (Data Visualization)

Scikit-learn (Preprocessing, Model Building, Evaluation)

Imbalanced-learn (imblearn) (SMOTE for Class Imbalance)

XGBoost (Advanced Model)
