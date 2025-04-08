# Day 6: Subqueries – Single-row, Multi-row, Correlated Subqueries

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. What is a Subquery?](#1-what-is-a-subquery)
  - [2. Single-row Subquery](#2-single-row-subquery)
  - [3. Multi-row Subquery](#3-multi-row-subquery)
  - [4. Correlated Subquery](#4-correlated-subquery)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

## Overview
Day 6 introduces **subqueries**—SQL queries nested inside another query. You’ll learn how to use single-row, multi-row, and correlated subqueries to enhance the power and flexibility of your SQL statements.

### Objectives
- Understand the concept and usage of subqueries.
- Differentiate between single-row, multi-row, and correlated subqueries.
- Apply subqueries to filter, compute, and compare data effectively.

## Topics Covered
1. What is a Subquery?  
2. Single-row Subquery  
3. Multi-row Subquery  
4. Correlated Subquery

---

## 1. What is a Subquery?
A subquery is a query nested inside another SQL query. It can be used in `SELECT`, `FROM`, or `WHERE` clauses.

**Example:**
```sql
SELECT name
FROM employees
WHERE department_id = (
  SELECT department_id
  FROM departments
  WHERE department_name = 'Sales'
);
```

---

## 2. Single-row Subquery
Returns a single value. Used with operators like `=`, `<`, `>`, etc.

**Example:**
```sql
SELECT name
FROM employees
WHERE salary = (
  SELECT MAX(salary)
  FROM employees
);
```

---

## 3. Multi-row Subquery
Returns multiple values. Used with operators like `IN`, `ANY`, `ALL`.

**Example (IN):**
```sql
SELECT name
FROM employees
WHERE department_id IN (
  SELECT department_id
  FROM departments
  WHERE region_id = 2
);
```

---

## 4. Correlated Subquery
A subquery that references columns from the outer query. It is executed once for each row in the outer query.

**Example:**
```sql
SELECT name, salary
FROM employees e
WHERE salary > (
  SELECT AVG(salary)
  FROM employees
  WHERE department_id = e.department_id
);
```

---

## Practice Exercises
1. Find the employee with the highest salary.
2. List employees who work in the same department as ‘John’.
3. Get names of employees who earn more than the average salary of their department.
4. Find departments where no employee earns more than $70,000.
5. List all employees in regions that have more than one department.

---

## Next Steps
Move on to **Day 7** to learn about **Joins** – combining data from multiple tables using `INNER JOIN`, `LEFT JOIN`, and more.

