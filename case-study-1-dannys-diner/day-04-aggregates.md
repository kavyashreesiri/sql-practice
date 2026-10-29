# Day 4: Count, sum and average

**Topic:** COUNT, SUM, MIN, MAX, AVG  
**Case study:** [8 Week SQL Challenge, Case Study #1: Danny's Diner](https://8weeksqlchallenge.com/case-study-1/)  
**Completed:** 2026-10-28  
**Engine:** SQLite (the original case study uses PostgreSQL; queries are standard SQL unless noted)

## 4.1

How many purchases are in the sales table? Return one number.

```sql
-- Write your query here
SELECT COUNT(*) 
FROM sales;
```

| COUNT(*) |
| --- |
| 15 |

Result: matches the expected answer.

## 4.2

What are the earliest and latest order dates? Return two columns: earliest, then latest.

```sql
-- Write your query here
SELECT min(order_date), max(order_date)
FROM sales;
```

| min(order_date) | max(order_date) |
| --- | --- |
| 2021-01-01 | 2021-02-01 |

Result: matches the expected answer.

## 4.3

What is the average menu price, rounded to 2 decimals?

```sql
-- Write your query here
SELECT ROUND(AVG(price), 2) AS avg_price
FROM menu;
```

| avg_price |
| --- |
| 12.33 |

Result: matches the expected answer.

## 4.4

On how many different days did customer C visit?

```sql
-- Write your query here
SELECT COUNT(DISTINCT order_date) AS visit_days
FROM sales
WHERE customer_id='C'
```

| visit_days |
| --- |
| 2 |

Result: matches the expected answer.

## What I learned
Day 4: COUNT, SUM, MIN, MAX, AVG (Danny's Diner)
Aggregates turn many rows into one. COUNT(DISTINCT) counts unique values.

Average menu price, scope for increasing or decreasing menu item price.
