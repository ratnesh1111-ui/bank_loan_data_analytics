#  Bank Loan Data Analytics Dashboard

This repository contains a **Power BI dashboard** analyzing bank loan data.  
It provides insights into loan distribution, payments, recoveries, and customer behavior.

---

##  Project Overview
The dashboard is designed to help banks and analysts understand:
- Loan disbursement trends across states and branches
- Recoveries and default patterns
- Customer demographics and credit behaviors
- Key influencers affecting loan default
- Drill-through navigation for advanced exploration

---

##  Dashboards Included
### 1️ Loan Overview Dashboard
- Loan disbursement trends  
- Total Funded Amount, Recoveries, Principal, and Interest  
- Waterfall chart for payments breakdown  

### 2️ Risk & Performance Dashboard
- Heatmap of loan default by state  
- Delinquency & default trends  
- Key Influencer visual to identify drivers of loan defaults  

### 3️ Customer Insights Dashboard
- Decomposition tree (loan performance by gender, age, region)  
- Borrower demographics  
- Drill-through navigation to customer-level details

---
Explanation:

SUM() → Aggregates numerical values like Payment, Principal, Interest.

COUNTROWS() + FILTER() → Counts the number of rows that satisfy a condition.

Example: Count of all loans where Is Default Loan = Y.

This gives you the number of defaulted loans vs. non-default loans.

These measures are useful for building KPIs, cards, and charts that separate risky loans from safe ones.
## Author section:-
(Ratnesh Jha, 225 )  
## Tools Used:-
### (Power BI, DAX, Excel)  
##  Key DAX Measures
```DAX
Total Payment = SUM('Banking Data'[Total_Pymnt])
Total Principal = SUM('Banking Data'[Total_Rec_Prncp])
Total Interest = SUM('Banking Data'[Total_Rec_Int])
Total Fees = SUM('Banking Data'[Total_Fees])
Total Recoveries = SUM('Banking Data'[Recoveries])

###  Customer Insights Dashboard
- **Decomposition Tree** → Explains loan performance by Gender, Age, and Region  
- **Key Influencer Visual** → Identifies main factors affecting loan defaults  
- Borrower demographics  
- Drill-through navigation to customer-level details
##  Key DAX Measures
```DAX
-- Count of Default Loans
Count of Default Loans = COUNTROWS(
    FILTER(
        'Banking Data',
        'Banking Data'[Is Default Loan] = "Y"
    )
)

-- Count of Non-Default Loans
Count of Non-Default Loans = COUNTROWS(
    FILTER(
        'Banking Data',
        'Banking Data'[Is Default Loan] = "N"
    )
)



   



