# 🗂️ SQL Case Studies – Northwind & Airline Databases  

## 📖 Project Overview  
This repository showcases **advanced SQL case studies** solving **real-world analytics problems** using two datasets:  
1. **Northwind Dataset** – Retail sales and operations data  
2. **Airline Dataset** – Flight performance and delay tracking data  

💡 **Goal:** Demonstrate SQL expertise in building optimized queries for **data analytics**, **business intelligence**, and **decision-making**.

Key SQL skills demonstrated:
- Window Functions (`RANK`, `DENSE_RANK`, `ROW_NUMBER`)  
- Common Table Expressions (**CTEs**)  
- Complex Joins & Subqueries  
- Data Cleaning & Transformation  
- Aggregations & Business Reporting  
- Query Optimization for performance  

---

## 🛠️ Tools & Technologies Used
- **SQL (PostgreSQL)** – Core query writing and data handling  
- **GitHub** – Portfolio hosting and version control  
- **Joins & Subqueries** – Integrating multiple relational tables  
- **Window Functions** – Dynamic ranking and trend calculations  

---

## 📊 Case Study 1 – Northwind Dataset *(Retail Analytics)*  
The **Northwind database** represents a retail company’s operations, with tables for **products, customers, orders, and regional performance**.

### **Business Questions Answered**
- Which **products and categories** generate the highest revenue?  
- Who are the **top customers** by sales and frequency of purchases?  
- What are the **monthly revenue and sales trends** across regions?  
- How to **rank stores and products dynamically** using window functions?

### **Key Actions**
- Connected multiple tables using **joins** for unified reporting.  
- Built **aggregations** to track total revenue, sales quantity, and order frequency.  
- Applied **window functions** for product and region-level ranking.  
- Conducted **time-series analysis** using `EXTRACT` and `DATE_TRUNC`.

**Sample Query – Ranking Products by Total Quantity Sold:**
```sql
SELECT 
    product_id, 
    SUM(orderquantity) AS total_quantity,
    RANK() OVER(ORDER BY SUM(orderquantity) DESC) AS sales_rank
FROM SALES
GROUP BY product_id;
---
## ✈️ Case Study 2 – Airline Dataset *(Operational Analytics)*  
The **Airline dataset** contains flight information, including **routes, delays, and airport performance**, providing a realistic scenario for analyzing operational efficiency.

---

### **Business Questions Answered**
- Which **airports have the lowest delay percentages**?  
- Which **routes experience the highest passenger traffic**?  
- How do **on-time vs delayed flight ratios** vary across airports?  
- What are the **monthly trends in flight delays**, and how can they be reduced?

---

### **Key Actions**
- Used **conditional aggregations** to calculate flight delay percentages.  
- Built performance summaries by **airport and route** using advanced SQL.  
- Ranked airports using `RANK()` and `DENSE_RANK()` to identify best and worst performers.  
- Generated actionable insights to improve **flight scheduling and operations**.

---

### **Sample Query – Delay Percentage by Airport**
```sql
SELECT 
    origin_airport, 
    COUNT(*) AS total_flights,
    ROUND(SUM(CASE WHEN delay > 0 THEN 1 ELSE 0 END) * 100.0 / COUNT(*), 2) AS delay_percentage
FROM FLIGHTS
GROUP BY origin_airport
ORDER BY delay_percentage ASC;




