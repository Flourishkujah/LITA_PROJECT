# LITA_PROJECT
# Project 1: Sales Performance Analysis for a Retail Store 
---

## SUMMARY: 
In this project, your objective is to analyze the sales performance of a retail store. You will investigate the sales data to identify important insights, including top-selling products, regional performance, and monthly sales patterns. The final goal is to create an interactive Power BI dashboard that visually presents these findings.

**Instructions:**

## 1. **Excel:**

   ![EXCEL SALES](https://github.com/user-attachments/assets/ea5fa5be-203a-4dab-89f5-24ce58acb54c)

    - Start by exploring the sales data. Use pivot tables to summarize total sales by product, region, and month.
    
   ![image](https://github.com/user-attachments/assets/c0faaa48-7a07-4a3a-b595-c07b2214bab8)

   
   - Apply Excel formulas to calculate key metrics like average sales per product and total revenue by region.

     Average sales per product
     
![EXCEL SALES PIVOT 2](https://github.com/user-attachments/assets/60a7abdc-c04d-498c-ba1e-4ae34e95e528)

Total revenue by region

![image](https://github.com/user-attachments/assets/8fd28ea0-6e17-4a15-9e0e-910e03634b6b)


   - Generate additional reports or insights that might be useful.
     ![EXCEL SALES PIVOT 3](https://github.com/user-attachments/assets/63d9fe4f-ab39-40ee-9f9f-3998f56e1f93)

    
     ## 2.	SQL: 

![image](https://github.com/user-attachments/assets/91496297-77d4-4956-82d8-6058234bee82)


### Write queries to extract key insights based on the following questions.  

o	retrieve the total sales for each product category. 
```
SELECT Product, SUM(Quantity * UnitPrice) AS TotalSales
FROM LITACapstoneDatasetCSV
GROUP BY Product;
```
![SQL SALES 1](https://github.com/user-attachments/assets/c56aa9a8-a6f9-4bb5-97f2-2e8c39e2a0ea)

o find the number of sales transactions in each region. 

```
SELECT Region, COUNT(OrderID) AS NumberOfTransactions
FROM LITACapstoneDatasetCSV
GROUP BY Region;
```
![image](https://github.com/user-attachments/assets/d2255a7c-7997-4682-bab5-f8be9d843486)

o find the highest-selling product by total sales value. 

```
SELECT TOP 1 Product, SUM(Quantity * UnitPrice) AS TotalSales
FROM LITACapstoneDatasetCSV
GROUP BY Product
ORDER BY TotalSales DESC;
```
![image](https://github.com/user-attachments/assets/9ba4df3d-2c09-4168-ab1b-22e83c3c296a)


o	calculate total revenue per product. 

```
SELECT Product, SUM(Sales) AS TotalRevenue
FROM LITACapstoneDatasetCSV
GROUP BY Product;
```
![image](https://github.com/user-attachments/assets/11fb98e8-90dc-4429-86c8-5b9268f1102b)


o calculate monthly sales totals for the current year.

```
SELECT DATENAME(MONTH, OrderDate) AS MonthName, SUM(Sales) AS MonthlySalesTotal
FROM LITACapstoneDatasetCSV
WHERE YEAR(OrderDate) = YEAR(GETDATE())  -- For the current year
GROUP BY MONTH(OrderDate), DATENAME(MONTH, OrderDate)
ORDER BY MONTH(OrderDate);
```
![image](https://github.com/user-attachments/assets/c787c70b-f8ff-4554-8c58-3f3d42e9c360)

o find the top 5 customers by total purchase amount. 

```
SELECT TOP 5 Customer_Id, sum(Sales) AS Totalpurchaseamount
FROM LITACapstoneDatasetCSV
GROUP BY Customer_Id
ORDER BY Totalpurchaseamount Desc;
```
![image](https://github.com/user-attachments/assets/df29cd2c-7c3c-434d-a69b-0eb9900eee35)

o	calculate the percentage of total sales contributed by each region. 

```
SELECT Region, 
       sum(Sales) AS RegionSales, 
       (sum(Sales) * 100.0) / (SELECT sum(Sales) FROM LITACapstoneDatasetCSV) AS PercentageContribution
FROM LITACapstoneDatasetCSV
GROUP BY Region
ORDER BY PercentageContribution Asc;
```

o identify products with no sales in the last quarter. 

```
SELECT DISTINCT Product
FROM LITACapstoneDatasetCSV
WHERE Product NOT IN (
    SELECT Product
    FROM LITACapstoneDatasetCSV
    WHERE OrderDate >= DATEADD(QUARTER, -1, GETDATE()) 
)
```
![image](https://github.com/user-attachments/assets/6da1159e-c485-4cad-8a6b-3d4e4b8cf818)


## 3.	Power BI: 
o	Create a dashboard that visualizes the insights found in Excel and SQL. 

![image](https://github.com/user-attachments/assets/2d492d81-28e0-4495-bb5b-d44dd5966d3e)





The dashboard should include a sales overview, top-performing products, and regional breakdowns. 

![image](https://github.com/user-attachments/assets/95e70dee-c3eb-4edf-9bbd-a5e3f24e1217)



     
