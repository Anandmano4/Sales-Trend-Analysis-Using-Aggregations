# Sales-Trend-Analysis-Using-Aggregations

# Sales Trend Analysis using SQL

## Overview

This project is part of my internship task (Task 6) and focuses on analyzing sales trends using SQL aggregations. The objective is to extract insights such as monthly revenue, order volume, top customers, and popular shipping methods from the `SalesOrderHeader` table.

## Dataset

- **Database Used:** AdventureWorks2022 (Sample Sales Database)
- **Table Used:** `SalesLT.SalesOrderHeader`

## Key Objectives

- Analyze monthly revenue and order volume
- Identify top customers by revenue and number of orders
- Understand preferred shipping methods

## Tools Used

- SQL Server Management Studio (SSMS)
- SQL Queries (Standard SQL)

## Queries Performed

1. **Monthly Revenue and Order Volume**
2. **Top 5 Sales Orders**
3. **Total Revenue by Customer**
4. **Order Count by Customer**
5. **Order Count by Ship Method**

## Sample SQL Query

```sql
SELECT 
    YEAR(OrderDate) AS OrderYear,
    MONTH(OrderDate) AS OrderMonth,
    SUM(TotalDue) AS MonthlyRevenue,
    COUNT(DISTINCT SalesOrderID) AS OrderVolume
FROM 
    SalesLT.SalesOrderHeader
GROUP BY 
    YEAR(OrderDate), MONTH(OrderDate)
ORDER BY 
    OrderYear, OrderMonth;
