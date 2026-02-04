# novapay-analytics
Fraudulent Transaction Detection for Digital Money Transfer 
 # Data Cleaning Summary

## Files
- 03_cleaning.ipynb: Notebook used for cleaning
- cleaned_transactions.csv: Final cleaned dataset

## Cleaning Rules Applied
- Describe datasets for numerical checks on negative transaction 
- Removed exact missing rows based on features with missing values
- Kept repeated amount_usd and fee values as valid transactions
- Filled missing fees with mean where applicable
- Converted date column to datetime format
- Removed rows with invalid transaction_id

## Notes
- Duplicate monetary values were not removed, as they represent legitimate transactions.
