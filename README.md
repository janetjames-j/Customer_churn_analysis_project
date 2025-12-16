Customer Churn Analysis

 
Project Overview

Customer churn is a critical challenge for subscription-based businesses, where retaining existing customers is significantly more cost-effective than acquiring new ones. This project performs an end-to-end customer churn analysis using SQL for structured querying and Python for exploratory data analysis and visualization. The goal is to identify key drivers of churn and generate actionable business insights to support decision-making.

Objectives

The main objectives of this project are:


Analyze customer churn behavior using historical customer data


Identify key factors influencing customer attrition


Measure churn rate across contract types, tenure groups, and billing patterns


Present insights through clear and interpretable visualizations



Dataset Description

The dataset contains 705 customer records, where each row represents a unique customer.
Key Features


CustomerID – Unique customer identifier


Gender – Male / Female


SeniorCitizen – Indicates senior citizen status


Partner & Dependents – Household details


Tenure – Number of months the customer has stayed


Contract – Month-to-month, One-year, Two-year


InternetService – DSL, Fiber optic, None


PaymentMethod – Mode of payment


MonthlyCharges – Monthly billing amount


TotalCharges – Cumulative charges


Churn (Target Variable) – Yes / No



Tools & Technologies Used


MySQL – Data storage, querying, aggregation


Python – Data analysis and visualization


Libraries


Pandas – Data manipulation


Matplotlib – Data visualization


Jupyter Notebook – Analysis environment



Methodology

Data Preparation


Imported CSV dataset into MySQL


Verified schema, column data types, and record counts


Checked for missing and inconsistent values


Standardized churn labels for accurate analysis


SQL-Based Analysis

SQL was used to compute churn metrics and identify high-risk customer segments:


Overall churn count and churn percentage


Gender-wise churn distribution


Contract-wise churn rate


Average monthly charges by churn status


Tenure-based churn analysis using CASE statements



SQL Analysis
-- Churn Distribution
SELECT Churn, COUNT(*) AS Total_Customers
FROM customer_churn
GROUP BY Churn;

-- Churn Percentage
SELECT 
    Churn,
    ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM customer_churn), 2) 
    AS Churn_Percentage
FROM customer_churn
GROUP BY Churn;

-- Contract-wise Churn Rate
SELECT 
    Contract,
    ROUND(
        SUM(CASE WHEN Churn = 'Yes' THEN 1 ELSE 0 END) * 100.0 / COUNT(*), 
        2
    ) AS Churn_Rate
FROM customer_churn
GROUP BY Contract;

-- Average Monthly Charges vs Churn
SELECT 
    Churn,
    ROUND(AVG(MonthlyCharges), 2) AS Avg_Monthly_Charges
FROM customer_churn
GROUP BY Churn;


Python Analysis & Visualization

Python was used for Exploratory Data Analysis (EDA) and visual storytelling.
Visualizations Created


Bar Chart – Churn distribution


Pie Chart – Churn percentage


Bar Chart – Contract type vs churn


Box Plot – Monthly charges vs churn


Line Chart – Tenure vs churn


These visualizations clearly highlight churn patterns and make insights accessible to non-technical stakeholders.
Key Findings & Insights


Customers on month-to-month contracts exhibit the highest churn rate


Short-tenure customers are more likely to churn


Higher monthly charges significantly increase churn probability


Long-term contracts (1-year, 2-year) improve customer retention


Contract type has a stronger impact on churn than gender


Business Impact

This analysis enables businesses to:


Identify high-risk customers early


Design targeted retention strategies


Encourage long-term contract adoption


Optimize pricing for high-charge customers


Improve overall Customer Lifetime Value (CLV)



Conclusion
This project demonstrates a complete analytical workflow by combining SQL for data querying and Python for data visualization. The insights generated help organizations understand customer churn behavior and take proactive steps to reduce customer attrition


Future Enhancements


Build a machine learning churn prediction model


Develop an interactive Power BI dashboard


Perform customer segmentation for personalized retention strategies


Incorporate behavioral and usage-level data for deeper insights


contact

JanetJames

Github:(https://github.com/janetjames-j/Customer_churn_analysis_project.git)
