# Day 3: Sort, dedupe and rename

**Topic:** ORDER BY, DISTINCT, AS  
**Case study:** [8 Week SQL Challenge, Case Study #1: Danny's Diner](https://8weeksqlchallenge.com/case-study-1/)  
**Completed:** 2026-10-28  
**Engine:** SQLite (the original case study uses PostgreSQL; queries are standard SQL unless noted)

## 3.1

Show the menu sorted from most to least expensive (all columns).

```sql
-- Write your query here
SELECT *
FROM menu
ORDER BY price DESC
```

| product_id | product_name | price |
| --- | --- | --- |
| 2 | curry | 15 |
| 3 | ramen | 12 |
| 1 | sushi | 10 |

Result: matches the expected answer.

## 3.2

List each customer who has made a purchase, once each. Return `customer_id`.

```sql
-- Write your query here
SELECT DISTINCT customer_id
FROM sales
ORDER BY customer_id, order_date;
```

| customer_id |
| --- |
| A |
| B |
| C |

Result: matches the expected answer.

## 3.3

List the distinct dates customer A visited, earliest first. Return `order_date`.

```sql
-- Write your query here
SELECT DISTINCT order_date
FROM sales
WHERE customer_id='A'
ORDER BY order_date;
```

| order_date |
| --- |
| 2021-01-01 |
| 2021-01-07 |
| 2021-01-10 |
| 2021-01-11 |

Result: matches the expected answer.

## 3.4

Return `customer_id`, `order_date`, `product_id` from sales, sorted by customer, then newest date first, then product_id smallest first.

```sql
-- Write your query here
SELECT customer_id, order_date, product_id
FROM sales
ORDER BY  customer_id,order_date DESC, product_id ASC;
```

| customer_id | order_date | product_id |
| --- | --- | --- |
| A | 2021-01-11 | 3 |
| A | 2021-01-11 | 3 |
| A | 2021-01-10 | 3 |
| A | 2021-01-07 | 2 |
| A | 2021-01-01 | 1 |
| A | 2021-01-01 | 2 |
| B | 2021-02-01 | 3 |
| B | 2021-01-16 | 3 |
| B | 2021-01-11 | 1 |
| B | 2021-01-04 | 1 |
| B | 2021-01-02 | 2 |
| B | 2021-01-01 | 2 |
| C | 2021-01-07 | 3 |
| C | 2021-01-01 | 3 |
| C | 2021-01-01 | 3 |

Result: matches the expected answer.

## 3.5

Show the menu with the columns renamed to `item` and `price_usd`.

```sql
-- Write your query here
SELECT product_name as item,price as price_usd
FROM menu
```

| item | price_usd |
| --- | --- |
| sushi | 10 |
| curry | 15 |
| ramen | 12 |

Result: matches the expected answer.

## What I learned

ORDER BY for order, DISTINCT for unique rows, AS for clear names.
