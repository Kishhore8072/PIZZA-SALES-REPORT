# 🍕 Pizza Sales Analysis Project

An end-to-end data analysis project combining **Power BI visualization** and **MySQL queries** to extract business insights from pizza sales data. This dashboard helps businesses monitor KPIs, identify trends, and make data-driven decisions.

---
📷 Dashboard Preview

<img width="608" alt="Screenshot 2025-07-09 213446" src="https://github.com/user-attachments/assets/371af1ff-a72c-4114-87a9-e68789f6ffd1" />


<img width="607" alt="Screenshot 2025-07-09 213517" src="https://github.com/user-attachments/assets/3f909152-64c4-40bc-84c9-d5dd29247be1" />

## 📦 Project Contents

- `Pizza sales report.pbix` – Interactive Power BI dashboard
- `PIZZA SALES MySQL QUERIES.docx` – SQL queries used for KPI and trend analysis
- `README.md` – Project documentation
- `/images` – Dashboard screenshots (optional)

---

## 📊 Overview

The **Pizza Sales Dashboard** is a complete business intelligence solution that provides both **interactive visuals** and **backend query logic** to support restaurant management and sales strategy. The dataset includes order details, quantities, pizza types, categories, prices, and more.

This project is ideal for:
- BI Analysts looking to explore visual storytelling with Power BI
- SQL learners interested in practical business queries
- Restaurant owners/teams seeking sales performance metrics

---

## 💡 Key Business Questions Answered

- What is the total revenue, order volume, and average order value?
- Which days and months are most profitable?
- What are the top- and bottom-selling pizzas by quantity and revenue?
- How are sales distributed by pizza category and size?
- How many pizzas are sold per order on average?

---

## 🛠 Tools & Technologies

| Tool         | Purpose                                |
|--------------|----------------------------------------|
| Power BI     | Dashboard development & data visualization |
| MySQL        | Data extraction and transformation     |
| DAX          | Custom measures and KPIs in Power BI   |
| Excel/CSV    | Raw dataset (assumed source)           |

---

## 🧾 Key SQL Queries Used

Here are examples of KPIs and trend queries used in MySQL:

### 📌 KPIs

```sql
-- Total Revenue
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;
-- Average Order Value
SELECT SUM(total_price) / COUNT(DISTINCT order_id) AS Average_Order_Value FROM pizza_sales;
-- Total Orders
SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales;

🧾 Key SQL Queries Used
-- Daily Order Trend
SELECT DAYNAME(STR_TO_DATE(order_date, '%d-%m-%Y')) AS order_day, COUNT(DISTINCT order_id) AS total_orders
FROM pizza_sales
WHERE order_date IS NOT NULL
GROUP BY order_day
ORDER BY FIELD(order_day, 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday');

-- Monthly Trend
SELECT MONTHNAME(STR_TO_DATE(order_date, '%d-%m-%Y')) AS Month_Name, COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales
GROUP BY Month_Name;

🥇 Top Performers
-- Top 5 Pizzas by Revenue
SELECT pizza_name, SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue DESC
LIMIT 5;

-- Bottom 5 by Quantity
SELECT pizza_name, SUM(quantity) AS Total_Quantity_Sold
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Quantity_Sold ASC
LIMIT 5;



🚀 How to Run
Power BI Report
Open Pizza sales report.pbix in Power BI Desktop

Refresh data if needed

Interact with visuals for insight

SQL Analysis
Import pizza sales data into MySQL

Run the queries from PIZZA SALES MySQL QUERIES.docx

Analyze results and compare with dashboard

📌 Notes
The dataset is for educational purposes.
Data is assumed to be cleaned and normalized.
Designed for learning BI and SQL fundamentals in business contexts.

📬 Contact
Created by: Kishore S
LinkedIn: [linkedin.com/in/kishore-s-8a038a239](https://www.linkedin.com/in/kishore-s-8a038a239/)


 
