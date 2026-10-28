# Day 1: Meet the data

**Topic:** SELECT, columns, LIMIT  
**Case study:** [8 Week SQL Challenge, Case Study #1: Danny's Diner](https://8weeksqlchallenge.com/case-study-1/)  
**Completed:** 2026-10-28  
**Engine:** SQLite (the original case study uses PostgreSQL; queries are standard SQL unless noted)

## 1.1

Show every row and every column from the `menu` table.

```sql
-- Write your query here
SELECT * FROM menu;
```

| product_id | product_name | price |
| --- | --- | --- |
| 1 | sushi | 10 |
| 2 | curry | 15 |
| 3 | ramen | 12 |

Result: matches the expected answer.

## 1.2

Show only `product_name` and `price` from the menu.

```sql
-- Write your query here
SELECT product_name,price FROM menu;
```

| product_name | price |
| --- | --- |
| sushi | 10 |
| curry | 15 |
| ramen | 12 |

Result: matches the expected answer.

## 1.3

Show the `customer_id` and `join_date` of every loyalty member.

```sql
-- Write your query here
SELECT customer_id,join_date FROM members
```

| customer_id | join_date |
| --- | --- |
| A | 2021-01-07 |
| B | 2021-01-09 |

Result: matches the expected answer.

## 1.4

Show the first 5 rows of the `sales` table, all columns.

```sql
-- Write your query here
SELECT * FROM sales
LIMIT 5;
```

| customer_id | order_date | product_id |
| --- | --- | --- |
| A | 2021-01-01 | 1 |
| A | 2021-01-01 | 2 |
| A | 2021-01-07 | 2 |
| A | 2021-01-10 | 3 |
| A | 2021-01-11 | 3 |

Result: matches the expected answer.

## What I learned

Refresher for basics-select, limit and limiting columns and rows
