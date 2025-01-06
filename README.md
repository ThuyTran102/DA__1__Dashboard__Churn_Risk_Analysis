# Churn_Risk_Analysis_Dashboard
### Credit Card Customer Churn Risk Analysis using **Power BI**
<p align="left" style="margin-top: 20px; margin-bottom: 20px;">
<img width="45%" src="https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard/blob/main/images/Churn_Image.png" alt="Outcome"></img>
</p>

## Table of Contents:
- [Project Objectives](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard?tab=readme-ov-file#project-objectives)
- [Datasource](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard?tab=readme-ov-file#datasource)
- [Data Preparation](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard?tab=readme-ov-file#data-preparation)
- [Data Analysis (DAX)](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard?tab=readme-ov-file#data-analysis-dax)
- [Data Visualization (Dashboard)](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard?tab=readme-ov-file#data-visualization-dashboard)
- [Insights](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard?tab=readme-ov-file#insights)
- [Recommendations](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard?tab=readme-ov-file#recommendations)


## Project Objectives:
The purpose of this analysis is to:
  - Define proper Key Measures/ Key Performance Indicators (KPIs) to measure customer churn.
  - Create a dashboard for the credit card manager that reflects all relevant KPIs and metrics in the dataset.
  - Based on findings, recommend actionable strategies to reduce churn and improve customer satisfaction.

## Datasource:
I got this dataset from a website with the URL as https://leaps.analyttica.com/home and available at: [Churn Dataset](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard/blob/main/BankChurners.csv)

**Inputs**:
  - **Churned Customers**: Customers who left within the last 12 months.
  - **Customer Demographics**: Age, gender, marital status, education level, income category, and number of dependents.
  - **Customer Account Information**: Card category, total products held, months on book, credit limit, average utilization ratio, and total revolving balance.
  - **Behavioral Metrics**: Transaction patterns, months inactive in the last 12 months, contacts with the bank, and changes in transaction count or amount.
  - **Retention Risk Indicators**: Key trends such as inactivity periods, frequent bank contacts, and transactional behavior associated with higher churn rates.
The analysis aims to uncover critical insights and propose targeted recommendations to retain customers and enhance the overall service experience.

The tabulation below shows the `BankChurners` table with its column names and their description:
| Column Name | Description |
| ----------- | ----------- |
| CLIENTNUM |   Client number. Unique identifier for the customer holding the account|
| Attrition_Flag | Internal event (customer activity) variable |
| Customer_Age | Demographic variable - Customer's Age in Years |
| Gender | Demographic variable - M=Male, F=Female |
| Dependent_count | Demographic variable - Number of dependents |
| Education_Level | Demographic variable - Educational Qualification of the account holder (example: high school, college graduate, etc.) |
| Marital_Status | Demographic variable - Married, Single, Divorced, Unknown |
| Income_Category | Demographic variable - Annual Income Category of the account holder (< $40K, $40K - 60K, $60K - $80K, $80K-$120K, >$ |
| Card_Category | Product Variable - Type of Card (Blue, Silver, Gold, Platinum) |
| Months_on_book | Describes how long as a customer - Indicates customer loyalty and tenure |
| Total_Relationship_count | Total no. of products held by the customer |
| Months_Inactive_12_mon | No. of months inactive in the last 12 months |
| Contacts_Count_12_mon | No. of Contacts in the last 12 months |
| Credit_Limit | Credit Limit on the Credit Card - Provides insight into customer creditworthiness and spending potential |
| Total_Ct_Chng_Q4_Q1 | Change in Transaction Count (Q4 over Q1) |
| Avg_Utilization_Ratio | Average Card Utilization Ratio |


## Data Preparation:
Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modeling.
- Ensure all columns are formatted correctly (e.g., numeric data as decimals, dates as date types).
- Handle missing or incorrect data using Power Query (replace, remove, or impute values).

## Data Analysis (DAX):
Measures used in all visualization are:
- Churn_Rate = `DIVIDE(
    COUNTROWS(FILTER('BankChurners', 'BankChurners'[Attrition_Flag] = "Attrited Customer")),
    COUNTROWS('BankChurners'), 0
)`
- Churn_Count = `CALCULATE(
    COUNTROWS('BankChurners'),
    'BankChurners'[Attrition_Flag] = "Attrited Customer"
)`
- Total_Customers = `COUNT(BankChurners[CLIENTNUM])`


## Data Visualization (Dashboard):
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

| Dashboard 1 |
| ----------- |
|![dashboard1](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard/blob/main/images/Churn_Risk_Doashboard1.png)|

| Dashboard 2 |
| ----------- |
|![dashboard2](https://github.com/ThuyTran102/Churn_Risk_Analysis_Dashboard/blob/main/images/Churn_Risk_Doashboard2.png)|



## Insights:
1. Churn Rate - Customer Segmentation by Attrition:
  - The overall churn rate is 15.72%, indicating that a significant portion of the customer base is leaving within the last 12 months.
  - Out of 7,081 customers, 1,113 (15.72%) are attrited customers, while 5,968 (84.28%) are existing customers.
  - The majority of attrited customers are associated with the **Blue card** category (92.9%).

2. Behavioral Analysis:
  - Products Held: Customers holding 2 or 3 products with banks have a higher churn rate compared to others. Otherwise, customers holding 4+ products with banks have a low churn rate => Customers holding fewer products are at a higher risk of churn.
  - Contacts with Bank: Customers with 3 contacts in the last 12 months have the highest churn rate. Otherwise, customers with 5+ contacts with banks have a low churn rate. 
  - Months Inactive: Customers inactive for 3 months show higher churn risk.
  - Transaction Behavior: A sharp increase in churn is observed with higher changes in transaction count from Q4 to Q1. The majority of churned customers have an Avg_Utilization_Ratio of 0.00, suggesting that inactive customers who do not utilize their credit cards are at a higher risk of churn.
  - Credit Limit: No effect of credit limit on customer churn was found in this dataset.

3. Demographic Insights:
  - Gender: Male and female customers show similar churn distribution.
  - Marital Status: Married customers constitute the majority of both churned and existing groups, with a slightly higher churn risk among singles and married customers.
  - Dependents: Customers with 2-3 dependents tend to churn more.
  - Income Category: Most churned customers belong to the "Less than $40K" income group, indicating a potential affordability issue.
  - Education Level: Graduates dominate the attrited group, followed by High School.
  - Age Distribution:  Churn is more prevalent among customers aged 40-50, representing a critical age group for targeted retention strategies.


## Recommendations:
1. **Retention Campaign**: Target Blue card holders and customers with two products by offering tailored rewards. Engage inactive customers (3–4 months) and those with limited contacts to address dissatisfaction.
2. **Product Optimization**: Enhance value for customers with two or more products and encourage cross-selling to less engaged users.
3. **Credit Limit Review**: Reassess credit limits for the "Less than $40K" income group to ensure affordability and financial stability.
4. **Demographic Strategies**: Tailor retention programs for married and single customers. Provide financial literacy initiatives for low-income and high school graduate groups.
5. **Boost Engagement**: Offer loyalty rewards for customers aged 40–50 and proactive communication for high-risk users. Incentivize inactive customers with cashback or low-interest offers, gather feedback on inactivity, and set alerts for low utilization accounts to prevent churn.
6. **Churn Prediction Model**:  Utilize predictive analytics to identify high-risk customers based on behavioral and demographic patterns and prioritize intervention.

These strategies, combined with continuous monitoring, can help reduce churn and improve customer satisfaction.
