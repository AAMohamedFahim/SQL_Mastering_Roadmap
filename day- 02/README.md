# Day 2: Filtering Data

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. WHERE Clause](#1-where-clause)
  - [2. BETWEEN Operator](#2-between-operator)
  - [3. LIKE Operator](#3-like-operator)
  - [4. IN Operator](#4-in-operator)
  - [5. IS NULL](#5-is-null)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

## Overview
Day 2 focuses on filtering data using advanced SQL operators and clauses to narrow down result sets efficiently.

### Objectives
- Use the `WHERE` clause to filter data based on conditions.
- Apply `BETWEEN`, `LIKE`, `IN`, and `IS NULL` for more precise filtering.

## Topics Covered
1. WHERE Clause
2. BETWEEN Operator
3. LIKE Operator
4. IN Operator
5. IS NULL

## 1. WHERE Clause
The `WHERE` clause is used to specify a condition while fetching data.

**Syntax:**
```sql
SELECT column1, column2
FROM table_name
WHERE condition;
```

**Example:**
```sql
SELECT * FROM employees WHERE age > 30;
```

## 2. BETWEEN Operator
The `BETWEEN` operator is used to filter the result set within a specific range.

**Example:**
```sql
SELECT * FROM products WHERE price BETWEEN 50 AND 100;
```

## 3. LIKE Operator
The `LIKE` operator is used for pattern matching.

**Example:**
```sql
SELECT * FROM customers WHERE name LIKE 'A%';
```

| Condition              | Query        |
| ---------------------- | ------------ |
| Starts with `A`        | `LIKE 'A%'`  |
| Ends with `A`          | `LIKE '%A'`  |
| Contains `A` anywhere  | `LIKE '%A%'` |
| Exact Match (only `A`) | `= 'A'`      |


## 4. IN Operator
The `IN` operator is used to specify multiple possible values for a column.

**Example:**
```sql
SELECT * FROM orders WHERE status IN ('Pending', 'Shipped');
```

## 5. IS NULL
The `IS NULL` operator checks for null values.

**Example:**
```sql
SELECT * FROM users WHERE email IS NULL;
```

## Practice Exercises
1. Retrieve products priced between $20 and $50.
2. Find customers whose names start with 'S'.
3. List orders with a status of 'Delivered' or 'Cancelled'.
4. Select all users without a phone number.

## Next Steps
Move on to **Day 3** to learn about sorting and limiting data with `ORDER BY`, `LIMIT`, and `OFFSET`.

