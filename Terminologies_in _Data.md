# 📖 Data Dictionary (Loan Dataset Terminologies)

## Overview

This document explains the meaning of each field used in the Bank Loan dataset and its business significance. Understanding these attributes helps in interpreting dashboard insights and performing meaningful financial analysis.

---

# Dataset Fields

## 1. Loan ID

**Description**

A unique identifier assigned to every loan application.

**Business Importance**

- Tracks each loan individually
- Prevents duplicate records
- Used as the primary key for loan management

---

## 2. Address State

**Description**

The borrower's state of residence.

**Business Importance**

- Analyze regional lending trends
- Compare loan performance across states
- Support geographical risk analysis

---

## 3. Employee Length

**Description**

The total duration the borrower has been employed.

**Business Importance**

- Indicates employment stability
- Helps estimate repayment capability
- Longer employment generally suggests lower lending risk

---

## 4. Employee Title

**Description**

The borrower's occupation or job role.

**Business Importance**

- Understand income sources
- Segment customers by profession
- Support borrower profiling

---

## 5. Grade

**Description**

A credit risk grade assigned to the borrower.

**Business Importance**

- Indicates overall creditworthiness
- Used for loan pricing
- Helps assess lending risk

---

## 6. Sub Grade

**Description**

A more detailed classification within each loan grade.

**Business Importance**

- Provides finer risk categorization
- Supports accurate interest rate assignment
- Improves credit analysis

---

## 7. Home Ownership

**Description**

The borrower's housing status.

Examples:

- Rent
- Mortgage
- Own

**Business Importance**

- Indicates financial stability
- Helps estimate default risk
- Supports customer segmentation

---

## 8. Issue Date

**Description**

The date on which the loan was issued.

**Business Importance**

- Enables monthly and yearly trend analysis
- Supports MTD and PMTD calculations
- Tracks loan origination over time

---

## 9. Last Credit Pull Date

**Description**

The most recent date when the borrower's credit report was accessed.

**Business Importance**

- Tracks credit history updates
- Assists in credit monitoring
- Supports lending decisions

---

## 10. Last Payment Date

**Description**

The latest payment received from the borrower.

**Business Importance**

- Monitors repayment behavior
- Detects overdue accounts
- Evaluates customer payment history

---

## 11. Loan Status

**Description**

Represents the current condition of the loan.

Common Values:

- Current
- Fully Paid
- Charged Off

**Business Importance**

- Measures portfolio health
- Identifies good and bad loans
- Supports risk reporting

---

## 12. Next Payment Date

**Description**

Scheduled date for the borrower's upcoming installment.

**Business Importance**

- Supports payment tracking
- Forecasts expected cash inflow
- Assists collection planning

---

## 13. Loan Purpose

**Description**

The reason for borrowing the loan.

Examples:

- Debt Consolidation
- Home Improvement
- Education
- Medical Expenses
- Small Business

**Business Importance**

- Identifies customer borrowing trends
- Supports product strategy
- Helps segment customers

---

## 14. Loan Term

**Description**

Duration of the loan.

Common Values:

- 36 Months
- 60 Months

**Business Importance**

- Determines repayment schedule
- Impacts interest earnings
- Supports portfolio planning

---

## 15. Verification Status

**Description**

Indicates whether the borrower's financial information has been verified.

**Business Importance**

- Measures data reliability
- Reduces fraud risk
- Improves lending confidence

---

## 16. Annual Income

**Description**

The borrower's total yearly income.

**Business Importance**

- Determines loan eligibility
- Estimates repayment capacity
- Used for affordability assessment

---

## 17. Debt-to-Income Ratio (DTI)

**Description**

The ratio of monthly debt obligations to monthly income.

**Business Importance**

- Measures financial health
- Estimates repayment ability
- Higher DTI generally indicates higher lending risk

---

## 18. Installment

**Description**

The fixed monthly payment made by the borrower.

**Business Importance**

- Calculates repayment schedules
- Estimates cash inflows
- Measures loan affordability

---

## 19. Interest Rate

**Description**

Annual percentage charged on the borrowed amount.

**Business Importance**

- Determines borrowing cost
- Generates interest income for the bank
- Used for profitability analysis

---

## 20. Loan Amount

**Description**

The total principal amount borrowed by the customer.

**Business Importance**

- Represents lending exposure
- Used to calculate funded amount
- Measures portfolio size

---

# How These Fields Are Used

The dashboard leverages these fields to calculate and visualize:

- Total Loan Applications
- Total Funded Amount
- Total Amount Received
- Average Interest Rate
- Average Debt-to-Income Ratio (DTI)
- Good Loan Percentage
- Bad Loan Percentage
- Monthly Lending Trends
- Loan Status Analysis
- State-wise Distribution
- Home Ownership Analysis
- Employee Length Analysis
- Loan Purpose Analysis

---


