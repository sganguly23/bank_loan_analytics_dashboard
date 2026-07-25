# SQL Queries Documentation

**Project:** Bank Loan Analysis Dashboard  
**Developed by:** Sourojeet Ganguly

---

# Overview

This document contains all SQL queries used to build the KPIs and visualizations for the Bank Loan Analysis Dashboard.

The queries calculate key business metrics including loan applications, funded amount, repayment performance, loan quality, portfolio analysis, and customer segmentation.

---

# Database

**Table Used**

```sql
bank_loan_data
```

---

# A. Executive Summary KPIs

## 1. Total Loan Applications

```sql
SELECT COUNT(id) AS Total_Applications
FROM bank_loan_data;
```

---

## 2. Month-to-Date (MTD) Loan Applications

```sql
SELECT COUNT(id) AS Total_Applications
FROM bank_loan_data
WHERE MONTH(issue_date)=12;
```

---

## 3. Previous Month-to-Date (PMTD) Loan Applications

```sql
SELECT COUNT(id) AS Total_Applications
FROM bank_loan_data
WHERE MONTH(issue_date)=11;
```

---

## 4. Total Funded Amount

```sql
SELECT SUM(loan_amount) AS Total_Funded_Amount
FROM bank_loan_data;
```

---

## 5. MTD Funded Amount

```sql
SELECT SUM(loan_amount) AS Total_Funded_Amount
FROM bank_loan_data
WHERE MONTH(issue_date)=12;
```

---

## 6. PMTD Funded Amount

```sql
SELECT SUM(loan_amount) AS Total_Funded_Amount
FROM bank_loan_data
WHERE MONTH(issue_date)=11;
```

---

## 7. Total Amount Received

```sql
SELECT SUM(total_payment) AS Total_Amount_Collected
FROM bank_loan_data;
```

---

## 8. Average Interest Rate

```sql
SELECT AVG(int_rate)*100 AS Avg_Int_Rate
FROM bank_loan_data;
```

---

## 9. Average Debt-to-Income Ratio (DTI)

```sql
SELECT AVG(dti)*100 AS Avg_DTI
FROM bank_loan_data;
```

---

# B. Good Loan Analysis

## Good Loan Percentage

```sql
SELECT
(COUNT(CASE
WHEN loan_status='Fully Paid'
OR loan_status='Current'
THEN id END)*100.0)
/COUNT(id) AS Good_Loan_Percentage
FROM bank_loan_data;
```

---

## Good Loan Applications

```sql
SELECT COUNT(id)
FROM bank_loan_data
WHERE loan_status='Fully Paid'
OR loan_status='Current';
```

---

## Good Loan Funded Amount

```sql
SELECT SUM(loan_amount)
FROM bank_loan_data
WHERE loan_status='Fully Paid'
OR loan_status='Current';
```

---

## Good Loan Amount Received

```sql
SELECT SUM(total_payment)
FROM bank_loan_data
WHERE loan_status='Fully Paid'
OR loan_status='Current';
```

---

# C. Bad Loan Analysis

## Bad Loan Percentage

```sql
SELECT
(COUNT(CASE
WHEN loan_status='Charged Off'
THEN id END)*100.0)
/COUNT(id) AS Bad_Loan_Percentage
FROM bank_loan_data;
```

---

## Bad Loan Applications

```sql
SELECT COUNT(id)
FROM bank_loan_data
WHERE loan_status='Charged Off';
```

---

## Bad Loan Funded Amount

```sql
SELECT SUM(loan_amount)
FROM bank_loan_data
WHERE loan_status='Charged Off';
```

---

## Bad Loan Amount Received

```sql
SELECT SUM(total_payment)
FROM bank_loan_data
WHERE loan_status='Charged Off';
```

---

# D. Loan Status Analysis

```sql
SELECT
loan_status,
COUNT(id) AS LoanCount,
SUM(total_payment) AS Total_Amount_Received,
SUM(loan_amount) AS Total_Funded_Amount,
AVG(int_rate*100) AS Interest_Rate,
AVG(dti*100) AS DTI
FROM bank_loan_data
GROUP BY loan_status;
```

---

# E. Dashboard Overview Queries

## Monthly Trends

```sql
SELECT
MONTH(issue_date) AS Month_Number,
DATENAME(MONTH,issue_date) AS Month_Name,
COUNT(id) AS Total_Loan_Applications,
SUM(loan_amount) AS Total_Funded_Amount,
SUM(total_payment) AS Total_Amount_Received
FROM bank_loan_data
GROUP BY MONTH(issue_date),DATENAME(MONTH,issue_date)
ORDER BY MONTH(issue_date);
```

---

## State-wise Analysis

```sql
SELECT
address_state,
COUNT(id),
SUM(loan_amount),
SUM(total_payment)
FROM bank_loan_data
GROUP BY address_state;
```

---

## Loan Term Analysis

```sql
SELECT
term,
COUNT(id),
SUM(loan_amount),
SUM(total_payment)
FROM bank_loan_data
GROUP BY term;
```

---

## Employee Length Analysis

```sql
SELECT
emp_length,
COUNT(id),
SUM(loan_amount),
SUM(total_payment)
FROM bank_loan_data
GROUP BY emp_length;
```

---

## Loan Purpose Analysis

```sql
SELECT
purpose,
COUNT(id),
SUM(loan_amount),
SUM(total_payment)
FROM bank_loan_data
GROUP BY purpose;
```

---

## Home Ownership Analysis

```sql
SELECT
home_ownership,
COUNT(id),
SUM(loan_amount),
SUM(total_payment)
FROM bank_loan_data
GROUP BY home_ownership;
```

---

# Dashboard Filters

The dashboard supports dynamic filtering by various attributes, including:

- Grade
- State
- Loan Status
- Term
- Home Ownership
- Employee Length
- Purpose

These filters allow users to drill down into specific customer segments and compare performance across different categories.

---

# Conclusion

These SQL queries form the foundation of the Power BI dashboard by transforming raw loan data into meaningful KPIs and business insights. They support executive reporting, portfolio monitoring, risk assessment, and trend analysis for better lending decisions.

---


