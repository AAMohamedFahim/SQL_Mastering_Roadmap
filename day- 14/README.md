# Day 14: Set Operations – UNION, INTERSECT, EXCEPT ➕➖➗

## 🧭 Navigation

* [Overview](#overview)
* [Objectives](#objectives)
* [Set Operation Topics](#set-operation-topics)

  * [1. Introduction to Set Operations in SQL](#1-introduction-to-set-operations-in-sql)
  * [2. UNION vs. UNION ALL](#2-union-vs-union-all)
  * [3. INTERSECT Operation](#3-intersect-operation)
  * [4. EXCEPT Operation (or MINUS in some databases)](#4-except-operation-or-minus-in-some-databases)
  * [5. Rules and Requirements for Set Operations](#5-rules-and-requirements-for-set-operations)
  * [6. Handling Duplicates in Set Operations](#6-handling-duplicates-in-set-operations)
  * [7. Using ORDER BY with Set Operations](#7-using-order-by-with-set-operations)
  * [8. Combining Multiple Set Operations](#8-combining-multiple-set-operations)
  * [9. Performance Considerations](#9-performance-considerations)
  * [10. Real-World Use Cases of Set Operations](#10-real-world-use-cases-of-set-operations)
* [🧪 Practice Scenarios](#practice-scenarios)
* [🧠 Tips](#tips)
* [🔜 Next Up](#next-up)

---

## Overview

Set operations let you combine the results of two (or more) queries into a single result set. They’re super handy when you need to merge, intersect, or subtract data from separate tables or queries.

## Objectives

* Understand how `UNION`, `INTERSECT`, and `EXCEPT` (or `MINUS`) work.
* Learn when to use `UNION ALL` vs. `UNION`.
* See the rules for combining queries.
* Practice with real-world examples.

---

## Set Operation Topics

### 1. Introduction to Set Operations in SQL

Set operations treat query results like mathematical sets:

* **UNION**: combine distinct rows from both queries.
* **INTERSECT**: return only rows common to both.
* **EXCEPT** (or **MINUS**): return rows in the first query that aren’t in the second.

*All queries must have the same number of columns and compatible data types.*

### 2. UNION vs. UNION ALL

* **UNION** removes duplicates.
* **UNION ALL** keeps all rows, including duplicates (faster).

```sql
-- Sample tables
-- Table: students_2024
-- | id | name   |
-- |----|--------|
-- | 1  | Alice  |
-- | 2  | Bob    |

-- Table: students_2025
-- | id | name   |
-- |----|--------|
-- | 2  | Bob    |
-- | 3  | Carol  |

-- UNION (distinct)
SELECT name FROM students_2024
UNION
SELECT name FROM students_2025;
-- Result: Alice, Bob, Carol

-- UNION ALL (with duplicates)
SELECT name FROM students_2024
UNION ALL
SELECT name FROM students_2025;
-- Result: Alice, Bob, Bob, Carol
```

### 3. INTERSECT Operation

Returns only the rows that appear in both query results.

```sql
SELECT name FROM students_2024
INTERSECT
SELECT name FROM students_2025;
-- Result: Bob
```

| name |
| :--: |
|  Bob |

### 4. EXCEPT Operation (or MINUS in some databases)

Returns rows from the first query that aren’t in the second.

```sql
SELECT name FROM students_2024
EXCEPT
SELECT name FROM students_2025;
-- Result: Alice
```

|  name |
| :---: |
| Alice |

> **Note:** In Oracle or Oracle‑compatible engines you use `MINUS` instead of `EXCEPT`.

### 5. Rules and Requirements for Set Operations

1. Same number of columns.
2. Corresponding columns have compatible data types.
3. Column names in the final result come from the first query.

### 6. Handling Duplicates in Set Operations

* `UNION` deduplicates.
* `UNION ALL` preserves duplicates.
* `INTERSECT` and `EXCEPT` always remove duplicates.

### 7. Using ORDER BY with Set Operations

You can only apply `ORDER BY` once, at the end of the combined query:

```sql
SELECT name FROM students_2024
UNION
SELECT name FROM students_2025
ORDER BY name;
```

### 8. Combining Multiple Set Operations

You can chain set operators but mind the precedence:

1. `INTERSECT`
2. `UNION` / `UNION ALL`
3. `EXCEPT`

Example:

```sql
-- Get names in 2024 or 2025, but not in 2026
SELECT name FROM students_2024
UNION
SELECT name FROM students_2025
EXCEPT
SELECT name FROM students_2026;
```

### 9. Performance Considerations

* `UNION ALL` is faster than `UNION` (no dedupe step).
* Indexes on involved columns can help.
* Large datasets: consider temp tables or hashing strategies.

### 10. Real-World Use Cases of Set Operations

* **Merging** customer lists from multiple sources: `UNION ALL`.
* **Finding common** orders between two periods: `INTERSECT`.
* **Filtering out** unsubscribed users: `EXCEPT`.

---

## 🧪 Practice Scenarios

1. **Monthly Sales**

   * Tables: `sales_jan`, `sales_feb`
   * Task: Show all unique products sold in January or February.

2. **Staff Overlap**

   * Tables: `dept_a_staff`, `dept_b_staff`
   * Task: Find staff who work in both departments.

3. **Product Clearance**

   * Tables: `inventory_full`, `inventory_current`
   * Task: List items that were in inventory last month but aren’t now.

---

## 🧠 Tips

* Always check column order & types before combining.
* Use `UNION ALL` when you don’t need duplicates removed.
* Remember that `EXCEPT`/`MINUS` is not supported in every dialect—check yours.
* Wrap complex queries in CTEs for clarity before set‑ops.

---

## 🔜 Next Up

Day 15: Indexing – CREATE INDEX, Clustered, Non-Clustered 🗂️⚡
