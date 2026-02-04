### Fraudulent Transaction Detection for Digital Money Transfer – Executive Summary
### 

NovaPay Fraud Environment Overview

NovaPay is a digital-first, cross-border money transfer platform headquartered in Toronto, operating across the UK, Canada, and the United States. The platform enables users to send, receive, and hold multiple currencies, processing millions of transactions monthly. While this international, real-time model delivers scalability and convenience, it also increases exposure to fraud and financial crime.

Key fraud risks include account takeover, where stolen credentials are used to initiate rapid, cross-border transfers, and money laundering, where criminals exploit multi-currency flows to obscure the origin of illicit funds. These risks pose financial, regulatory, and reputational threats, making accurate, explainable fraud detection central to NovaPay’s risk-based fraud and AML strategy.

The primary objective of this project was to accurately distinguish fraudulent transactions from legitimate activity, while maintaining transaction-level transparency to support fraud analysts, compliance teams, and regulatory oversight.

Data Preparation & Quality Assurance
A dedicated data cleaning and validation process was carried out to ensure model reliability and auditability.

Key actions included:
* Removal of invalid transaction records and rows with critical missing values
* Validation of monetary fields (negative and duplicate values assessed and retained where legitimate)
* Conversion of date fields to appropriate datetime formats
* Imputation of missing fees using mean values where applicable

Duplicate transaction amounts were intentionally retained, as they represent valid customer behaviour rather than data errors. The final cleaned dataset formed a reliable foundation for model development and evaluation.

Model Development & Performance
Four machine learning models were evaluated: Logistic Regression, Random Forest, XGBoost, and LightGBM. Given the imbalanced nature of fraud data, performance was assessed using precision, recall, F1-score, and ROC-AUC, rather than accuracy alone.
Best Overall Model: Random Forest

* 100% precision – zero legitimate transactions blocked
* 92% recall – majority of fraud cases detected
* 98% ROC-AUC – strong separation between fraud and legitimate activity
* 99% overall classification accuracy

This performance demonstrates a strong balance between fraud detection effectiveness and customer protection.

Explainability & Key Fraud Drivers (SHAP)
To ensure transparency, SHAP explainability was applied at both global and transaction levels.

Key global fraud drivers included:

* High-risk destination currencies (CNY, USD, NGN)
* KYC tier (standard and low tiers)
* Geographic risk indicators (unknown or high-risk locations)
* Channel usage (mobile vs web)
* Device trust and IP risk signals

A real fraud case (Test Sample #45) illustrated how these factors combine in practice, with a new account, high IP risk, low device trust, and risky currency corridor leading to a fraud prediction confidence of ~100%.

Business Insights & Impact:
* Currency corridors and KYC tiering are among the strongest fraud predictors
* Missing or inconsistent customer location data significantly increases risk
* Mobile channels show higher fraud exposure than web channels
* Device trust and IP-based signals remain critical controls
The model outperforms traditional rule-based systems, improves fraud detection rates, and eliminates unnecessary customer friction caused by false positives.

Project Outcomes:
* End-to-end fraud detection pipeline delivered
* Explainable, regulator-friendly model decisions enabled via SHAP
* Zero false positives with strong fraud recall achieved
* Model validated, saved, and ready for production deployment

Conclusion:
This project demonstrates that NovaPay can enhance fraud detection capability using explainable machine learning, achieving stronger fraud prevention while maintaining customer trust and regulatory compliance. The solution is production-ready and well-aligned with NovaPay’s risk-based fraud management strategy.
