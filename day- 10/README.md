# Day 10: Advanced SQL – Window Functions

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. What is a Window Function?](#1-what-is-a-window-function)
  - [2. Syntax](#2-syntax)
  - [3. Common Window Functions](#3-common-window-functions)
    - [ROW_NUMBER()](#row_number)
    - [RANK()](#rank)
    - [DENSE_RANK()](#dense_rank)
    - [NTILE()](#ntile)
    - [LEAD() & LAG()](#lead--lag)
    - [SUM(), AVG(), etc. with OVER()](#aggregate-functions-with-over)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

---

## Overview
Window functions let you perform **calculations across rows** that are related to the current row, **without collapsing results** like `GROUP BY`.

They’re great for **ranking**, **running totals**, **moving averages**, and **row comparisons**.

---

## Objectives
- Learn how to use `OVER()` with different clauses.
- Apply `ROW_NUMBER()`, `RANK()`, and `DENSE_RANK()` for ranking rows.
- Use `LEAD()` and `LAG()` for comparing rows.
- Perform rolling calculations like running totals.

---

## Topics Covered

### 1. What is a Window Function?
A window function performs a calculation **across a set of table rows** that are somehow related to the current row — this set is called the "window".

---

### 2. Syntax

```sql
SELECT
  column,
  function_name(...) OVER (
    PARTITION BY col1
    ORDER BY col2
    ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
  ) AS result
FROM table;
```

The `OVER()` clause defines the window.

---

### 3. Common Window Functions

#### `ROW_NUMBER()`
Assigns a unique number to each row within a partition.

```sql
ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC)
```

---

#### `RANK()`
Gives the same rank to ties, **with gaps**.

```sql
RANK() OVER (PARTITION BY department ORDER BY salary DESC)
```

---

#### `DENSE_RANK()`
Like `RANK()` but **without gaps**.

```sql
DENSE_RANK() OVER (PARTITION BY department ORDER BY salary DESC)
```

---

#### `NTILE(n)`
Divides rows into `n` buckets.

```sql
NTILE(4) OVER (ORDER BY salary)
```

---

#### `LEAD()` & `LAG()`
Access next or previous row.

```sql
LAG(salary, 1) OVER (PARTITION BY department ORDER BY salary)
LEAD(salary, 1) OVER (PARTITION BY department ORDER BY salary)
```

---

#### Aggregate functions with `OVER()`
Perform running totals, moving averages.

```sql
SUM(salary) OVER (PARTITION BY department ORDER BY employee_id)
AVG(score) OVER (ORDER BY test_date ROWS BETWEEN 2 PRECEDING AND CURRENT ROW)
```

---

## Practice Exercises
1. Use `ROW_NUMBER()` to pick the highest-paid employee in each department.
2. Use `RANK()` and `DENSE_RANK()` to compare their results.
3. Apply `NTILE(3)` to divide employees into 3 salary bands.
4. Use `LAG()` to compare this month's sales with last month.
5. Calculate a running total of purchases per customer.

---

## Next Steps
On **Day 11**, you'll get into **SQL Joins Deep Dive** — covering `INNER`, `LEFT`, `RIGHT`, `FULL`, `CROSS`, and practical use cases.

See you in the Joiniverse! 🌐
