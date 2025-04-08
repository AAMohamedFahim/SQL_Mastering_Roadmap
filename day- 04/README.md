# Day 4: Aggregate Functions

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. COUNT()](#1-count)
  - [2. SUM()](#2-sum)
  - [3. AVG()](#3-avg)
  - [4. MIN()](#4-min)
  - [5. MAX()](#5-max)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

## Overview
Day 4 introduces **aggregate functions**, which perform calculations on a set of values and return a single result. They're essential when you're summarizing or analyzing data.

### Objectives
- Use aggregate functions to calculate totals, averages, and other summaries.
- Understand how these functions work with filtering and grouping.

## Topics Covered
1. COUNT()
2. SUM()
3. AVG()
4. MIN()
5. MAX()

---

## 1. COUNT()
Returns the number of rows that match a condition or in total.

**Syntax:**
```sql
SELECT COUNT(column_name) FROM table_name;
```

**Example:**
```sql
SELECT COUNT(*) FROM employees;
```

---

## 2. SUM()
Returns the total sum of a numeric column.

**Example:**
```sql
SELECT SUM(salary) FROM employees;
```

---

## 3. AVG()
Returns the average value of a numeric column.

**Example:**
```sql
SELECT AVG(age) FROM users;
```

---

## 4. MIN()
Returns the smallest value in a column.

**Example:**
```sql
SELECT MIN(price) FROM products;
```

---

## 5. MAX()
Returns the largest value in a column.

**Example:**
```sql
SELECT MAX(rating) FROM reviews;
```

---

## Practice Exercises
1. Count the number of customers in the `customers` table.
2. Find the total revenue from the `orders` table.
3. Get the average delivery time from the `shipments` table.
4. Identify the minimum price of products in the `inventory`.
5. Find the highest rating in the `feedback` table.

---

## Next Steps
Move on to **Day 5** to learn about **grouping data** using `GROUP BY` and filtering grouped results with `HAVING`.
