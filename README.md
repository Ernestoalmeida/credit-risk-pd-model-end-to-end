# credit-risk-pd-model-end-to-end
12-month Probability of Default (PD) model with AUC/KS evaluation, calibration analysis, and approval vs expected loss simulation.

---

## README 2 — PD (Credit Risk)  
Repo sugerido: `credit-risk-pd-model-end-to-end`

```markdown
# Credit Risk PD Model — End-to-End Implementation

## 📌 Overview
This project builds an end-to-end **Probability of Default (PD) model** to predict 12-month default risk at loan origination.

It combines statistical rigor (AUC/KS/calibration) with business decisioning (cutoffs, approval rate, expected loss) to demonstrate production-ready credit modeling.

This repository demonstrates:
- Data preprocessing & feature engineering
- Model development (Logistic Regression & XGBoost)
- Evaluation (AUC, KS, calibration)
- Cutoff optimization and portfolio trade-offs
- Interpretability (coefficients / SHAP)

---

## 🧠 Business Context
Credit decisioning must balance:
- 📈 Approval rate
- 💰 Expected loss
- ⚖️ Risk appetite and stability over time

A PD model quantifies risk and supports data-driven lending strategy.

---

## 📊 Dataset
Borrower-level dataset including:
- Income, DTI, loan amount, utilization
- Credit history indicators / delinquency flags
- Target: `default_12m` (1 = default within 12 months)

> If using a public dataset, add the source link here.

---

## ⚙️ Methodology

### 1️⃣ EDA
- Missing values and outliers
- Target prevalence
- Segment risk analysis
- Correlation and leakage checks

### 2️⃣ Feature Engineering
- Ratio and log transforms
- Risk banding (when applicable)
- Encoding for categorical variables
- Outlier treatment and imputation strategies

### 3️⃣ Modeling
Models implemented:
- Logistic Regression (baseline, interpretable)
- XGBoost (non-linear, higher lift)

Splitting strategy:
- Stratified split and/or **out-of-time validation** if dates exist.

---

## 📈 Model Performance
| Model               | AUC  | KS   | Brier Score |
|---------------------|------|------|------------|
| Logistic Regression | 0.xx | 0.xx | 0.xx       |
| XGBoost             | 0.xx | 0.xx | 0.xx       |

*(Replace with actual results.)*

---

## 🎯 Cutoff Optimization & Business Simulation
We simulate portfolio outcomes across thresholds:

| Cutoff | Approval Rate | Avg PD | Expected Loss |
|--------|---------------|--------|---------------|
| 0.30   | xx%           | 0.xx   | Medium        |
| 0.35   | xx%           | 0.xx   | Lower         |
| 0.40   | xx%           | 0.xx   | Conservative  |

This supports selecting a cutoff aligned with risk appetite and volume objectives.

---

## 📉 Evaluation Metrics
- ROC-AUC
- KS Statistic
- Confusion Matrix by cutoff
- Precision/Recall at decision thresholds
- Calibration curve (reliability)
- Feature importance / SHAP (XGBoost)
- Coefficients (logistic)

---

## 🗂 Project Structure
```text
credit-risk-pd-model-end-to-end/
│
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_model_training.ipynb
│   └── 04_model_evaluation.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── features.py
│   ├── train.py
│   ├── evaluate.py
│   └── score.py
│
├── models/
│   └── model.pkl
│
├── reports/
│   └── figures/
│
├── requirements.txt
└── README.md
