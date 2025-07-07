# Elevate_Labs_Internship_Task-06

# Sales Trends Analysis Using Aggregations

**Dataset:** `cleaned_dataset.csv`  
**Data Cleaning and Preprocessing:** `Elevate-Labs-Internship-Task-6`  
**Cleaned Dataset:** `cleaned_dataset.csv`
Now we use the cleaned_sales_data.csv to perform sales trends analysis using aggregation. 

# Using the DB Browser for SQLite, create a new database.
- Import the cleaned_sales_data.csv into the database as a table.
- Perform SQL queries on the table.
- Observe and note the output.
- Save the queries in a SQL file.
- SQL Queries and Outputs for Sales Trends Analysis using Aggregations
- Monthly Revenue and Order Volume in 2015,2016,2017,2018.
- Top Months Revenue OF ALL YEARS.
- YEAR WISE REVENUE OF ALL YEAR.


-- =========================================
## Sales Trends Analysis using Aggregations
-- =========================================

## Monthly Revenue and Order Volume for 2015

**Query:**

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
**Output**
 
![J1](https://github.com/user-attachments/assets/2856d17d-3128-4b42-9534-3b67a3e6d9f8)


## Monthly Revenue and Order Volume for 2016
**Query:**

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
**Output:**


![J2](https://github.com/user-attachments/assets/0340ce29-92ef-4826-b11f-16eec9e0826b)

## Monthly Revenue and Order Volume for 2017

**Query:**

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
 **Output:**

![J3](https://github.com/user-attachments/assets/c6682ab7-27a5-418e-9d27-475632b77d80)


## Monthly Revenue and Order volume in 2018
**Query:**

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

**Output:**
![J4](https://github.com/user-attachments/assets/1acfdd25-dfd3-49b0-928b-dd47c009f81a)


## Top 5 months with most revenue
**Query:**

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

**Output:**

![J5](https://github.com/user-attachments/assets/7705cec1-da1b-4749-8541-bdfa19efce03)

## Year-wise revenue (2015 - 2018)

**Query:**

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
**Output:**


![J6](https://github.com/user-attachments/assets/defedf0a-d085-4937-a243-d94bdacab9da)
