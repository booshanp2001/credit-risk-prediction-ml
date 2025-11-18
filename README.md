# Credit Risk Prediction using XGBoost, SHAP, and LIME

This project predicts the likelihood of a loan applicant defaulting using machine learning techniques.  
The model is built using **XGBoost**, and interpretability is provided using **SHAP** and **LIME**.

The project follows a complete ML workflow including:
- Data cleaning  
- Feature engineering  
- Model training  
- Model evaluation  
- Model interpretability (Global + Local)  
- Case study analysis  
- Exported plots and parameters  

---

## 📂 Project Structure

CreditRiskProject/
├── notebook.ipynb
├── credit_risk_dataset.csv
├── requirements.txt
├── README.md
├── report.md
├── model_parameters.txt
├── plots/
│ ├── roc_curve.png
│ ├── confusion_matrix.png
│ ├── shap_summary.png
│ ├── shap_bar.png
│ ├── lime_high_risk.png
│ ├── lime_low_risk.png
│ ├── lime_borderline.png
│ ├── shap_force_high_risk.png
│ ├── shap_force_low_risk.png
│ ├── shap_force_borderline.png

yaml
Copy code

---

## 🚀 How to Run the Project

### **1. Install dependencies**
pip install -r requirements.txt

yaml
Copy code

### **2. Open the notebook**
Run the `notebook.ipynb` in Google Colab or Jupyter Notebook.

---

## 🧹 Data Preprocessing

- Missing values were filled using numerical medians.
- Categorical values were encoded using `LabelEncoder`.
- Two interaction features were created:
  - `income_to_loan_ratio`
  - `credit_age_interaction`

---

## 🤖 Model Used — XGBoost

Hyperparameters used:

n_estimators = 400
learning_rate = 0.05
max_depth = 5
subsample = 0.8
colsample_bytree = 0.8
eval_metric = "logloss"

yaml
Copy code

These parameters were selected for stability and generalization on credit-risk datasets.

---

## 📊 Model Evaluation

- **ROC-AUC Score:** High (value in notebook)  
- **Confusion Matrix:** Indicates model performance on positive vs negative classes  
- **Classification Report:** Includes precision, recall, F1-score  

All plots are saved in the `/plots` directory.

---

## 🔍 Model Interpretability

### **1. SHAP (Global + Local)**  
- Global feature importance (summary + bar plots)  
- Local SHAP force plots for:
  - High-risk case
  - Low-risk case
  - Borderline case  

### **2. LIME (Local)**  
Explains predictions of:
- High-risk applicant  
- Low-risk applicant  
- Borderline applicant  

---

## 📝 Case Studies Included

Three prediction cases were selected:
- **High-Risk Case** (Model says “High chance of default”)  
- **Low-Risk Case** (Model says “Safe customer”)  
- **Borderline Case** (Probability ≈ 50%)  

Both SHAP and LIME are used to explain each decision.

---

## 📦 Model Parameters Saved

`model_parameters.txt` contains the dump of XGBoost’s hyperparameters for test evaluation.

---

## 🧾 Report

A full project report is included in `report.md`.

---

## ✨ Summary

This project demonstrates:
- End-to-end credit-risk model development  
- Strong evaluation metrics  
- Explainability using SHAP + LIME  
- Clean GitHub-ready structure  

Perfect for data science tests, ML job tasks, or academic submissions.

---

## 👨‍💻 Author

Created as part of a machine learning evaluation task.  
Prepared using **Python, XGBoost, SHAP, LIME, Google Colab, and GitHub**.
