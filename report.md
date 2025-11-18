# Credit Risk Prediction — Full Project Report

## 1. Introduction
Credit risk prediction is essential for financial institutions to assess whether a loan applicant is likely to default.  
This project builds an interpretable machine learning model to predict credit risk using a structured dataset.

The main goals:
- Build a reliable classifier  
- Interpret predictions using SHAP + LIME  
- Provide clear evaluation metrics  
- Create case studies for model explanations  

---

## 2. Dataset Overview
The dataset contains information on:
- Applicant demographics  
- Income and employment  
- Loan amount and intention  
- Credit history  
- Target variable: **loan_status** (1 = Default, 0 = Non-default)

The dataset is cleaned and preprocessed to handle:
- Missing values  
- Categorical encoding  
- Feature engineering  

---

## 3. Preprocessing Steps

### 3.1 Handling Missing Values
- Numerical columns: Filled with median  
- Categorical columns: Encoded using LabelEncoder  

### 3.2 Feature Engineering
Two interaction features were added:
1. **income_to_loan_ratio**  
   Formula: `person_income / loan_amount`

2. **credit_age_interaction**  
   Formula: `person_age * credit_history_length`

These help the model understand combined effects of income, age, and credit history.

---

## 4. Model Selection — XGBoost

XGBoost is chosen due to:
- Excellent performance on tabular data  
- Handles non-linear patterns  
- Works well with missing values  
- Provides feature importance  

Hyperparameters used:
n_estimators = 400
learning_rate = 0.05
max_depth = 5
subsample = 0.8
colsample_bytree = 0.8
eval_metric = "logloss"

yaml
Copy code

---

## 5. Model Evaluation

### 5.1 Metrics Used
- ROC-AUC  
- Confusion Matrix  
- Classification Report  
- Probability Distribution  

### 5.2 Findings
- The model shows strong performance in distinguishing defaulters vs non-defaulters.
- Both precision and recall are balanced.
- ROC curve shows high true positive rate.

All plots are saved under:
/plots

yaml
Copy code

---

## 6. Model Interpretability

### 6.1 SHAP — Global Explanation
SHAP shows how each feature impacts the model:
- High income reduces credit risk  
- High loan amounts increase risk  
- Longer credit history reduces risk  
- Certain loan intents (e.g., small_business) increase risk  

### 6.2 SHAP — Local Explanation
Three case studies:
- **High-risk** → Strong effects from low income, high loan, poor credit history  
- **Low-risk** → Stable income, low loan amount, long credit history  
- **Borderline** → Mixed features near classifier threshold  

Force plots for each case are saved as PNG.

### 6.3 LIME — Local Explanation
Provides clear feature-level contributions for each case study.  
Helps understand why the model predicts “Risky” or “Safe”.

---

## 7. Case Studies (3 Applicants)

### 7.1 High-Risk Applicant
- High loan amount  
- Low income  
- Short credit history  
Model strongly predicts default.

### 7.2 Low-Risk Applicant
- Stable job  
- Good credit  
- Small loan  
Model predicts safe borrower.

### 7.3 Borderline Applicant
- Probability near 0.5  
- Mixed signals: moderate income & medium loan  
Useful for explaining uncertainty.

---

## 8. Files Included

notebook.ipynb
credit_risk_dataset.csv
plots/
requirements.txt
model_parameters.txt
README.md
report.md

yaml
Copy code

---

## 9. Conclusion

The model demonstrates:
- High predictive power  
- Strong interpretability through SHAP & LIME  
- A complete, end-to-end credit-risk solution  

This project is ready for:
- GitHub submission  
- Machine learning tests  
- Interview tasks  
- Portfolio showcasing  
