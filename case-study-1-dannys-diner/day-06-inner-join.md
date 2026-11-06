# Day 6: Join two tables

**Topic:** INNER JOIN  
**Case study:** [8 Week SQL Challenge, Case Study #1: Danny's Diner](https://8weeksqlchallenge.com/case-study-1/)  
**Completed:** 2026-11-06  
**Engine:** SQLite (the original case study uses PostgreSQL; queries are standard SQL unless noted)

Case study questions answered today: Q1

## 6.1

Show each sale with its product name. Return `customer_id`, `order_date`, `product_name`.

```sql
-- Write your query here
Select s.order_date,m.product_name,s.customer_id
from menu as m
join sales as s
on  s.product_id=m.product_id
```

| order_date | product_name | customer_id |
| --- | --- | --- |
| 2021-01-01 | sushi | A |
| 2021-01-04 | sushi | B |
| 2021-01-11 | sushi | B |
| 2021-01-01 | curry | A |
| 2021-01-07 | curry | A |
| 2021-01-01 | curry | B |
| 2021-01-02 | curry | B |
| 2021-01-10 | ramen | A |
| 2021-01-11 | ramen | A |
| 2021-01-11 | ramen | A |
| 2021-01-16 | ramen | B |
| 2021-02-01 | ramen | B |
| 2021-01-01 | ramen | C |
| 2021-01-01 | ramen | C |
| 2021-01-07 | ramen | C |

Result: matches the expected answer.

## 6.2

Show each sale's price. Return `customer_id`, `product_name`, `price`.

```sql
-- Write your query here
Select s.customer_id, m.product_name,m.price
from menu as m
join sales as s
on s.product_id=m.product_id
```

| customer_id | product_name | price |
| --- | --- | --- |
| A | sushi | 10 |
| B | sushi | 10 |
| B | sushi | 10 |
| A | curry | 15 |
| A | curry | 15 |
| B | curry | 15 |
| B | curry | 15 |
| A | ramen | 12 |
| A | ramen | 12 |
| A | ramen | 12 |
| B | ramen | 12 |
| B | ramen | 12 |
| C | ramen | 12 |
| C | ramen | 12 |
| C | ramen | 12 |

Result: matches the expected answer.

## 6.3 (Q1)

**Case study Q1.** What is the total amount each customer spent? Return `customer_id` and `total_spent`.

```sql
-- Write your query here
select s.customer_id, sum(m.price) as total_spent
from menu as m
join sales as s
on s.product_id=m.product_id
group by customer_id
```

| customer_id | total_spent |
| --- | --- |
| A | 76 |
| B | 74 |
| C | 36 |

Result: matches the expected answer.

## 6.4

How much revenue did each menu item bring in? Return `product_name` and `revenue`.

```sql
-- Write your query here
select m.product_name,sum(m.price) as revenue
from menu as m
join sales as s
 on s.product_id=m.product_id
group by m.product_name
```

| product_name | revenue |
| --- | --- |
| curry | 60 |
| ramen | 96 |
| sushi | 30 |

Result: matches the expected answer.

## What I learned

Insights to understand trends and get wholistic picture of the business and using Join with other operations
