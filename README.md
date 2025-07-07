# Elevate_Labs_Internship_Task-06

# Sales Trends Analysis Using Aggregations

-- Project: Data-Analyst-Internship-at-ElevateLabs-Task-6
-- Dataset Source: [Kaggle - sales_data.csv]
-- Cleaned Data: cleaned_sales_data.csv (from Task 1)
-- Now we use the cleaned_sales_data.csv to perform sales trends analysis using aggregation. Here is a brief overview of the process:

# Using the DB Browser for SQLite, create a new database.
-- Import the cleaned_sales_data.csv into the database as a table.
-- Perform SQL queries on the table.
-- Observe and note the output.
-- Save the queries in a SQL file.
-- SQL Queries and Outputs for Sales Trends Analysis using Aggregations
-- Monthly Revenue and Order Volume in 2015


-- =========================================
## Sales Trends Analysis using Aggregations
-- =========================================

## Monthly Revenue and Order Volume for 2015

-- Query:

```sql

SELECT 
    strftime('%Y', order_date) AS order_year, 
    strftime('%m', order_date) AS order_month, 
    SUM(sales) AS monthly_revenue, 
    COUNT(DISTINCT order_id) AS monthly_order_volume
FROM cleaned_sales_data
WHERE order_date BETWEEN '2015-01-01' AND '2015-12-31'
GROUP BY order_year, order_month
ORDER BY order_year, order_month;
```
-- Output:

## Monthly Revenue and Order Volume for 2016
Query:
```sql
SELECT
strftime('%Y', order_date) AS order_year,
strftime('%m', order_date) AS order_month,
SUM(sales) AS monthly_revenue,
COUNT(DISTINCT order_id) AS monthly_order_volume
FROM
cleaned_sales_data
WHERE
order_date BETWEEN "2016-01-01" AND "2016-12-31"
GROUP BY
order_year, order_month
ORDER BY
order_year, order_month;
```
-- Output:


## Monthly Revenue and Order Volume for 2017

-- Query:
```sql
SELECT
strftime('%Y', order_date) AS order_year,
strftime('%m', order_date) AS order_month,
SUM(sales) AS monthly_revenue,
COUNT(DISTINCT order_id) AS monthly_order_volume
FROM
cleaned_sales_data
WHERE
order_date BETWEEN "2017-01-01" AND "2017-12-31"
GROUP BY
order_year, order_month
ORDER BY
order_year, order_month;
```
-- Output:

## Monthly Revenue and Order volume in 2018
-- Query:
```sql
SELECT
strftime('%Y', order_date) AS order_year,
strftime('%m', order_date) AS order_month,
SUM(sales) AS monthly_revenue,
COUNT(DISTINCT order_id) AS monthly_order_volume
FROM
cleaned_sales_data
WHERE
order_date BETWEEN "2018-01-01" AND "2018-12-31"
GROUP BY
order_year, order_month
ORDER BY
order_year, order_month;
```

-- Output:


## Top 5 months with most revenue
-- Query:
```sql

SELECT
strftime('%Y', order_date) AS order_year,
strftime('%m', order_date) AS order_month,
SUM(sales) AS monthly_revenue,
COUNT(DISTINCT order_id) AS monthly_order_volume
FROM
cleaned_sales_data
GROUP BY
order_year, order_month
ORDER BY
monthly_revenue DESC
LIMIT 5;
```

-- Output:

## Year-wise revenue (2015 - 2018)
-- Query:
```sql
SELECT
strftime('%Y', order_date) AS order_year,
SUM(sales) AS yearly_revenue,
COUNT(DISTINCT order_id) AS yearly_order_volume
FROM
cleaned_sales_data
GROUP BY
order_year
ORDER BY
yearly_revenue DESC;
```
-- Output:

