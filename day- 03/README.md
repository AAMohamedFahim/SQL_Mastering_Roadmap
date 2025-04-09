# Day 3: Sorting & Limiting Data

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. ORDER BY Clause](#1-order-by-clause)
  - [2. Sorting by Multiple Columns](#2-sorting-by-multiple-columns)
  - [3. LIMIT Clause](#3-limit-clause)
  - [4. OFFSET Clause](#4-offset-clause)
  - [5. Pagination with LIMIT and OFFSET](#5-pagination-with-limit-and-offset)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

## Overview
Day 3 focuses on how to **sort** and **limit** SQL query results to improve data readability and performance.

### Objectives
- Sort data using `ORDER BY` in ascending or descending order.
- Apply `LIMIT` to control the number of rows returned.
- Use `OFFSET` to skip rows.
- Implement basic pagination using `LIMIT` and `OFFSET`.

## Topics Covered
1. ORDER BY Clause  
2. Sorting by Multiple Columns  
3. LIMIT Clause  
4. OFFSET Clause  
5. Pagination with LIMIT and OFFSET

## 1. ORDER BY Clause
The `ORDER BY` clause is used to sort the result set based on one or more columns.

**Syntax:**
```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 ASC|DESC;
```

**Example:**
```sql
SELECT * FROM employees
ORDER BY salary DESC;
```

## 2. Sorting by Multiple Columns
You can sort by multiple columns to further refine the result ordering.

**Example 1:**  
Sort students first by grade in descending order, and then by name in ascending order.
```sql
SELECT * FROM students
ORDER BY grade DESC, name ASC;
```

**Example 2:**  
Sort results by `percentage` in descending order and then by `contest_id` in ascending order.
```sql
SELECT * FROM results
ORDER BY percentage DESC, contest_id ASC;
```

## 3. LIMIT Clause
The `LIMIT` clause restricts the number of rows returned.

**Example:**
```sql
SELECT * FROM products
ORDER BY price ASC
LIMIT 5;
```

## 4. OFFSET Clause
The `OFFSET` clause skips a specified number of rows before starting to return rows.

**Example:**
```sql
SELECT * FROM orders
ORDER BY order_date DESC
LIMIT 10 OFFSET 5;
```

## 5. Pagination with LIMIT and OFFSET
Use `LIMIT` and `OFFSET` together for pagination.

**Example:**
```sql
-- Page 2 with 10 results per page
SELECT * FROM books
ORDER BY title
LIMIT 10 OFFSET 10;
```

## Practice Exercises
1. Retrieve the top 10 highest-paid employees.
2. Find the 5 most recent customer signups.
3. List 10 products ordered by price, skipping the first 5.
4. Display orders sorted by status and date, showing only 7 results.

## Next Steps
Move on to **Day 4** to learn about **Aggregate Functions** such as `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()` to perform calculations on your data.
