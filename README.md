# Fraud Detection and Customer Insights Dashboards using IBM Cognos Analytics

## Overview
This repository showcases a data analytics project featuring interactive dashboards built with **IBM Cognos Analytics**. The project focuses on detecting fraudulent activities, analyzing customer transaction behavior, and providing actionable business insights.

---

## Project Objective
1. Detect and visualize potential fraudulent activities in financial transactions.
2. Analyze customer behavior across demographics and transaction patterns.
3. Track performance metrics and identify actionable insights for business optimization.

---

## Dataset
- **Source**: Kaggle
- **Description**:
  - The dataset contains 2,500+ rows of financial transaction data.
  - Key columns:
    - `TransactionID`, `TransactionAmount`, `TransactionDate`
    - `Location`, `DeviceID`, `CustomerAge`, `CustomerOccupation`
    - `TransactionDuration`, `LoginAttempts`, `AccountBalance`

---

## Derived Fields
1. **Days Since Last Transaction**:  
   Calculates the time gap between consecutive transactions.
   ```cognos
   _days_between([TransactionDate], [PreviousTransactionDate])
2. **Suspicious Transaction Flag:
   Flags transactions exceeding twice the account's average transaction amount.
   ```cognos
   IF ([TransactionAmount] > (AVG([TransactionAmount]) * 2)) THEN 'Flagged' ELSE 'Normal'

