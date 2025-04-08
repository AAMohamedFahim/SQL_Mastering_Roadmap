# 📅 Day 10: Advanced SQL – Window Functions

> ✅ *If you're learning Window Functions — this is your one-stop guide. No need to refer to any other resource. It's all here — explained, simplified, and supported with examples and practice problems.*

---

## 🧭 Navigation
- [📌 Overview](#overview)
- [🎯 Objectives](#objectives)
- [📚 Topics Covered](#topics-covered)
  - [1. What is a Window Function?](#1-what-is-a-window-function)
  - [2. Syntax](#2-syntax)
  - [3. Example Table](#3-example-table)
  - [4. Common Window Functions](#4-common-window-functions)
    - [ROW_NUMBER()](#row_number)
    - [RANK()](#rank)
    - [DENSE_RANK()](#dense_rank)
    - [NTILE()](#ntile)
    - [LEAD() & LAG()](#lead--lag)
    - [Aggregate Functions with OVER()](#aggregate-functions-with-over)
- [🧠 Practice Exercises](#practice-exercises)
- [🚀 Next Steps](#next-steps)

---

## 📌 Overview

**Window Functions** allow you to perform calculations across rows that are **related to the current row** — but **without collapsing rows** like `GROUP BY` does.

They are essential when working with:
- Rankings (1st, 2nd, 3rd, …)
- Running totals
- Moving averages
- Value comparisons between rows

---

## 🎯 Objectives

By completing this module, you will:

- ✅ Understand how the `OVER()` clause works.
- ✅ Apply ranking functions like `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`.
- ✅ Use `LAG()` and `LEAD()` to compare current vs previous/next rows.
- ✅ Perform running totals and moving averages using aggregate window functions.

---

## 📚 Topics Covered

---

### 1. What is a Window Function?

A **Window Function** performs a calculation across a **set of table rows** related to the current row, defined by a window. Unlike `GROUP BY`, it **retains all individual rows** while adding extra calculated fields.

> 💡 Think of it as “GROUP BY + analytics — without collapsing your data.”

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

- `PARTITION BY` divides the data into groups (like GROUP BY)
- `ORDER BY` orders rows within each partition
- `ROWS BETWEEN` defines the frame (optional, advanced)

---

### 3. Example Table

Let’s use this sample `employees` table:

| employee_id | name     | department | salary |
|-------------|----------|------------|--------|
| 1           | Alice    | HR         | 60,000 |
| 2           | Bob      | IT         | 80,000 |
| 3           | Charlie  | IT         | 95,000 |
| 4           | Diana    | HR         | 75,000 |
| 5           | Evan     | IT         | 70,000 |
| 6           | Fiona    | HR         | 85,000 |

---

### 4. Common Window Functions

---

#### 🆔 `ROW_NUMBER()`

Assigns a unique number to each row **within a partition** based on the order.

```sql
SELECT name, department, salary,
  ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) AS row_num
FROM employees;
```

| name   | department | salary | row_num |
|--------|------------|--------|---------|
| Fiona  | HR         | 85,000 | 1       |
| Diana  | HR         | 75,000 | 2       |
| Alice  | HR         | 60,000 | 3       |
| Charlie| IT         | 95,000 | 1       |
| Bob    | IT         | 80,000 | 2       |
| Evan   | IT         | 70,000 | 3       |

---

#### 🏆 `RANK()`

Ranks rows within a partition — **gives same rank for ties**, with gaps.

```sql
SELECT name, department, salary,
  RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS rank
FROM employees;
```

---

#### 🥇 `DENSE_RANK()`

Like `RANK()`, but **no gaps** between tied ranks.

```sql
SELECT name, department, salary,
  DENSE_RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS dense_rank
FROM employees;
```

---

#### 🎲 `NTILE(n)`

Distributes rows into `n` **equal groups**.

```sql
SELECT name, salary,
  NTILE(3) OVER (ORDER BY salary DESC) AS bucket
FROM employees;
```

---

#### ⏪ `LAG()` & ⏩ `LEAD()`

Compare with previous or next row.

```sql
SELECT name, salary,
  LAG(salary, 1) OVER (ORDER BY salary) AS prev_salary,
  LEAD(salary, 1) OVER (ORDER BY salary) AS next_salary
FROM employees;
```

| name   | salary | prev_salary | next_salary |
|--------|--------|-------------|-------------|
| Alice  | 60000  | NULL        | 70000       |
| Evan   | 70000  | 60000       | 75000       |
| Diana  | 75000  | 70000       | 80000       |
| Bob    | 80000  | 75000       | 85000       |
| Fiona  | 85000  | 80000       | 95000       |
| Charlie| 95000  | 85000       | NULL        |

---

#### 📊 Aggregate Functions with `OVER()`

You can use window versions of `SUM()`, `AVG()`, `COUNT()` and more.

```sql
SELECT name, department, salary,
  SUM(salary) OVER (PARTITION BY department ORDER BY salary) AS dept_running_total
FROM employees;
```

This gives a **running total of salary per department**.

---

## 🧠 Practice Exercises

Try solving these on your own!

1. ✅ Use `ROW_NUMBER()` to find the highest-paid employee in each department.
2. 🎯 Compare `RANK()` vs `DENSE_RANK()` when salaries are tied.
3. 📦 Divide employees into 3 groups using `NTILE(3)`.
4. 🔄 Use `LAG()` to find the change in salary from the previous employee.
5. 💰 Show a running total of salary for the entire company and for each department.

> 🧠 Bonus: Combine multiple window functions in one query!

---

## Next Steps
On **Day 11**, you’ll dive into **SQL String Functions** — mastering `UPPER()`, `LOWER()`, `CONCAT()`, `SUBSTRING()`, `TRIM()` and more.

Get ready to manipulate text like a pro in SQL! 🔤
---

🏁 **Done with Day 10?**  
If this guide helped you, give the repo a ⭐ and share it with a friend who wants to master SQL!

