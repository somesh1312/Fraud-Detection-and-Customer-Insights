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
2. **Suspicious Transaction Flag**:
   Flags transactions exceeding twice the account's average transaction amount.
   ```cognos
   IF ([TransactionAmount] > (AVG([TransactionAmount]) * 2)) THEN 'Flagged' ELSE 'Normal'
3. **Account Risk Score**:
   Combines login attempts and transaction amount ratios to assess account risk.
   ```cognos
   ([LoginAttempts] * 0.4) + ([TransactionAmount] / [AccountBalance] * 0.6)

## Dashboards
1. Fraud Detection Dashboard
   - Visuals
     - Bar Chart: Number of flagged transactions by location.
     - Heat Map: Transaction volume and flagged transactions by region.
     - KPI: Total flagged transactions.

2. Customer Insights Dashboard
   - Visuals
     - Pie Chart: Distribution of transaction types by age group.
     - Bar Chart: Average transaction amount by customer occupation.

3. Performance Metrics Dashboard
   - Visuals
     - Line Chart: Trends in days since last transaction over time.
     - Table: Risk score distribution across regions.
       - Table Details:
         - The table lists each region alongside the count of accounts grouped by risk categories (Low, Medium, High).
         - Provides an easy-to-understand breakdown of regional risks for operational decision-making.
           
## key Insights
1. Fraud Detection: Urban regions recorded the highest flagged transactions, suggesting concentrated risk areas.
2. Customer Behavior: Customers aged 26–35 contributed the highest transaction volumes, with online channels being the most popular.
3. Security: High login attempts coincided with flagged transactions, highlighting potential security risks.

## Skills Demonstrated

- Data Cleaning and Transformation in IBM Cognos
- Advanced Data Modeling and Derived Fields
- Data Visualization and Business Intelligence Reporting
- Fraud Detection and Risk Analysis





