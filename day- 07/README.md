# Day 7: Joins – INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. What are Joins?](#1-what-are-joins)
  - [2. INNER JOIN](#2-inner-join)
  - [3. LEFT JOIN](#3-left-join)
  - [4. RIGHT JOIN](#4-right-join)
  - [5. FULL JOIN](#5-full-join)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

## Overview
Day 7 dives into **SQL Joins**, which are used to combine rows from two or more tables based on a related column. Understanding joins is crucial for working with relational databases effectively.

### Objectives
- Learn how to combine data from multiple tables using different types of joins.
- Understand the differences between `INNER`, `LEFT`, `RIGHT`, and `FULL` joins.
- Apply joins to extract meaningful insights from relational data.

## Topics Covered
1. What are Joins?  
2. INNER JOIN  
3. LEFT JOIN  
4. RIGHT JOIN  
5. FULL JOIN

| Join Type                         | Purpose                                                                     | Example Scenario                                  |
| --------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------- |
| **INNER JOIN**                    | Returns only matching rows from both tables                                 | Customers with Orders                             |
| **LEFT JOIN (LEFT OUTER JOIN)**   | Returns all rows from left table + matching rows from right                 | All Customers even if they have no Orders         |
| **RIGHT JOIN (RIGHT OUTER JOIN)** | Returns all rows from right table + matching rows from left                 | All Orders even if customer details are missing   |
| **FULL JOIN (FULL OUTER JOIN)**   | Returns all rows when there is a match in one of the tables (left or right) | All Customers and all Orders, even unmatched ones |
| **CROSS JOIN**                    | Returns **cartesian product** (all possible combinations)                   | Pair every customer with every product            |
| **SELF JOIN**                     | Join a table with itself                                                    | Find employees who report to other employees      |


---

## 1. What are Joins?
A **JOIN** clause is used to combine rows from two or more tables based on a related column between them.

---

## 2. INNER JOIN
Returns only the rows that have matching values in both tables.

**Example:**
```sql
SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

---

## 3. LEFT JOIN
Returns all rows from the left table and the matched rows from the right table. If there is no match, NULLs are returned.

**Example:**
```sql
SELECT employees.name, departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;
```

---

## 4. RIGHT JOIN
Returns all rows from the right table and the matched rows from the left table. If there is no match, NULLs are returned.

**Example:**
```sql
SELECT employees.name, departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;
```

---

## 5. FULL JOIN
Returns all rows when there is a match in one of the tables. Rows without a match in either table will have NULLs.

**Example:**
```sql
SELECT employees.name, departments.department_name
FROM employees
FULL OUTER JOIN departments
ON employees.department_id = departments.department_id;
```

*Note:* `FULL JOIN` may not be supported in all SQL dialects (e.g., MySQL). In such cases, use `UNION` of `LEFT` and `RIGHT` joins.

---

## Practice Exercises
1. Get a list of employees along with their department names.
2. List all employees, even those without a department.
3. List all departments, even those without any employees.
4. Find employees who are not assigned to any department.
5. Get a combined list of all employees and departments, regardless of matches.

---

## Next Steps
Move on to **Day 8** to explore **Self Joins and Cross Joins** – techniques to join a table with itself and combine all rows.
