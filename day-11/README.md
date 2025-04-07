# Day 11: String Functions 🎯

## 🧭 Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [Common String Functions](#common-string-functions)
  - [1. UPPER()](#1-upper)
  - [2. LOWER()](#2-lower)
  - [3. CONCAT()](#3-concat)
  - [4. SUBSTRING()](#4-substring)
  - [5. TRIM()](#5-trim)
- [🧪 Practice Scenarios](#practice-scenarios)
- [🧠 Tips](#tips)
- [🔜 Next Up](#next-up)

---

## 📖 Overview
String functions in SQL allow you to manipulate and transform text data. These are crucial for cleaning, formatting, and standardizing string fields like names, emails, and IDs.

---

## 🎯 Objectives
- Learn the most commonly used string functions in SQL
- Understand how to clean and format string data
- Chain multiple functions together for powerful transformations

---

## 🧵 Common String Functions

### 1. UPPER()
Converts a string to **uppercase**.

```sql
SELECT UPPER('mohamed') AS upper_name;
-- Result: MOHAMED
```

---

### 2. LOWER()
Converts a string to **lowercase**.

```sql
SELECT LOWER('FAHIM') AS lower_name;
-- Result: fahim
```

---

### 3. CONCAT()
Combines two or more strings into one.

```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name
FROM users;
```

You can also use `||` for concatenation in some SQL dialects.

---

### 4. SUBSTRING()
Extracts part of a string starting from a given position.

```sql
SELECT SUBSTRING('Hello World', 1, 5) AS result;
-- Result: Hello
```

---

### 5. TRIM()
Removes leading and trailing spaces (or specified characters).

```sql
SELECT TRIM('   fahim   ') AS cleaned_name;
-- Result: 'fahim'
```

You can also do:

```sql
SELECT TRIM(BOTH 'x' FROM 'xxxhello worldxxx') AS result;
-- Result: 'hello world'
```

---

## 🧪 Practice Scenarios

1. Format all product names to lowercase.
2. Show first 3 letters of each customer's name.
3. Concatenate city and state with a comma (e.g., "Chennai, TN").
4. Remove extra spaces from customer input names.
5. Convert all email addresses to lowercase for standardization.

---

## 🧠 Tips

- Combine multiple functions for powerful results:
  ```sql
  SELECT CONCAT(UPPER(first_name), ' ', LOWER(last_name)) AS formatted_name
  FROM employees;
  ```
- Always `TRIM()` user input when comparing strings.
- Use `SUBSTRING()` to extract codes, initials, or prefixes.

---

## 🔜 Next Up
On **Day 12**, we dive into **DDL commands** like `CREATE`, `ALTER`, and `DROP` to define and modify your database structures. 📦

Get ready to take control of your schemas! 🧱
