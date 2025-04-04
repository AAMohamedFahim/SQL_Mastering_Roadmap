# Day 1: Basic SQL Queries

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. SELECT Statement](#1-select-statement)
  - [2. FROM Clause](#2-from-clause)
  - [3. WHERE Clause](#3-where-clause)
  - [4. ORDER BY Clause](#4-order-by-clause)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

## Overview
Day 1 focuses on fundamental SQL queries, including `SELECT`, `FROM`, `WHERE`, and `ORDER BY`. These queries form the foundation for data retrieval and filtering from databases.

### Objectives
- Understand how to retrieve data from a database using `SELECT` and `FROM`.
- Apply filtering conditions with `WHERE`.
- Sort the result set using `ORDER BY`.

## Topics Covered
1. SELECT Statement
2. FROM Clause
3. WHERE Clause
4. ORDER BY Clause

## 1. SELECT Statement
The `SELECT` statement is used to fetch data from a database.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name;
```

**Example:**
```sql
SELECT name, age FROM employees;
```

## 2. FROM Clause
The `FROM` clause specifies the table from which to retrieve data.

**Example:**
```sql
SELECT * FROM customers;
```

## 3. WHERE Clause
The `WHERE` clause filters records based on specified conditions.

**Example:**
```sql
SELECT * FROM orders WHERE price > 100;
```

## 4. ORDER BY Clause
The `ORDER BY` clause sorts the result set in ascending or descending order.

**Example:**
```sql
SELECT name, age FROM employees ORDER BY age DESC;
```

## Practice Exercises
1. Retrieve the names of all products from the `products` table.
2. Get the names and prices of products costing more than $50.
3. List all customers, ordered by their registration date in ascending order.

## Next Steps
Move on to **Day 2** to learn about filtering data using `WHERE`, `BETWEEN`, `LIKE`, `IN`, and `IS NULL`.

