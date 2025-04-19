# Day 12: Date & Time Functions ⏳

## 🧭 Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Core Date & Time Functions](#core-date--time-functions)
  - [1. NOW()](#1-now)
  - [2. DATEDIFF()](#2-datediff)
  - [3. EXTRACT()](#3-extract)
  - [4. DATE_ADD()](#4-date_add)
  - [5. FORMAT_DATE()](#5-format_date)
- [🧪 Practice Scenarios](#practice-scenarios)
- [🧠 Tips](#tips)
- [🔜 Next Up](#next-up)

---

## 📖 Overview
Date and time functions allow you to perform calculations and extract insights based on timestamps — crucial for tracking events, aging data, and scheduling operations.

---

## 🎯 Objectives
- Learn how to retrieve and manipulate date/time values
- Calculate differences between dates
- Extract specific components (like year or month)
- Add or subtract time intervals
- Format dates into readable strings

---

## ⏱️ Core Date & Time Functions

### 1. NOW()
Returns the current date and time.

```sql
SELECT NOW() AS current_timestamp;
-- Example Result: 2025-04-07 10:23:45
```

---

### 2. DATEDIFF()
Calculates the **difference in days** between two dates.

```sql
SELECT DATEDIFF('2025-04-10', '2025-04-01') AS diff_days;
-- Result: 9
```

---

### 3. EXTRACT()
Extracts a specific part (year, month, day, etc.) from a date.

```sql
SELECT EXTRACT(YEAR FROM order_date) AS order_year
FROM orders;
```

You can also extract:
- `MONTH`
- `DAY`
- `WEEK`
- `HOUR`, `MINUTE`, `SECOND`

---

### 4. DATE_ADD()
Adds a specific time interval to a date.

```sql
SELECT DATE_ADD('2025-04-01', INTERVAL 7 DAY) AS future_date;
-- Result: 2025-04-08
```

Similarly, you can use:
```sql
SELECT DATE_ADD(NOW(), INTERVAL 1 MONTH);
```

---

### 5. FORMAT_DATE()
Formats a `DATE` into a readable string using a format pattern.

```sql
SELECT FORMAT_DATE('%d-%m-%Y', DATE '2025-04-19') AS formatted;
-- Result: 19-04-2025
```

Other examples:
```sql
SELECT FORMAT_DATE('%B %d, %Y', DATE '2025-04-19');
-- Result: April 19, 2025

SELECT FORMAT_DATE('%A', DATE '2025-04-19');
-- Result: Saturday
```

Common format specifiers:
- `%Y` = Year (e.g., 2025)
- `%m` = Month (01–12)
- `%B` = Full month name
- `%d` = Day of the month (01–31)
- `%A` = Full weekday name

> Note: `FORMAT_DATE()` is available in BigQuery. Use `TO_CHAR()` in PostgreSQL or `FORMAT()` in MySQL.

---

## 🧪 Practice Scenarios

1. Find how many days have passed since a user's last login.
2. List orders placed in the current year.
3. Show all records created in the last 30 days.
4. Calculate the number of months between two dates.
5. Add 90 days to each subscription start date.
6. Format the created_at column to show `dd/MM/yyyy`.

---

## 🧠 Tips

- Use `NOW()` or `CURRENT_DATE` for real-time filters.
- Combine `DATEDIFF()` with `WHERE` to filter old records:
  ```sql
  SELECT * FROM sessions WHERE DATEDIFF(NOW(), start_time) > 30;
  ```
- `EXTRACT()` is useful for creating time-based groupings.
- `FORMAT_DATE()` is perfect for clean, human-friendly output.

---

## 🔜 Next Up
On **Day 13**, you'll explore **aggregate functions** like `COUNT()`, `SUM()`, `AVG()`, `MAX()`, and `MIN()` to summarize and analyze your data effectively. 📊

Things are about to get statistically awesome!
