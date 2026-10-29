# Day 5: Group results

**Topic:** GROUP BY, HAVING  
**Case study:** [8 Week SQL Challenge, Case Study #1: Danny's Diner](https://8weeksqlchallenge.com/case-study-1/)  
**Completed:** 2026-10-28  
**Engine:** SQLite (the original case study uses PostgreSQL; queries are standard SQL unless noted)

Case study questions answered today: Q2

## 5.1

Count purchases per customer. Return `customer_id` and the count.

```sql
-- Write your query here
select customer_id as Customer,COUNT(customer_id) as Total_purchases
from sales
group by customer_id
```

| Customer | Total_purchases |
| --- | --- |
| A | 6 |
| B | 6 |
| C | 3 |

Result: matches the expected answer.

## 5.2

Count how many times each `product_id` was ordered. Return product_id and the count.

```sql
-- How many times each product was ordered?
SELECT product_id as product,COUNT(product_id) as times_ordered
from sales
group by product_id
order by product
```

| product | times_ordered |
| --- | --- |
| 1 | 3 |
| 2 | 4 |
| 3 | 8 |

Result: matches the expected answer.

## 5.3

Which customers made more than 5 purchases? Return `customer_id` and the count.

```sql
-- Write your query here
SELECT customer_id,count(*) AS purchase_count
FROM sales
GROUP BY customer_id
HAVING COUNT(*)>5
```

| customer_id | purchase_count |
| --- | --- |
| A | 6 |
| B | 6 |

Result: matches the expected answer.

## 5.4 (Q2)

**Case study Q2.** How many days has each customer visited the restaurant? Return `customer_id` and `visit_days`.

```sql
-- Write your query here
select customer_id AS customer,COUNT(DISTINCT order_date) as visit_days
from sales
group by customer_id
```

| customer | visit_days |
| --- | --- |
| A | 4 |
| B | 6 |
| C | 2 |

Result: matches the expected answer.

## What I learned

WHERE filters rows before grouping. HAVING filters groups after the aggregates are calculated
Every column in SELECT must either be in GROUP BY or be inside an aggregate function.
