Got it! Here’s the updated **README** with the formula centered on the line and each notebook name listed once in bold:
# Credit Risk Modeling

## Overview
This project demonstrates the implementation of **Credit Risk Modeling** using historical loan data. The model calculates the **Expected Loss (EL)** of a bank’s loan portfolio based on the following formula:

<p align="center">
  **EL = PD × LGD × EAD**
</p>

Where:
- **PD (Probability of Default)**: The likelihood that a borrower will default on their loan.
- **LGD (Loss Given Default)**: The percentage of the loan that is lost in the event of a default.
- **EAD (Exposure at Default)**: The amount of the loan that is at risk when the borrower defaults.

The model uses loan data from **2007 to 2014** for training and testing, with data from **2015** reserved for **model monitoring**. The goal is to assess the bank’s expected loss over time and make informed decisions about future lending practices. Typically, expected loss values range between **2% and 10%** of the exposure value, guiding the bank's decision-making to be either more conservative or more aggressive in issuing loans.

## Table of Contents
1. [Installation](#installation)
2. [Notebooks](#notebooks)
3. [Input Data](#input-data)
4. [Results](#results)
5. [Course Information](#course-information)

## Installation

To get started with this project, clone the repository to your local machine:

```bash
git clone https://github.com/mypham14/credit-risk-modeling.git
cd credit-risk-modeling
```

### Prerequisites

You will need to have **Python 3.x** and **pip** installed. Install the required Python packages by running:

```bash
pip install -r requirements.txt
```

The project uses the following dependencies:
- `pandas`: For handling and manipulating data
- `numpy`: For mathematical calculations
- `matplotlib`: For data visualizations (optional)
- `seaborn`: For advanced visualizations (optional)
- `scikit-learn`: For data splitting (`train_test_split`) and performance metrics
- `scipy`: For statistical functions
- `pickle`: For saving and loading models

## Notebooks

This project is organized into several Jupyter Notebooks, each addressing different aspects of credit risk modeling:

- **[Credit Risk Modeling Pt 1 - Preprocessing.ipynb](Credit Risk Modeling Pt 1 - Preprocessing.ipynb)**: Handles the preprocessing steps, such as data cleaning, feature selection, and preparing the datasets for training and testing.
  
- **[Credit Risk Modeling Pt 2 - PD.ipynb](Credit Risk Modeling Pt 2 - PD.ipynb)**: Focuses on building a model for calculating the **Probability of Default (PD)** using machine learning techniques.

- **[Credit Risk Modeling Pt 3 - Monitoring.ipynb](Credit Risk Modeling Pt 3 - Monitoring.ipynb)**: Monitors the model’s performance using data from **2015** to assess its generalization ability on unseen data.

- **[Credit Risk Modeling Pt 4 - LGD and EAD Models and Calculating EL.ipynb](Credit Risk Modeling Pt 4 - LGD and EAD Models and Calculating EL.ipynb)**: Builds models for **Loss Given Default (LGD)** and **Exposure at Default (EAD)**, followed by the calculation of the **Expected Loss (EL)** based on the formula.

## Input Data

The loan dataset includes various columns with information about each loan, such as borrower details, loan status, and payment history. Below is a list of the key columns used in this project:

- `id`: Unique identifier for each loan
- `member_id`: Member ID associated with the loan
- `loan_amnt`: Loan amount
- `funded_amnt`: Funded amount for the loan
- `funded_amnt_inv`: The investor's portion of the loan
- `term`: Term of the loan in months
- `int_rate`: Interest rate on the loan
- `installment`: Monthly installment payment amount
- `grade`: Credit grade assigned to the loan
- `sub_grade`: Sub-category of the credit grade
- `emp_title`: Title of the borrower's employment
- `emp_length`: Length of employment in years
- `home_ownership`: Home ownership status
- `annual_inc`: Annual income of the borrower
- `verification_status`: Whether the income was verified
- `issue_d`: Date when the loan was issued
- `loan_status`: Current status of the loan
- `pymnt_plan`: Payment plan status
- `purpose`: Purpose of the loan
- `zip_code`: Borrower's zip code
- `addr_state`: Borrower's state
- `dti`: Debt-to-income ratio
- `delinq_2yrs`: Number of delinquencies in the last 2 years
- `earliest_cr_line`: Date of the borrower's earliest credit line
- `inq_last_6mths`: Number of inquiries in the last 6 months
- `mths_since_last_delinq`: Months since the last delinquency
- `mths_since_last_record`: Months since the last record
- `open_acc`: Number of open credit accounts
- `pub_rec`: Number of derogatory public records
- `revol_bal`: Revolving balance
- `revol_util`: Revolving utilization rate
- `total_acc`: Total number of credit accounts
- `initial_list_status`: Initial listing status of the loan
- `out_prncp`: Outstanding principal
- `out_prncp_inv`: Outstanding principal (investor portion)
- `total_pymnt`: Total payment made on the loan
- `total_pymnt_inv`: Total payment made to the investor
- `total_rec_prncp`: Total principal recovered
- `total_rec_int`: Total interest recovered
- `total_rec_late_fee`: Total late fees recovered
- `recoveries`: Amount recovered after a default
- `collection_recovery_fee`: Collection recovery fee paid
- `last_pymnt_d`: Last payment date
- `last_pymnt_amnt`: Last payment amount
- `next_pymnt_d`: Next payment date
- `last_credit_pull_d`: Last date the borrower's credit was pulled
- `collections_12_mths_ex_med`: Collections in the last 12 months, excluding medical collections
- `mths_since_last_major_derog`: Months since the last major derogatory event
- `policy_code`: Policy code of the loan
- `application_type`: Type of loan application
- `annual_inc_joint`: Joint annual income (if applicable)
- `dti_joint`: Joint debt-to-income ratio (if applicable)
- `verification_status_joint`: Joint verification status (if applicable)
- `acc_now_delinq`: Number of accounts currently in delinquency
- `tot_coll_amt`: Total collections amount
- `tot_cur_bal`: Total current balance across all accounts
- `open_acc_6m`: Number of open credit accounts in the last 6 months
- `open_il_6m`: Number of open installment loans in the last 6 months
- `open_il_12m`: Number of open installment loans in the last 12 months
- `open_il_24m`: Number of open installment loans in the last 24 months
- `mths_since_rcnt_il`: Months since the most recent installment loan opened
- `total_bal_il`: Total balance of installment loans
- `il_util`: Installment loan utilization rate
- `open_rv_12m`: Number of open revolving accounts in the last 12 months
- `open_rv_24m`: Number of open revolving accounts in the last 24 months
- `max_bal_bc`: Maximum balance on a revolving account
- `all_util`: All credit utilization rate
- `total_rev_hi_lim`: Total high credit/limit across all revolving accounts
- `inq_fi`: Number of inquiries for financial products
- `total_cu_tl`: Total credit union accounts
- `inq_last_12m`: Number of inquiries in the last 12 months

## Results

The **Expected Loss (EL)** value helps the bank assess the potential risk in its loan portfolio. Based on the model, we observed the following:

- **Proportion of defaults** is around **7.6%**.
- Banks typically hold **10% of their assets as capital**.
- The **Expected Loss (EL)** on a loan portfolio should generally be **less than its capital**.
- In practice, observed expected loss values are anywhere between **2% and 10%** of the loan exposure.

Given these observations, the bank can adjust its lending strategy. A higher **Expected Loss (EL)** indicates more risk, prompting the bank to be **more conservative** in its lending practices. Conversely, a lower **EL** may allow the bank to take **more aggressive lending** actions.

## Course Information

This project is part of a course offered by **365 Careers**, which teaches practical applications of financial modeling, credit risk assessment, and Python programming for finance.
