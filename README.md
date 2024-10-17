# LITA_PROJECT
## Project 1: Sales Performance Analysis for a Retail Store 
---

### SUMMARY: 
In this project, your objective is to analyze the sales performance of a retail store. You will investigate the sales data to identify important insights, including top-selling products, regional performance, and monthly sales patterns. The final goal is to create an interactive Power BI dashboard that visually presents these findings.

**Instructions:**

1. **Excel:**

   ![EXCEL SALES](https://github.com/user-attachments/assets/ea5fa5be-203a-4dab-89f5-24ce58acb54c)

    - Start by exploring the sales data. Use pivot tables to summarize total sales by product, region, and month.
   - Apply Excel formulas to calculate key metrics like average sales per product and total revenue by region.
   - Generate additional reports or insights that might be useful.
     
     ### 2.	SQL: 
Hint – You need to load the dataset into your SQL Server environment to write and validate your queries. 

Write queries to extract key insights based on the following questions.  
o	retrieve the total sales for each product category. 
```
SELECT Product, SUM(Quantity * UnitPrice) AS TotalSales
FROM LITACapstoneDatasetCSV
GROUP BY Product;
```
![SQL SALES 1](https://github.com/user-attachments/assets/c56aa9a8-a6f9-4bb5-97f2-2e8c39e2a0ea)

o find the number of sales transactions in each region. o find the highest-selling product by total sales value. 
o	calculate total revenue per product. o calculate monthly sales totals for the current year. o find the top 5 customers by total purchase amount. 
o	calculate the percentage of total sales contributed by each region. o identify products with no sales in the last quarter. 


     
