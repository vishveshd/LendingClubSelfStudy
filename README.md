# Lending Club Case Study

## Table of Contents
- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [Dataset Analysis](#dataset-analysis)
- [Approach](#approach)
- [Case Study Analysis](#case-study-analysis)
- [Conclusions](#conclusions)
- [Technologies Used](#technologies-used)
- [Glossary](#glossary)
- [Team](#team)

## Problem Statement

Lending Club is a consumer finance marketplace for personal loans that matches borrowers who are seeking a loan with investors looking to lend money and make a return.

It specializes in lending various types of loans to urban customers. When the company receives a loan application, it must decide for loan approval based on the applicant's profile.

Like most other lending companies, lending loans to "risky" applicants is the largest source of financial loss (called credit loss). Credit loss is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed.

In other words, borrowers who default cause the largest amount of loss to the lenders. In this case, customers labeled as *"charged-off"* are the defaulters.

The core objective of the exercise is to **help the company minimize credit loss**. The two potential sources of **credit loss** are:
- Applicant **likely to repay the loan**; rejecting such applicants results in loss of business.
- Applicant **not likely to repay**; approving such loans may lead to financial loss.

## Objectives

The goal is to identify risky loan applicants, so that such loans can be reduced, cutting down the amount of credit loss. The aim of this case study is to identify such applicants using EDA.

The company wants to understand the driving factors (driver variables) behind loan default, i.e., the variables that are strong indicators of default. This knowledge can be utilized for portfolio and risk assessment.

## Dataset Analysis

The dataset contains information about past loan applicants and whether they defaulted or not. The aim is to identify patterns that indicate if a person is likely to default. This could inform actions such as denying the loan, reducing the loan amount, or offering loans at higher interest rates to risky applicants.

- The dataset reflects loans post-approval, thus there is no information about rejection criteria.
- The loan process involves three steps:
    1. The borrower requests a loan amount (*loan_amnt*).
    2. The approver approves/rejects based on history/risk (*funded_amnt*).
    3. The final amount offered as a loan by the investor (*funded_amnt_inv*).

### Leading Attribute: Loan Status
The *loan_status* column has three distinct values:
- Fully-Paid: The customer successfully paid the loan.
- Charged-Off: The customer has defaulted.
- Current: Loan is in progress, these rows will be ignored for the analysis.

### Important Columns
- **Customer Demographics**
  - *Annual Income* (annual_inc)
  - *Home Ownership* (home_ownership)
  - *Employment Length* (emp_length)
  - *Debt to Income* (dti)
  - *State* (addr_state)
  
- **Loan Attributes**
  - *Loan Amount* (loan_amt)
  - *Grade* (grade)
  - *Term* (term)
  - *Loan Date* (issue_date)
  - *Purpose of Loan* (purpose)
  - *Interest Rate* (int_rate)
  - *Installment* (installment)
  - *Public Records* (public_rec)
  - *Public Records Bankruptcy* (public_rec_bankruptcy)

### Ignored Columns
- **Customer Behavior Columns**: Post-loan approval data like delinquencies, past payments, etc.
- **Granular Data**: Columns like sub-grade which are too detailed.
  
### Data Cleaning

1. **Rows to Drop**
   - Rows where *loan_status = Current* will be dropped.
   - Duplicate rows will be removed.

2. **Columns to Drop**
   - Columns with only NA values.
   - Columns with constant or zero values.
   - Columns where more than 65% of data is missing.
   - Redundant columns like *id, member_id, emp_title, desc, title, url*.
   - Customer behavior columns that don’t contribute to loan approval prediction.

3. **Data Type Conversion**
   - Convert columns like *loan_amnt, funded_amnt, int_rate* to the appropriate data types.

4. **New Columns Added**
   - *verification_status_n* based on verification hierarchy.
   - *issue_y* and *issue_m* extracted from *issue_d*.

## Approach

1. Data cleaning and manipulation.
2. Drop rows and columns based on EDA and domain knowledge.
3. Convert data types.
4. Identify columns with missing values for imputation.
5. Analysis of the cleaned dataset.
6. Outlier treatment.
7. Univariate, bivariate, and derived metrics analysis.
8. Conclusions and recommendations.

## Case Study Analysis

- Analysis is conducted using univariate, bivariate, and multivariate techniques to identify significant factors contributing to loan default.

## Conclusions

- Insights gained from the analysis to be mentioned here.

## Technologies Used

- **Python** - Version 3.9.12
- **numpy** - Version 1.21.5
- **pandas** - Version 1.4.2
- **matplotlib** - Version 3.5.1
- **seaborn** - Version 0.11.2
- **Jupyter Notebook** - Version 3.3.2
- **JupyterLab** - Version 6.4.11
- **Anaconda** - Version 2.1

## Glossary

- **EDA**: Exploratory Data Analysis

## Team

- Vinay Kumar Saroha
- Vishvesh Deobhankar