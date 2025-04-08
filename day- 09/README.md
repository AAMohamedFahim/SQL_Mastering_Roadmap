# 📅 Day 9: Common Table Expressions (CTEs) – `WITH` Clause Mastery

## 🧭 Navigation
- [📌 Overview](#overview)
- [🎯 Objectives](#objectives)
- [📚 Topics Covered](#topics-covered)
  - [1. What is a CTE?](#1-what-is-a-cte)
  - [2. Syntax of a CTE](#2-syntax-of-a-cte)
  - [3. CTE vs Subquery](#3-cte-vs-subquery)
  - [4. Chaining Multiple CTEs](#4-chaining-multiple-ctes)
- [🧠 Practice Exercises](#practice-exercises)
- [🚀 Next Steps](#next-steps)

---

## 📌 Overview

Welcome to Day 9 of your SQL learning journey! Today, we dive into one of the **most powerful and elegant** tools in SQL — **Common Table Expressions (CTEs)**.

CTEs let you:
- Write modular and readable queries
- Avoid complex nested subqueries
- Reuse logic across multiple steps
- Even **write recursive queries** (advanced topic)

By the end of today, you’ll be writing cleaner SQL like a pro!

---

## 🎯 Objectives

By completing this module, you will:

- ✅ Understand what a Common Table Expression (CTE) is.
- ✅ Learn how to use the `WITH` clause to define a CTE.
- ✅ Compare CTEs to subqueries and know when to use each.
- ✅ Use **multiple chained CTEs** to break down complex logic.
- ✅ Get hands-on with practice problems to reinforce learning.

---

## 📚 Topics Covered

### 1. What is a CTE?

A **Common Table Expression (CTE)** is a **temporary, named result set** that you can reference within a SQL query. It makes your SQL **more readable**, especially when dealing with multi-step logic.

Think of a CTE like a named "helper query" that you define *before* your main query.

> 🔍 **Why use a CTE?**  
> - Improve readability  
> - Simplify debugging  
> - Modularize complex logic

---

### 2. Syntax of a CTE

The syntax starts with the `WITH` keyword, followed by the CTE name and the query inside parentheses.

#### 📌 Basic Syntax:
```sql
WITH cte_name AS (
  SELECT column1, column2
  FROM table_name
  WHERE condition
)
SELECT *
FROM cte_name;
```

#### 🧪 Example:
```sql
-- Define a CTE called HighSalary
WITH HighSalary AS (
  SELECT name, salary
  FROM employees
  WHERE salary > 80000
)
-- Use it like a table in the main query
SELECT *
FROM HighSalary
ORDER BY salary DESC;
```

---

### 3. CTE vs Subquery

Let’s compare CTEs to subqueries to understand when and why CTEs are preferred:

| Feature            | CTE                           | Subquery                   |
|-------------------|-------------------------------|----------------------------|
| ✅ Readability     | High (named, structured)       | Low (especially when nested) |
| 🔁 Reusability     | Can be referenced multiple times | Limited to one-time use    |
| 🔄 Recursive Support | Yes (with `RECURSIVE`)        | No                         |
| 📦 Structure        | Organized like a code block    | Buried inside query logic  |

---

### 4. Chaining Multiple CTEs

You can define **multiple CTEs in sequence**. Each one builds on the previous — similar to variables in programming.

#### 🧩 Example:
```sql
WITH employees_with_bonus AS (
  SELECT *, salary * 0.10 AS bonus
  FROM employees
),
high_earners AS (
  SELECT name, salary, bonus
  FROM employees_with_bonus
  WHERE salary > 90000
)
SELECT *
FROM high_earners;
```

> ✨ **Why chain CTEs?**  
> Break a long, complex query into manageable logical steps!

---

## 🧠 Practice Exercises

Try out these exercises to strengthen your understanding:

1. **Above Average**  
   Write a CTE to find employees earning above the average salary.

2. **Chain Reaction**  
   Use two CTEs:  
   - First to count employees per department  
   - Second to list departments with more than 5 employees.

3. **Simplify Joins**  
   Use a CTE to simplify a query involving multiple joins (e.g., employees, departments, locations).

4. **Subquery Makeover**  
   Take a query that uses a subquery and rewrite it using a CTE.

5. **Top-N Records**  
   Combine a CTE with `ORDER BY` and `LIMIT` to get the top 3 highest-paid employees.

> 💡 Pro Tip: Use CTEs even if you're writing for readability — not just complexity. Clean code is powerful code.

---

## 🚀 Next Steps

Tomorrow, on **Day 10**, we step into the **analytical side of SQL** — exploring **Window Functions** like:

- `ROW_NUMBER()`
- `RANK()` & `DENSE_RANK()`
- `LAG()` & `LEAD()`

These are especially useful for **rankings**, **comparisons across rows**, and **time-based analytics**.

> ✨ Stay curious — SQL is all about expressing logic clearly!
