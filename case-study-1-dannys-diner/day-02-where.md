# Day 2: Filter rows with WHERE

**Topic:** WHERE, AND, OR, IN  
**Case study:** [8 Week SQL Challenge, Case Study #1: Danny's Diner](https://8weeksqlchallenge.com/case-study-1/)  
**Completed:** 2026-10-28  
**Engine:** SQLite (the original case study uses PostgreSQL; queries are standard SQL unless noted)

## 2.1

Show all of customer B's purchases (all columns).

```sql
-- Write your query here
SELECT * FROM sales
WHERE customer_id='B'
```

| customer_id | order_date | product_id |
| --- | --- | --- |
| B | 2021-01-01 | 2 |
| B | 2021-01-02 | 2 |
| B | 2021-01-04 | 1 |
| B | 2021-01-11 | 1 |
| B | 2021-01-16 | 3 |
| B | 2021-02-01 | 3 |

Result: matches the expected answer.

## 2.2

Show the menu items that cost more than $10 (all columns).

```sql
-- Write your query here
SELECT * FROM menu
where price>10
```

| product_id | product_name | price |
| --- | --- | --- |
| 2 | curry | 15 |
| 3 | ramen | 12 |

Result: matches the expected answer.

## 2.3

Show every purchase made on `2021-01-01` (all columns).

```sql
-- Write your query here
SELECT * FROM sales
where order_date='2021-01-01'
```

| customer_id | order_date | product_id |
| --- | --- | --- |
| A | 2021-01-01 | 1 |
| A | 2021-01-01 | 2 |
| B | 2021-01-01 | 2 |
| C | 2021-01-01 | 3 |
| C | 2021-01-01 | 3 |

Result: matches the expected answer.

## 2.4

Show customer A's purchases from `2021-01-10` onward, including that day (all columns).

```sql
-- Write your query here
SELECT * FROM sales 
WHERE order_date>='2021-01-10' AND customer_id='A'
```

| customer_id | order_date | product_id |
| --- | --- | --- |
| A | 2021-01-10 | 3 |
| A | 2021-01-11 | 3 |
| A | 2021-01-11 | 3 |

Result: matches the expected answer.

## 2.5

Show every purchase of product 1 or product 3 using `IN` (all columns).

```sql
-- Write your query here

SELECT * FROM sales 
WHERE product_id IN (1,3)
```

| customer_id | order_date | product_id |
| --- | --- | --- |
| A | 2021-01-01 | 1 |
| A | 2021-01-10 | 3 |
| A | 2021-01-11 | 3 |
| A | 2021-01-11 | 3 |
| B | 2021-01-04 | 1 |
| B | 2021-01-11 | 1 |
| B | 2021-01-16 | 3 |
| B | 2021-02-01 | 3 |
| C | 2021-01-01 | 3 |
| C | 2021-01-01 | 3 |
| C | 2021-01-07 | 3 |

Result: matches the expected answer.

## What I learned

Learnt to filter data with logical operators.
WHERE filters rows before anything else happens. Quote text and dates, not numbers.
