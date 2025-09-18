# Credit & Fraud Risk Analytics System
Project overview

This repository contains an end-to-end implementation of a Credit & Fraud Risk Analytics System designed to showcase data engineering, big-data processing, machine learning, deployment (future events), and reporting for two parallel but related use-cases:

- **Fraud Detection (transaction-level)** — using the Kaggle Credit Card Fraud Detection dataset (PCA-transformed) to detect fraudulent transactions in (near) real-time.

- **Credit Risk Scoring (customer-level)** — using a synthetic/loan dataset to predict loan default probability for applicants.

## Motivation

Financial services require two complementary risk systems: one that protects the business from fraudulent transactions (fast, transaction-level detection) and one that scores credit risk of customers (applicant-level decisions). This project demonstrates both systems, end-to-end, with a focus on scalability, interpretability, and production-readiness.

## Highlights / What you'll learn
- How to process anonymized high-dimensional transactional data (PCA features) and still build performant models.
- How to build credit scoring models from applicant-level features and interpret them for business stakeholders.
- How to use Hive + PySpark for distributed preprocessing and Parquet outputs for performance.
- How to handle class imbalance (SMOTE, scale_pos_weight, anomaly detection).
- How to deploy models as microservices (FastAPI) and simulate streaming (Kafka + Spark Structured Streaming).
- How to present results with Power BI and integrate SHAP explanations into reports.

## Repository structure
/project-root
├─ data/        # raw CSVs (creditcard.csv, loans.csv)
├─ notebooks/
│ ├─ 01_eda_fraud.ipynb
│ ├─ 02_eda_loans.ipynb
│ ├─ 03_modeling_fraud.ipynb
│ └─ 04_modeling_loans.ipynb
├─ spark_jobs/
│ ├─ fraud_preprocess.py
│ └─ loans_preprocess.py
├─ models/
│ ├─ fraud_xgb.pkl
│ └─ loans_xgb.pkl
├─ deploy/
│ ├─ fraud_api.py
│ └─ loans_api.py
├─ dashboards/
│ └─ powerbi_files.pbix
├─ requirements.txt
└─ README.md

## Datasets

- Fraud: creditcard.csv (Kaggle - European card transactions) — columns: Time, V1, V2,..,V28, Amount, Class. The dataset is PCA-anonymized; the only interpretable features are Time and Amount. 

- Loans: loan_data.csv (open dataset) — example columns: person_age, person_gender, person_education, person_income, person_emp_exp, person_home_ownership, loan_amount, loan_intent, loan_int_rate, loan_percent_income, cb_person_cred_hist_length, credit_score, previous_loan_defaults_on_file, loan_status.
