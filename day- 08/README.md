# Day 8: Self Joins and Cross Joins

## Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
  - [1. Self Join](#1-self-join)
  - [2. Cross Join](#2-cross-join)
- [Practice Exercises](#practice-exercises)
- [Next Steps](#next-steps)

---

## Overview
On Day 8, we explore more advanced join concepts: **Self Joins** and **Cross Joins**. These joins help in comparing rows within the same table or creating Cartesian products.

---

## Objectives
- Understand how to join a table with itself using a **Self Join**.
- Learn how a **Cross Join** creates a Cartesian product of two tables.
- Use these joins for hierarchical comparisons and combinatorial logic.

---

## Topics Covered

### 1. Self Join
A **Self Join** is a regular join but the table is joined with itself.

**Use Case:** Finding employees and their managers from the same `employees` table.

**Example:**
```sql
SELECT A.name AS employee, B.name AS manager
FROM employees A
JOIN employees B
ON A.manager_id = B.employee_id;
```

📌 **Alias** is important in self joins to differentiate the two instances of the same table.

---

### 2. Cross Join
A **Cross Join** returns the Cartesian product of two tables. It joins each row of the first table with every row of the second table.

**Use Case:** Creating all combinations of sizes and colors.

**Example:**
```sql
SELECT colors.color, sizes.size
FROM colors
CROSS JOIN sizes;
```

📌 Be careful with large tables — cross joins can produce a huge number of rows.

---

## Practice Exercises
1. List all employee-manager pairs using a self join.
2. Find employees who don’t have a manager (use `LEFT JOIN` logic).
3. Generate all combinations of two columns (e.g., product types and regions) using cross join.
4. Combine two short tables (e.g., 3 rows x 3 rows) and observe the output of cross join.
5. Use self join to find duplicate records based on some columns (excluding ID).

---

## Next Steps
On **Day 9**, we'll dive into **UNION, INTERSECT, and EXCEPT** to combine result sets from multiple queries.

Keep joining the dots! 🔗
