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
  - [6. LPAD()](#6-lpad)
  - [7. RPAD()](#7-rpad)
  - [8. LENGTH()](#8-length)
  - [9. POSITION()](#9-position)
  - [10. REPLACE()](#10-replace)
  - [11. REVERSE()](#11-reverse)
  - [12. REGEXP_REPLACE()](#12-regexp_replace)
  - [13. REGEXP_LIKE() / ~](#13-regexp_like--)
  - [14. INITCAP()](#14-initcap)
  - [15. TRANSLATE()](#15-translate)
  - [16. SPLIT_PART()](#16-split_part)
  - [17. FORMAT() / TO_CHAR()](#17-format--to_char)
  - [18. SOUNDEX()](#18-soundex)
- [🧪 Practice Scenarios](#practice-scenarios)
- [🧠 Tips](#tips)
- [🔍 Dialect Notes](#dialect-notes)
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

### 6. LPAD()
Pads the left side of a string with a given character to a certain length.

```sql
SELECT LPAD('123', 5, '0') AS padded;
-- Result: 00123
```

---

### 7. RPAD()
Pads the right side of a string with a given character.

```sql
SELECT RPAD('abc', 5, '.') AS padded;
-- Result: abc..
```

---

### 8. LENGTH()
Returns the number of characters in a string.

```sql
SELECT LENGTH('fahim') AS len;
-- Result: 5
```

---

### 9. POSITION()
Finds the position of a substring.

```sql
SELECT POSITION('o' IN 'mohamed') AS pos;
-- Result: 2
```

---

### 10. REPLACE()
Replaces all occurrences of a substring.

```sql
SELECT REPLACE('fahim', 'a', 'x') AS new_string;
-- Result: fxhim
```

---

### 11. REVERSE()
Reverses a string (available in many dialects).

```sql
SELECT REVERSE('abc') AS rev;
-- Result: cba
```

---

### 12. REGEXP_REPLACE()
Replaces substrings that match a regular expression.

```sql
SELECT REGEXP_REPLACE('abc123', '\\d', '') AS clean;
-- Result: abc
```

---

### 13. REGEXP_LIKE() / ~ (PostgreSQL)
Used to check if a string matches a regex pattern.

```sql
SELECT name FROM users WHERE name ~ '^[A-Z]';
-- Names that start with uppercase
```

---

### 14. INITCAP()
Capitalizes the first letter of each word.

```sql
SELECT INITCAP('hello world') AS title_case;
-- Result: Hello World
```

---

### 15. TRANSLATE()
Replaces characters in a string one-by-one.

```sql
SELECT TRANSLATE('abc123', 'abc', 'xyz') AS result;
-- Result: xyz123
```

---

### 16. SPLIT_PART()
Splits a string by a delimiter and returns part.

```sql
SELECT SPLIT_PART('john.doe@example.com', '@', 1) AS username;
-- Result: john.doe
```

---

### 17. FORMAT() / TO_CHAR()
Formats numbers or dates as strings.

```sql
SELECT TO_CHAR(12345.678, '99999.99') AS formatted;
-- Result: 12345.68
```

---

### 18. SOUNDEX()
Returns a phonetic representation useful for fuzzy matches.

```sql
SELECT SOUNDEX('Mohamed'), SOUNDEX('Muhammad');
-- Both will likely return M053 (depends on DB)
```

---

## 🧪 Practice Scenarios

1. Format all product names to lowercase.
2. Show first 3 letters of each customer's name.
3. Concatenate city and state with a comma (e.g., "Chennai, TN").
4. Remove extra spaces from customer input names.
5. Convert all email addresses to lowercase for standardization.
6. Pad customer IDs to 5 digits (e.g., 00042).
7. Extract domain from email addresses.
8. Replace vowels with '*'.
9. Identify names that sound similar using `SOUNDEX()`.
10. Title-case all customer names.

---

## 🧠 Tips

- Combine multiple functions for powerful results:
  ```sql
  SELECT CONCAT(UPPER(first_name), ' ', LOWER(last_name)) AS formatted_name
  FROM employees;
  ```
- Always `TRIM()` user input when comparing strings.
- Use `SUBSTRING()` to extract codes, initials, or prefixes.
- Use `LENGTH()` and `POSITION()` for validation and parsing.

## for regex refer

---

## 🔍 Dialect Notes

- `INITCAP()` and `TRANSLATE()` are available in PostgreSQL and Oracle.
- `SPLIT_PART()` is available in PostgreSQL; use `STRING_SPLIT()` in SQL Server.
- `TO_CHAR()` is used in PostgreSQL/Oracle; use `FORMAT()` in SQL Server.
- String concatenation uses `||` in PostgreSQL and `+` in SQL Server.

---

## 🔜 Next Up
On **Day 12**, we dive into **DDL commands** like `CREATE`, `ALTER`, and `DROP` to define and modify your database structures. 📦

Get ready to take control of your schemas! 🧱

