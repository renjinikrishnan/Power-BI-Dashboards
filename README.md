# Finance Mortgage Loan Analysis: Microsoft Power BI Implementation

## Introduction

This README provides comprehensive details on the analysis questions, visualizations, and analyses conducted for the finance-mortgage-loan dataset, focusing on Microsoft Power BI implementation.


## 1. Details of the Data Set

The dataset used is "Finance-Mortgage_Loan_Application.xlsx," which contains information related to mortgage loan applications.

- **Size**: 700 KB

The dataset is organized into several sheets, each providing specific information:

### a. Borrower Sheet

- **Description**: Contains details about the borrowers, including personal information, contact details, and demographics.
- **Number of Rows**: 2000
- **Number of Columns**: 15
  - Key columns: Borrower Key, SSN (Social Security Number), First Name, Last Name, Email, Phone, Cell Phone, Marital Status, DOB (Date of Birth), Address, State, Zip, Sex, Ethnicity, Race

### b. Loan Sheet

- **Description**: Includes details about the loan type, purpose, co-borrower information, and other loan-specific details.
- **Number of Rows**: 2000
- **Number of Columns**: 9
  - Key columns: Loan Key, Loan ID, Property ID, Property Usage, Purpose of Loan, Credit Card Authorization, Co-Borrower SSN, Rent or Own, Loan Date

### c. Property Sheet

- **Description**: Contains information about properties related to the mortgage loans, including location and real estate agent details.
- **Number of Rows**: 2000
- **Number of Columns**: 8
  - Key columns: Property Key, Property ID, Property City, Property State, Property Zip, Real Estate Agent Name, Real Estate Agent Phone, Real Estate Agent Email

### d. Financials Sheet

- **Description**: Provides financial information such as income, assets, and liabilities related to the borrowers and their mortgage applications.
- **Number of Rows**: 3000
- **Number of Columns**: 16
  - Key columns: Financial Key, Borrower Key, Property Key, Loan Key, Years at Address, Loan Amount, Purchase Price, Number of Units, Monthly Income, Bonuses, Commission, Other Income, Checking, Savings, Retirement Fund, Mutual Fund



## 2. Data Model and DAXs

### a. Transform Data

The dataset was transformed to ensure relevance and consistency for analysis. Essential transformations were made, including:

- **Borrower Sheet**: Promoted headers and changed data types.
- **Loan Sheet**: Promoted headers and changed data types. Inserted year, quater, month, day and month name
- **Property Sheet**: Promoted headers, changed types, inserted a merged column (city and state), and renamed column.
- **Financial Sheet**: Promoted headers, changed types, removed null values (1000 rows) through loan key column.

### b. Data Model

The data model in Power BI integrates and establishes relationships between tables. Details are provided in the Power BI project files.

### c. Data Model

- **Created hierarchies for drill downs**

- Created 'Property Location Hierarchy'.
- Created 'Load Date Hierarchy'.


### d. DAXs

- **Calculated Columns**

Created some cloumn based on specific calculation/ condition.

- Calculated the 'Age' column from DOB.
- Created 'Age breakdown' column for dividing borrower's age into bins.
- Created 'Age breakdown numeric' column for having numeric equivalent for each age bin.

- **Measures**

A range of DAX calculations were performed, including:

- Calculating the total loan amount across all states and for all states.
- Computing the percentage of the loan amount for each state and age group.
- Counting credit approvals to identify trends.
- Getting selected value of 'state' to display in the visual (Property tab)


## 3. Visualization and Analysis

### Overview

Provides an overview of mortgage lending in the US for 2019, including:

- **Question 1**: Top 5 states with the highest total loan amounts in 2019.
  - **Answer**: California, New York, Pennsylvania, Michigan, and Kentucky had the highest loan amounts. California alone accounted for 6.95% of the total loan amount.

- **Question 2**: Age group with the highest total loan amount.
  - **Answer**: Individuals over 55+ years old had the highest total loan amount, totaling nearly 460 million USD (49.01% of the total loan amount).

- **Question 3**: Differences in mortgage lending based on marital status and gender.
  - **Answer**: Married couples had higher loan amounts, with females having higher loan amounts compared to males.

### Borrower

Analyzes trends and relationships between loan amounts and monthly income, categorized by age, marital status, race, and gender.

- **Question 4**: Relationship between loan amounts and monthly income by gender.
  - **Answer**: Higher monthly income correlates with higher loan approvals, indicating the importance of financial stability in securing larger loans.

### Loan Approval

