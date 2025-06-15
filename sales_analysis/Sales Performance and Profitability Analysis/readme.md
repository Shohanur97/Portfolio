# 📊 Sales and Profitability Analysis

A data-driven project that analyzes sales performance and profitability using SQL, Excel, and Power BI. The project aims to uncover insights across products, customer segments, and regions, helping businesses make informed decisions.

---

## 🧠 Business Problem Statement

> The company seeks to evaluate and optimize its sales and profitability by analyzing transactional sales data. While revenue is growing, inconsistent profit margins across products, segments, and regions are impacting strategy. This project aims to identify profitable vs. unprofitable products, evaluate discount impacts, and provide actionable insights for better pricing, marketing, and operations.

---

## 🛠️ Tools & Technologies

- **Excel** – For data cleaning and preprocessing  
- **SQL** – For data querying and analysis  
- **Power BI** – For interactive dashboards and data visualization

---
![Interactive Dashboard](https://github.com/Shohanur97/Portfolio/blob/main/sales_analysis/Sales%20Performance%20and%20Profitability%20Analysis/Sales_analysis.png)

## 📂 Dataset

- **File:** [`Sales_Analysis_Dataset.csv`](https://github.com/Shohanur97/Portfolio/blob/main/sales_analysis/Sales%20Performance%20and%20Profitability%20Analysis/Sales.csv)
- Contains:  
  - Order details (ID, Date, Quantity)  
  - Sales and profit data  
  - Product and customer segment information  
  - Regional and discount metrics

---

## 📌 Key Areas of Analysis

1. **Descriptive Analysis** – Overall sales, order count, and profit trends  
2. **Product Analysis** – Best and worst-performing products and sub-categories  
3. **Segment Analysis** – Customer segment profitability  
4. **Regional Analysis** – Region-wise sales and profit performance  
5. **Profitability Analysis** – Impact of discounts on profit margins  

---

## 🧮 Sample SQL Queries

Here are some SQL queries used for initial analysis:

```sql
-- Total Sales, Profit, Quantity
SELECT SUM(Sales), SUM(Profit), SUM(Quantity)
FROM sales_data;

-- Most Profitable Sub-Categories
SELECT SubCategory, SUM(Profit) AS Profit
FROM sales_data
GROUP BY SubCategory
ORDER BY Profit DESC
LIMIT 5;

