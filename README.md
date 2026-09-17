# 📱 PhonePe AI-Powered Fraud Detection

An AI/ML-based prototype for detecting fraudulent digital payment transactions, built as an academic project (BBA FinTech & AI).

> **Disclaimer:** This project uses a **synthetic, randomly generated dataset** for educational purposes only. It does not use, reference, or claim access to any real PhonePe transaction data.

## 🔍 Project Overview

Digital payments have become central to everyday financial life. As transaction volumes grow, so does the risk of fraud. This project explores how a machine learning classifier can distinguish genuine transactions from suspicious or fraudulent ones based on behavioral and transaction-level features.

## 🎯 Business Problem

How can a digital payment platform identify potentially fraudulent transactions while still letting genuine customers pay smoothly? The system aims to classify transactions as:

- ✅ Genuine
- ⚠️ Suspicious
- 🚨 Potentially fraudulent

## 🎯 Objectives

- Detect potentially fraudulent transactions
- Explore transaction patterns and engineered features
- Build a machine learning classification model
- Evaluate the model with appropriate metrics
- Demonstrate how AI/ML can support real-time fraud detection

## 🗂️ Dataset

A synthetic dataset of 10,000 transactions is generated with `numpy`, including features such as:

- Transaction amount
- Transactions in the last 24 hours
- Account age (days)
- New device / new recipient / location change flags
- Failed login/payment attempts
- Night-time transaction flag
- Previous fraud reports
- Fraud label (`is_fraud`)

## 🧠 Model

- **Algorithm:** Random Forest Classifier (`scikit-learn`)
- **Split:** 80% train / 20% test (stratified)
- **Class balancing:** `class_weight="balanced"`
- **Metrics:** Accuracy, ROC-AUC, classification report, confusion matrix
- **Explainability:** Feature importance ranking and chart

## 🚦 Risk Scoring

Predicted fraud probability is mapped to a decision:

| Fraud Probability | Decision |
|---|---|
| < 30% | LOW RISK – Approve |
| 30% – 70% | MEDIUM RISK – Verify |
| > 70% | HIGH RISK – Block / Investigate |

A `check_transaction()` helper function lets you test any custom transaction live.

## 🛠️ Tech Stack

- Python 3
- pandas, numpy
- scikit-learn
- matplotlib, seaborn

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/anchitphutela-max/phonepe-ai-fraud-detection/
   cd phonepe_fraud_detection_model
   ```
2. (Optional) Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Launch Jupyter and run the notebook top to bottom:
   ```bash
   jupyter notebook phonepe_fraud_detection_model.ipynb
   ```

## 📁 Repository Structure

```
.
├── phonepe_fraud_detection_model.ipynb   # Main notebook (data, model, evaluation, demo)
├── requirements.txt                      # Python dependencies
├── README.md                             # Project documentation
└── LICENSE                               # License
```

## 📊 Results

The notebook prints accuracy, ROC-AUC, a full classification report, and displays a confusion matrix and feature-importance chart when run.

## ✅ Conclusion

This project demonstrates an end-to-end pipeline — **Data → Preprocessing → ML Model → Prediction → Evaluation → Fraud Detection** — showing how AI/ML can help improve security and reduce fraud in digital payment systems.


