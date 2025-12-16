# Customer Churn Analysis (Telecom Industry)

## Overview
Customer churn is a critical challenge in the telecommunications industry due to high acquisition costs and low switching barriers.  
This project applies an end-to-end, explainable data science workflow to identify, validate, and interpret the key drivers of customer churn using statistically grounded methods.

The focus is on **interpretability, statistical significance, and business impact**, rather than black-box prediction alone.

---

## Business Problem
**Core Question:**

Which customer characteristics and behaviors most strongly influence churn, and are these effects statistically significant?

Understanding churn behavior supports:
- Improved customer lifetime value (CLV)
- Optimized pricing strategies
- Effective retention programs
- Reduced early-life customer loss

---

## Objectives
- Identify key churn drivers using validated statistical methods
- Quantify relationships between churn and customer attributes
- Engineer business-meaningful features
- Reduce feature dimensionality while preserving interpretability
- Translate insights into actionable retention strategies

---

## Dataset
**Name:** Telco Customer Churn Dataset  
**Type:** Real-world customer subscription data  

### Feature Types
- **Numerical:** `tenure`, `MonthlyCharges`, `TotalCharges`
- **Categorical:** `Contract`, `PaymentMethod`, service subscriptions, billing preferences
- **Target Variable:**  
  - `Churn` → 1 (Churned), 0 (Retained)

Each record represents a unique customer at the time of analysis.

---

## Analytical Workflow
1. Data Loading & Inspection  
2. Data Wrangling & Quality Management  
3. Exploratory Data Analysis (EDA)  
4. Feature Engineering  
5. Feature Selection  
6. Probability Analysis & Hypothesis Testing  
7. Dimensionality Reduction (PCA)  
8. Business Insight Interpretation  

---

## Data Preparation
- Data type standardization (`TotalCharges` converted to numeric)
- Domain-based missing value treatment  
  (`TotalCharges = tenure × MonthlyCharges`)
- Duplicate removal
- Categorical normalization (lowercase, trimmed)
- Outlier treatment using IQR capping
- Identifier removal (`customerID`)
- Binary encoding of churn

**Final Output:** `cleaned_telco_churn.csv`  
(No missing values or duplicate records)

---

## Exploratory Data Analysis (EDA)
Key findings:
- Highest churn risk occurs within the first 6–12 months
- Higher monthly charges increase churn likelihood
- Month-to-month contracts show significantly higher churn
- Billing and payment methods influence churn behavior

---

## Feature Engineering
Business-driven engineered features include:
- `TenureGroup`
- `AvgMonthlySpend`
- `IsLongContract`
- `PaperlessAndElectronic`
- `HasTechSupportOrSecurity`
- `ServiceCount`

Each feature captures meaningful customer behavior and improves explanatory power.

---

## Feature Selection
- Correlation analysis
- Chi-Square tests
- Recursive Feature Elimination (RFE)
- L1-regularized Logistic Regression

Final features were selected using a **consensus-based approach** to improve robustness and interpretability.

---

## Statistical Analysis
All tests were conducted at **α = 0.05**.

| Test | Relationship | Result |
|----|----|----|
| t-test | MonthlyCharges vs Churn | Significant |
| Chi-Square | PaymentMethod vs Churn | Significant |
| ANOVA | Contract vs MonthlyCharges | Significant |
| Correlation | Tenure vs Churn | Significant |

All null hypotheses were rejected.

---

## Dimensionality Reduction (PCA)
- Features encoded and standardized
- Majority of variance captured by the first components
- Confirms redundancy among original features

**Interpretation:**
- PC1: Financial exposure and usage intensity
- PC2: Contractual commitment and billing behavior

PCA results align with EDA findings.

---

## Business Insights
### Key Churn Drivers
- Short tenure
- High monthly charges
- Month-to-month contracts
- Low service engagement

### Strategic Recommendations
- Strengthen early onboarding programs
- Incentivize long-term contracts
- Personalize pricing for high-risk segments
- Increase service bundling to reduce switching behavior

---

## Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook
- Power Bi
---

