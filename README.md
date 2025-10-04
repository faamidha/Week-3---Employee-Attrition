# 📉 Employee Attrition Prediction

## 📘 Overview
This project leverages **Machine Learning (ML)** to analyze and predict employee turnover (attrition) using a comprehensive HR dataset. The main goal is to build a **robust classification model** that identifies employees at high risk of leaving the company. This predictive capability allows HR teams to implement proactive retention strategies before voluntary turnover occurs.

The analysis also addresses the challenge of **class imbalance** (more employees stay than leave) using the **SMOTE oversampling technique**, ensuring a fair and effective model.

---

## 📂 Dataset and Features
**Source:** Fictional HR Dataset (`WA_Fn-UseC_-HR-Employee-Attrition.csv`)  

**Target Variable:** `Attrition` (Yes/No)  

**Key Features:**
- `MonthlyIncome`
- `JobRole`
- `OverTime`
- `YearsAtCompany`
- `EnvironmentSatisfaction`

---

## 🔍 Key Project Steps

1. **Exploratory Data Analysis (EDA)**  
   Visualized attrition rates across different demographic and employment groups.

2. **Preprocessing**  
   - Encoding categorical variables  
   - Scaling numerical features using `StandardScaler`

3. **Imbalance Handling**  
   Applied **SMOTE** to balance the target class distribution.

4. **Modeling**  
   Trained and evaluated the following classifiers:
   - Logistic Regression
   - Random Forest
   - XGBoost

5. **Interpretation**  
   Determined the most impactful features contributing to attrition risk.

---

## 💻 Technologies Used

| Category       | Tools & Libraries                    |
|----------------|-------------------------------------|
| Language       | Python                              |
| Data Handling  | Pandas, NumPy                        |
| Visualization  | Seaborn, Matplotlib                  |
| ML Libraries   | Scikit-learn, imblearn (SMOTE), XGBoost |

---

# ✅ Conclusion and Recommendations
Model Performance

The XGBoost Classifier was the top-performing model, achieving:

Accuracy: 92%

Recall (Attrition Class): 89%

High recall is critical as it minimizes the risk of missing employees who are about to leave.

## Actionable Recommendations for HR

Address Overtime:
The OverTime feature is the strongest predictor. Implement stricter controls or offer compensatory benefits for employees consistently working overtime.

Review Compensation:
MonthlyIncome is a key factor. Conduct targeted salary reviews in high-attrition roles.

Enhance Workplace Experience:
The importance of EnvironmentSatisfaction suggests investing in office facilities, team-building activities, or conflict resolution programs.
# 📁 Files Included

Week_3_Employee_Attrition_.ipynb – Main notebook with all code, analysis, and model evaluations.

README.md – Project documentation.
