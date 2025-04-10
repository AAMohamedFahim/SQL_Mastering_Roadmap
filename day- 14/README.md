# Day 14: Set Operations – UNION, INTERSECT, EXCEPT ➕➖➗

## 🧭 Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Set Operation Topics](#set-operation-topics)
  - [1. Introduction to Set Operations in SQL](#1-introduction-to-set-operations-in-sql)
  - [2. UNION vs. UNION ALL](#2-union-vs-union-all)
  - [3. INTERSECT Operation](#3-intersect-operation)
  - [4. EXCEPT Operation (or MINUS in some databases)](#4-except-operation-or-minus-in-some-databases)
  - [5. Rules and Requirements for Set Operations](#5-rules-and-requirements-for-set-operations)
  - [6. Handling Duplicates in Set Operations](#6-handling-duplicates-in-set-operations)
  - [7. Using ORDER BY with Set Operations](#7-using-order-by-with-set-operations)
  - [8. Combining Multiple Set Operations](#8-combining-multiple-set-operations)
  - [9. Performance Considerations](#9-performance-considerations)
  - [10. Real-World Use Cases of Set Operations](#10-real-world-use-cases-of-set-operations)
- [🧪 Practice Scenarios](#practice-scenarios)
- [🧠 Tips](#tips)
- [🔜 Next Up](#next-up)

---

## 📖 Overview
Set operations allow you to combine results from multiple queries. They enable comparisons and unions of different datasets — all while preserving or eliminating duplicates based on the operation used.

---

## 🎯 Objectives
- Understand how to combine results using SQL set operations
- Differentiate between `UNION`, `UNION ALL`, `INTERSECT`, and `EXCEPT`
- Learn about handling duplicates and column compatibility
- Master ordering and chaining of multiple operations

---

## 🧩 Set Operation Topics

### 1. Introduction to Set Operations in SQL
Set operations combine results from two or more queries. Each query must return the same number and type of columns.

---

### 2. UNION vs. UNION ALL

```sql
-- UNION: Removes duplicates
SELECT city FROM customers
UNION
SELECT city FROM suppliers;

-- UNION ALL: Keeps duplicate
SELECT city FROM customers
UNION ALL
SELECT city FROM suppliers;
