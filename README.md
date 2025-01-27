# Credit Card Consumption Analysis

## Overview

This project is designed to analyze and visualize customer spending behavior based on a dataset of transactions. The data includes information such as city, customer age, product type, spend amount, repayment amount, and transaction date. Through this analysis, we uncover valuable insights into customer spend patterns, repayment trends, and product preferences across different cities and demographics.

## Features

- **City-wise Spend Analysis**: Identify the city with the highest spend.
- **Age Group Spend Analysis**: Determine which age group contributes the most to total spend.
- **Top Repayment Customers**: List the top 10 customers based on repayment amounts.
- **Yearly Spend on Products**: Analyze spending on various product types year by year across cities.
- **Data Visualizations**: Visual representation of spend data across different variables.

## Dataset

The dataset contains the following columns:

- `Customer`: A unique identifier for each customer.
- `City`: The city where the transaction took place.
- `Age`: The age of the customer.
- `Type`: The product type purchased.
- `Spend_Amount`: The amount spent on the product.
- `Repayment_Amount`: The amount repaid by the customer.
- `Date`: The date of the transaction.

## Sample Analysis

### **City with Maximum Spend**

We calculate the city with the highest total spend using the following code:

```python
max_spend_city = final_tab.groupby('City').Spend_Amount.sum().sort_values(ascending=False).head(1)
