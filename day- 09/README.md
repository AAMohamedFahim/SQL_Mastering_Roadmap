# Day 9: Common Table Expressions (CTEs) – WITH Clause

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. What is a CTE?](#1-what-is-a-cte)
  - [2. Syntax of a CTE](#2-syntax-of-a-cte)
  - [3. CTE vs Subquery](#3-cte-vs-subquery)
  - [4. Chaining Multiple CTEs](#4-chaining-multiple-ctes)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

---

## Overview
Day 9 introduces **Common Table Expressions (CTEs)** using the `WITH` clause. CTEs help break down complex queries into readable, modular parts and allow reuse of intermediate results.

---

## Objectives
- Understand what CTEs are and when to use them.
- Learn the syntax for writing single and multiple CTEs.
- Compare CTEs to subqueries in terms of readability and maintainability.
- Apply CTEs to write cleaner, more structured SQL code.

---

## Topics Covered

### 1. What is a CTE?
A **Common Table Expression** is a temporary result set defined within the execution scope of a `SELECT`, `INSERT`, `UPDATE`, or `DELETE` statement.

---

### 2. Syntax of a CTE

**Basic Syntax:**
```sql
WITH cte_name AS (
  SELECT column1, column2
  FROM table_name
  WHERE condition
)
SELECT *
FROM cte_name;
```

**Example:**
```sql
WITH HighSalary AS (
  SELECT name, salary
  FROM employees
  WHERE salary > 80000
)
SELECT *
FROM HighSalary
ORDER BY salary DESC;
```

---

### 3. CTE vs Subquery

| Feature           | CTE                        | Subquery               |
|------------------|----------------------------|------------------------|
| Readability       | High                       | Low (for nested logic) |
| Reusability       | Can be referenced multiple times | Limited                |
| Recursive Support | Yes (Recursive CTE)        | No                     |

---

### 4. Chaining Multiple CTEs

You can define multiple CTEs in one query:

```sql
WITH cte1 AS (
  SELECT * FROM table1
),
cte2 AS (
  SELECT * FROM cte1 WHERE condition
)
SELECT * FROM cte2;
```

This allows step-by-step logic building, similar to variable declarations in code.

---

## Practice Exercises
1. Write a CTE to find employees earning above the average salary.
2. Chain two CTEs to find departments with more than 5 employees and list them.
3. Use a CTE to simplify a query that involves multiple joins.
4. Rewrite a subquery-based SQL using a CTE.
5. Combine CTE with `ORDER BY` and `LIMIT` to get top-N results.

---

## Next Steps
On **Day 10**, you'll learn about **Window Functions** like `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `LEAD()`, and `LAG()` — perfect for advanced analytics and ranking use cases.

Get ready to slide through rows! 🪄