Displays loan amount by state and age breakdown, percentage of loan amount by marital status, and the number of credit approvals by loan purpose.

- **Question 5**: Effect of loan purpose on credit approval.
  - **Answer**: Loans with the 'Purchase' purpose had the highest number of credit approvals, particularly for primary residence purchases.

### Property

Shows loan details based on property usage in various states and highlights areas with high loan amounts.

- **Question 6**: Top 5 cities for investment property loans.
  - **Answer**: California, Pennsylvania, New York, Kentucky, and Iowa were the top cities for investment property loans.

- **Question 7**: Distribution of loans by property usage.
  - **Answer**: Most loans are for primary residences, followed by investment properties, with second homes having the smallest share.

### Buying Trend

Displays the relationship between purchase price and monthly income over 2019 and features a multi-row card showing loan amounts by age and marital status.

- **Question 8**: Influence of total monthly income on home purchases.
  - **Answer**: Higher monthly income leads to higher home purchase investments, underscoring the importance of financial capability in purchasing decisions.

### Q&A

Contains Q&A sections for interacting with the reports using natural language queries.








Vocabulary:

Property:

Property Usage: 
* Investment
* Primary Residence
* Second Home

Purpose Of Loan:

1. Cash-Out Finance
A cash-out refinance allows a homeowner to replace their existing mortgage with a new one that has a higher loan amount. The difference between the old mortgage and the new mortgage is taken as cash by the homeowner.

Example:
Home Value: $300,000
Existing Mortgage Balance: $200,000
New Loan Amount: $250,000
Cash Received: $50,000
?? Used for: Home renovations, debt consolidation, or other expenses.
?? Higher interest rates than traditional refinancing.

2. Construction Loan
A construction loan is a short-term loan used to finance the building of a new home or property.
?? Funds are disbursed in stages (called "draws") based on the construction progress.
?? Higher interest rates compared to traditional mortgages.
?? Once the construction is complete, borrowers may convert it into a permanent mortgage or pay it off in full.

3. Construction-Perm (Construction-to-Permanent Loan)
A construction-to-permanent loan combines a construction loan and a permanent mortgage into one single loan.
How it Works:
1?? The loan starts as a construction loan while the home is being built.
2?? Once construction is complete, it automatically converts into a permanent mortgage.
?? Advantage: No need for two separate loans (avoids extra closing costs and paperwork).
?? Commonly used for custom-built homes.

4. No Cash-Out Refinance
A no cash-out refinance (or rate-and-term refinance) replaces the existing mortgage with a new one without taking additional cash.
?? The main goal is to reduce the interest rate or change the loan term (e.g., from 30 years to 15 years).
?? Unlike cash-out refinance, you do not receive any extra money beyond what is needed to pay off the existing loan.
Example:
Old Loan: $200,000 at 5% interest
New Loan: $200,000 at 3.5% interest
No extra cash is taken

5. Purchase Loan
A purchase loan is a mortgage loan used to buy a home (instead of refinancing an existing one).
?? Can be conventional, FHA, VA, or USDA loans.
?? Requires a down payment (usually 3% to 20% of the home price).
?? Interest rates and terms depend on the borrower's credit, income, and loan type.
Example:
Home Price: $300,000
Down Payment: $60,000 (20%)
Loan Amount: $240,000


 

### Measures (In separate Measures table) :

 [Total Loan Amount] = SUM('Financials'[Loan Amount])

[Total Loan Amount All States] = CALCULATE(
[Total Loan Amount],
REMOVEFILTERS('Borrower'[State]))

[% of All Loan Amount] = DIVIDE(
[Total Loan Amount], [Total Loan Amount All States],"Error")

[Total Loan Amount All Ages] = CALCULATE(
[Total Loan Amount],
REMOVEFILTERS('Borrower'[Age breakdown]))


[% of All Loan Amount by Ages] = DIVIDE(
'Financials'[Total Loan Amount],'Financials'[Total Loan Amount All Ages],"Error")

% of All Loan Amount by States = DIVIDE([Total Loan Amount], [Total Loan Amount All States], "Error")



Count Credit Approval = CALCULATE(COUNTROWS(Loan), 'Loan'[Credit Card Authorization] = "YES")

For card title based on property state selected
Selected State Card Value = CONCATENATE("Total Loan Amount : ", SELECTEDVALUE('Property'[Property State]))

For table title based on property state selected
Selected State for Table = CONCATENATE("Total Loan Amount by Property Usage and State : ",
SELECTEDVALUE('Property'[Property State]))




