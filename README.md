# Credit Model Bias Testing

![screenshot-localhost_8888-2025 04 02-14_02_55](https://github.com/user-attachments/assets/b632bdbf-81be-4ece-a5b7-2751716feb26)

### Project Overview

This project analyzes the German Credit Dataset to:

1. Predict credit risk (good vs. bad) using Logistic Regression and Decision Tree models.

2. Audit fairness across gender groups (male/female) using:
- Demographic Parity (approval rate equality)
- Equalized Odds (error rate equality)
-  Disparate Impact Ratio (legal fairness standard)

**Key Question:** Do models unintentionally discriminate based on gender?

### Dataset

The dataset contains credit application information, including applicant demographics, financial status, and loan outcomes. Key variables include:

- Age
- Gender
- Credit History
- Employment Duration
- Loan Amount
- Default (Target Variable: 1 = Default, 0 = No Default)

### Methodology

1. Data Preprocessing
- Cleaned missing values in Saving accounts/Checking account.
- Encoded categorical features:Label Encoding for ordinal features (e.g., account types). One-Hot Encoding for nominal features (e.g., Sex, Housing).
- Balanced class imbalance using SMOTE.

2. Model Training

- Logistic Regression
- Random Forest
- XGBoost

3. Fairness Evaluation

Fairlearn Metrics:
- Demographic Parity Difference (<0.1 is fair)
- Equalized Odds Difference (<0.1 is fair)
- Disparate Impact Ratio (0.8–1.2 is fair)

2. Aequitas Audit:
- False Positive Rate (FPR) Disparity
- False Discovery Rate (FDR) Disparity

### Key Insights:

- Decision Tree is fairer in approvals (2.4% difference vs. 6.7%) but still has biased error rates.
- Both models comply with legal disparate impact standards (0.8–1.2).

### Conclusion

This analysis underscores that model selection is a socio-technical decision. While the Decision Tree is fairer in approvals, its higher false alarms for "bad risk" could increase lender risk. Striking the right balance requires collaboration between data scientists, policymakers, and business leaders.

### Source

![German Credit Data from Kaggle](https://www.kaggle.com/datasets/varunchawla30/german-credit-data)
