# Day 7: Keep unmatched rows

**Topic:** LEFT JOIN, NULL  
**Case study:** [8 Week SQL Challenge, Case Study #1: Danny's Diner](https://8weeksqlchallenge.com/case-study-1/)  
**Completed:** 2026-11-06  
**Engine:** SQLite (the original case study uses PostgreSQL; queries are standard SQL unless noted)

## 7.1

Show every sale with the customer's join date (blank for non-members). Return `customer_id`, `order_date`, `join_date`. You should get 15 rows.

```sql
-- Write your query here
Select s.customer_id,s.order_date,mb.join_date
from sales as s
Left join members as mb
on s.customer_id=mb.customer_id
```

| customer_id | order_date | join_date |
| --- | --- | --- |
| A | 2021-01-01 | 2021-01-07 |
| A | 2021-01-01 | 2021-01-07 |
| A | 2021-01-07 | 2021-01-07 |
| A | 2021-01-10 | 2021-01-07 |
| A | 2021-01-11 | 2021-01-07 |
| A | 2021-01-11 | 2021-01-07 |
| B | 2021-01-01 | 2021-01-09 |
| B | 2021-01-02 | 2021-01-09 |
| B | 2021-01-04 | 2021-01-09 |
| B | 2021-01-11 | 2021-01-09 |
| B | 2021-01-16 | 2021-01-09 |
| B | 2021-02-01 | 2021-01-09 |
| C | 2021-01-01 | NULL |
| C | 2021-01-01 | NULL |
| C | 2021-01-07 | NULL |

Result: matches the expected answer.

## 7.2

Which customers bought something but are not members? Return `customer_id`, once each.

```sql
-- Write your query here
Select DISTINCT s.customer_id
from sales as s
left join members as mb on s.customer_id=mb.customer_id
where mb.join_date IS NULL
```

| customer_id |
| --- |
| C |

Result: matches the expected answer.

## 7.3

For each customer, show their join date and number of purchases. Return `customer_id`, `join_date`, `purchase_count`.

```sql
-- Write your query here
SELECT s.customer_id,mb.join_date,COUNT(*) as purchase_count
FROM sales as s
LEFT JOIN members as mb ON s.customer_id=mb.customer_id
GROUP BY s.customer_id,mb.join_date
```

| customer_id | join_date | purchase_count |
| --- | --- | --- |
| A | 2021-01-07 | 6 |
| B | 2021-01-09 | 6 |
| C | NULL | 3 |

Result: matches the expected answer.

## What I learned

LEFT JOIN keeps all left rows. Missing matches show as NULL.
Use group by, Distinct, count to aggregate further
