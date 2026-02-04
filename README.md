# NovaPay Fraud Detection Project

## Fraudulent Transaction Detection for Digital Money Transfer

This project develops and evaluates a machine learning–based fraud detection system for **NovaPay**, a digital-first, cross-border money transfer platform operating across Canada, the UK, and the United States. The solution focuses on **high fraud detection accuracy, zero customer friction, and explainable decision-making** suitable for operational and regulatory stakeholders.

---

## Business Context

NovaPay processes millions of international transactions monthly across multiple currencies. This scale and global reach increase exposure to:

- Account takeover fraud
- High-velocity transaction abuse
- Cross-border money laundering
- Device, IP, and identity-based fraud

The organisation adopts a **risk-based fraud management approach**, prioritising early detection, transparency, and regulatory compliance while maintaining customer trust.

---

## Project Objectives

- Accurately distinguish fraudulent from legitimate transactions
- Minimise false positives to avoid blocking genuine customers
- Handle severe class imbalance in fraud data
- Provide **transaction-level explainability** using SHAP
- Deliver a production-ready fraud detection model

---

## Data Cleaning Summary

### Files
- `03_cleaning.ipynb` – Data cleaning and validation notebook  
- `cleaned_transactions.csv` – Final cleaned dataset  

### Cleaning Rules Applied
- Validated numerical features (negative and invalid values)
- Removed rows with invalid `transaction_id`
- Removed rows with critical missing values
- Filled missing fee values with mean where applicable
- Converted date columns to datetime format
- Retained duplicate transaction amounts as legitimate behaviour

---

## Models Trained and Evaluated

- Logistic Regression  
- Random Forest Classifier  
- XGBoost  
- LightGBM  

Class imbalance was handled using **ensemble methods, class weighting, and threshold optimisation**.

---

## Model Performance Summary

| Model            | Precision | Recall | F1-Score | ROC-AUC |
|------------------|-----------|--------|----------|---------|
| Logistic Reg     | 79%       | 94%    | 86%      | 98%     |
| **Random Forest**| **100%**  | **92%**| **96%**  | **98%** |
| XGBoost          | 95%       | 92%    | 93%      | 97%     |
| LightGBM         | 92%       | 92%    | 92%      | 97%     |

### Best Model
**Random Forest Classifier**
- Zero false positives
- High fraud recall
- Stable and explainable predictions

---

## Explainability with SHAP

SHAP was used for both **global** and **local (transaction-level)** explanations.

### Top Global Fraud Drivers (SHAP)
- Destination currencies (CNY, USD, NGN)
- KYC tier (standard and low)
- Missing or unknown home country
- Source currency (GBP)
- IP and device trust signals
- Channel (mobile vs web)

---

## SHAP Case Study – Random Fraud Sample (#81)

**Transaction Summary**
- Amount (USD): 857.73  
- Account Age: 44 days  
- IP Risk Score: 1.00  
- Device Trust Score: 0.236  
- Transaction Velocity (24h): 6  
- True Label: FRAUD  

**Model Prediction**
- Predicted: **FRAUD**
- Confidence: **99.95%**

### Key Risk Contributors
- High-risk destination currencies (USD, CNY)
- Standard KYC tier
- Unknown home country
- High IP risk score
- Source currency GBP

This confirms strong alignment between **global SHAP patterns and individual fraud decisions**.

---

## Key Business Insights

- Currency corridors are strong fraud indicators
- KYC tiering materially impacts fraud exposure
- Missing geographic data is a high-risk signal
- Mobile channels show higher fraud risk
- Device and IP intelligence are critical controls
- New and partially verified accounts are consistently higher risk

---

## Deliverables Completed

- Data cleaning and validation
- Feature engineering and encoding
- Four ML models trained and evaluated
- Class imbalance handling
- SHAP global and local explainability
- Best-performing model saved for deployment
- Executive stakeholder presentation prepared

---

## Project Outcomes

- Achieved **zero false positives** with strong fraud recall
- Significantly outperformed rule-based approaches
- Delivered transparent, explainable fraud decisions
- Validated using real fraud test samples
- Model is **ready for production deployment**

---

## Status

✅ **Project Complete**  
📊 **Model Validated**  
🚀 **Deployment Ready**

