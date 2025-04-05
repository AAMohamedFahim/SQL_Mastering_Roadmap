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
