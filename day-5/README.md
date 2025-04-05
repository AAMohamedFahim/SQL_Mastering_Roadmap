# Day 5: Grouping Data

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. GROUP BY Clause](#1-group-by-clause)
  - [2. HAVING Clause](#2-having-clause)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

## Overview
Day 5 focuses on grouping rows in a table based on one or more columns and then applying aggregate functions to those groups. It also introduces the `HAVING` clause to filter grouped results.

### Objectives
- Use `GROUP BY` to group rows that have the same values.
- Apply aggregate functions to grouped data.
- Use `HAVING` to filter data after grouping.

## Topics Covered
1. GROUP BY Clause  
2. HAVING Clause

---

## 1. GROUP BY Clause
The `GROUP BY` clause is used with aggregate functions to group the result-set by one or more columns.

**Syntax:**
```sql
SELECT column_name, AGGREGATE_FUNCTION(column_name)
FROM table_name
GROUP BY column_name;
```

**Example:**
```sql
SELECT department, COUNT(*) AS total_employees
FROM employees
GROUP BY department;
```

---

## 2. HAVING Clause
The `HAVING` clause is used to filter groups created by the `GROUP BY` clause, unlike `WHERE` which filters rows before grouping.

**Example:**
```sql
SELECT department, AVG(salary) AS avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;
```

---

## Practice Exercises
1. Count the number of products in each category.
2. Get the total sales amount for each customer.
3. Find departments with more than 5 employees.
4. Show average order value per region, only for regions with avg > $100.
5. List categories with total stock less than 100 units.

---

## Next Steps
Move on to **Day 6** to learn about **joining tables** using different types of SQL joins: `INNER`, `LEFT`, `RIGHT`, and `FULL OUTER JOIN`.
