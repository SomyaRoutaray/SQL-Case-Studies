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




