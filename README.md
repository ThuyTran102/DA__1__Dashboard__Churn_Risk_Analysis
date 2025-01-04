# Churn_Risk_Analysis_Dashboard
Credit Card Customer Churn Risk Analysis using Power BI

## Table of Contents:


## Project Objectives:
The purpose of this analysis is to:
  - Define proper Key Measures/ Key Performance Indicators (KPIs) to measure customer churn.
  - Create a dashboard for the credit card manager that reflects all relevant KPIs and metrics in the dataset.
  - Based on findings, recommend actionable strategies to reduce churn and improve customer satisfaction.

#### Datasource:
**Inputs**:
  - **Churned Customers**: Customers who left within the last 12 months.
  - **Customer Demographics**: Age, gender, marital status, education level, income category, and number of dependents.
  - **Customer Account Information**: Card category, total products held, months on book, credit limit, average utilization ratio, and total revolving balance.
  - **Behavioral Metrics**: Transaction patterns, months inactive in the last 12 months, contacts with the bank, and changes in transaction count or amount.
  - Retention Risk Indicators**: Key trends such as inactivity periods, frequent bank contacts, and transactional behavior associated with higher churn rates.
The analysis aims to uncover critical insights and propose targeted recommendations to retain customers and enhance the overall service experience.


## Data Preparation:


## Data Analysis (DAX):


## Data Visualization (Dashboard):
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

| Dashboard 1 |
| ----------- |
|![dashboard1](https://github.com/ThuyTran102/Credit-Card-Transactions_FRAUD-Detection/blob/main/images/Churn_Risk_Doashboard1.png)|

| Dashboard 2 |
| ----------- |
|![dashboard2](https://github.com/ThuyTran102/Credit-Card-Transactions_FRAUD-Detection/blob/main/images/Churn_Risk_Doashboard2.png)|



## Insights:
1. Churn Rate - Customer Segmentation by Attrition:
  - The overall churn rate is 15.72%, indicating that a significant portion of the customer base is leaving within the last 12 months.
  - Out of 7,081 customers, 1,113 (15.72%) are attrited customers, while 5,968 (84.28%) are existing customers.
  - The majority of attrited customers are associated with the **Blue card** category (92.9%).

2. Behavioral Analysis:
  - Products Held: Customers holding 2 or 3 products with banks have a higher churn rate compared to others. Otherwise, customers holding 4+ products with banks have a low churn rate. 
  - Contacts with Bank: Customers with 3 contacts in the last 12 months have the highest churn rate. Otherwise, customers with 5+ contacts with banks have a low churn rate. 
  - Months Inactive: Customers inactive for 3 months show higher churn risk.
  - Transaction Behavior: A sharp increase in churn is observed with higher changes in transaction count from Q4 to Q1.
  - Credit Limit: The average credit limit for customers is $8,493, but it may not be optimized for certain segments.

3. Demographic Insights:
  - Gender: Male and female customers show similar churn distribution.
  - Marital Status: Married customers constitute the majority of both churned and existing groups, with a slightly higher churn risk among singles and married customers.
  - Dependents: Customers with 2-3 dependents tend to churn more.
  - Income Category: Most churned customers belong to the "Less than $40K" income group, indicating a potential affordability issue.
  - Education Level: Graduates dominate the attrited group, followed by High School.
  - Age Distribution:  Churn is more prevalent among customers aged 40-50, representing a critical age group for targeted retention strategies.


## Recommendations:
1. **Targeted Retention Campaigns**:  Focus on Blue card customers and those with 2 products held. Offering personalized rewards or benefits may reduce attrition.
Create engagement strategies for customers inactive for 3-4 months and those with 3-4 contacts to prevent dissatisfaction or unmet service needs.

2. **Product Optimization**:  Analyze the usage and satisfaction of customers holding 2 products and implement measures to increase value or enhance utility.

3. **Credit Limit Assessment**:  Conduct a review of credit limits, especially for the "Less than $40K" income group, to ensure affordability and better financial management for these customers.

4. **Demographic-Specific Actions**:  Design retention programs for married and single customers with tailored messaging to address their unique needs.
Provide financial literacy programs targeting High School graduates and low-income groups to improve their understanding of credit card benefits and terms.

5. **Enhanced Engagement**:  Develop loyalty programs or rewards targeting customers aged 40-50, who show a higher churn tendency.
Focus on proactive communication and personalized offers for customers in high-risk categories based on transaction changes and months inactive.

6. **Churn Prediction Model**:  Utilize predictive analytics to identify high-risk customers based on behavioral and demographic patterns and prioritize intervention.

These strategies, combined with continuous monitoring, can help reduce churn and improve customer satisfaction.
