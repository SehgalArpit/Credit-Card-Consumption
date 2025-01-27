# Customer Spend Analysis

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

## Analysis Summary

### 1. **City with Maximum Spend**

We calculate the city with the highest total spend using the following code:

```python
max_spend_city = final_tab.groupby('City').Spend_Amount.sum().sort_values(ascending=False).head(1)

### 2. **Age Group with Maximum Spend**

Customers are grouped into the following age bins:

- 18-31
- 31-43
- 43-55
- 55-67
- 67-79

The analysis shows that the **43-55** age group spends the most, with a total spend of ₹80,737,505.37.

### 3. **Top 10 Customers in Terms of Repayment**

Top customers who repaid the most are:

```python
top_10_repayment_customers = final_tab.groupby('Customer').Repayment_Amount.sum().sort_values(ascending=False).head(10)

### **Visualizations**

Visualizations can be generated using libraries like `matplotlib` and `seaborn` to create insightful graphics. Below is an example of how to plot the yearly spend on **FOOD** products across different cities:

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Example: Plotting spend on 'FOOD' across cities by year
sns.lineplot(data=df8[df8['Type'] == 'FOOD'], x='Year', y='Spend_Amount', hue='City')
plt.title("Yearly Spend on Food Across Cities")
plt.xlabel('Year')
plt.ylabel('Spend Amount')
plt.show()

