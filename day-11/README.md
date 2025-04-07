# Day 11: SQL Joins Deep Dive 🔄

## 🧭 Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Types of Joins](#types-of-joins)
  - [1. INNER JOIN](#1-inner-join)
  - [2. LEFT JOIN](#2-left-join)
  - [3. RIGHT JOIN](#3-right-join)
  - [4. FULL OUTER JOIN](#4-full-outer-join)
  - [5. CROSS JOIN](#5-cross-join)
  - [6. SELF JOIN](#6-self-join)
- [Visual Guide](#visual-guide)
- [Practice Scenarios](#practice-scenarios)
- [Next Up](#next-up)

---

## 📖 Overview
Joins combine rows from two or more tables based on related columns. They're the backbone of relational databases and key to data analysis.

---

## 🎯 Objectives
- Understand all types of SQL joins.
- Learn when to use each join type.
- Write join queries to answer real-world questions.

---

## 🔗 Types of Joins

### 1. INNER JOIN
Returns rows where there is a **match in both tables**.

```sql
SELECT *
FROM orders
INNER JOIN customers ON orders.customer_id = customers.id;
```

---

### 2. LEFT JOIN (or LEFT OUTER JOIN)
Returns **all rows from the left table** and matching rows from the right.

```sql
SELECT *
FROM customers
LEFT JOIN orders ON customers.id = orders.customer_id;
```

---

### 3. RIGHT JOIN (or RIGHT OUTER JOIN)
Returns **all rows from the right table** and matching rows from the left.

```sql
SELECT *
FROM orders
RIGHT JOIN customers ON orders.customer_id = customers.id;
```

---

### 4. FULL OUTER JOIN
Returns **all rows from both tables**, with NULLs where there’s no match.

```sql
SELECT *
FROM customers
FULL OUTER JOIN orders ON customers.id = orders.customer_id;
```

---

### 5. CROSS JOIN
Returns the **Cartesian product** – every row of A with every row of B.

```sql
SELECT *
FROM colors
CROSS JOIN sizes;
```

---

### 6. SELF JOIN
A table joined with itself – useful for hierarchical data.

```sql
SELECT A.name AS Employee, B.name AS Manager
FROM employees A
JOIN employees B ON A.manager_id = B.id;
```

---

## 🖼️ Visual Guide
```plaintext
Table A         Table B

A1              B1
A2              B2
A3              B3

INNER JOIN ➡️ Only matching rows (A2=B2)
LEFT JOIN  ➡️ All from A + matches from B (fill NULLs where no match)
RIGHT JOIN ➡️ All from B + matches from A
FULL JOIN  ➡️ Everything from both
```

---

## 🧪 Practice Scenarios
1. List all customers, even if they haven't placed any orders.
2. Show all orders, including those without matching customers (data issue).
3. Get a list of employees and their managers (self-join).
4. Generate a list of all product and category combinations (cross join).
5. Find customers who didn’t place any orders (use `LEFT JOIN` + `WHERE IS NULL`).

---

## 🔜 Next Up
On **Day 12**, you'll learn how to **create and modify tables** using `CREATE`, `ALTER`, and `DROP`. This will give you DDL (Data Definition Language) superpowers! 🧙

---
```markdown

Let me know if you’d like this formatted as a GitHub project README or in a ZIP with all previous days!
