# Day 13: CASE Statements – Conditional Logic in Queries 🧠⚙️

## 🧭 Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [CASE Statement Topics](#case-statement-topics)
  - [1. Introduction to Conditional Logic in SQL](#1-introduction-to-conditional-logic-in-sql)
  - [2. Basic Syntax of CASE Statement](#2-basic-syntax-of-case-statement)
  - [3. Simple CASE vs. Searched CASE](#3-simple-case-vs-searched-case)
  - [4. Using CASE in SELECT Clause](#4-using-case-in-select-clause)
  - [5. Using CASE in ORDER BY Clause](#5-using-case-in-order-by-clause)
  - [6. Using CASE in WHERE Clause](#6-using-case-in-where-clause)
  - [7. Nested CASE Statements](#7-nested-case-statements)
  - [8. Handling NULLs with CASE](#8-handling-nulls-with-case)
  - [9. Combining CASE with Aggregate Functions](#9-combining-case-with-aggregate-functions)
  - [10. Real-World Use Cases with CASE](#10-real-world-use-cases-with-case)
- [🧪 Practice Scenarios](#practice-scenarios)
- [🧠 Tips](#tips)
- [🔜 Next Up](#next-up)

---

## 📖 Overview
The `CASE` statement is a powerful SQL feature that allows conditional logic directly within queries. Whether you're transforming values, categorizing data, or creating dynamic ordering — `CASE` has you covered.

---

## 🎯 Objectives
- Understand how conditional logic works in SQL
- Write both simple and searched `CASE` expressions
- Use `CASE` across `SELECT`, `WHERE`, and `ORDER BY`
- Handle NULL values and integrate logic into aggregate functions

---

## 🧩 CASE Statement Topics

### 1. Introduction to Conditional Logic in SQL
SQL is declarative, but with `CASE`, you introduce decision-making within your queries, similar to `if-else` logic in programming.

---

### 2. Basic Syntax of CASE Statement

```sql
CASE 
  WHEN condition THEN result
  [WHEN ...]
  [ELSE default_result]
END
```

---

### 3. Simple CASE vs. Searched CASE

**Simple CASE** (compares a single expression):

```sql
CASE status
  WHEN 'new' THEN '🆕 New Order'
  WHEN 'shipped' THEN '🚚 Shipped'
  ELSE '❓ Unknown'
END
```

**Searched CASE** (evaluates multiple conditions):

```sql
CASE 
  WHEN amount > 1000 THEN 'High Value'
  WHEN amount > 500 THEN 'Medium Value'
  ELSE 'Low Value'
END
```

---

### 4. Using CASE in SELECT Clause

```sql
SELECT 
  name,
  salary,
  CASE 
    WHEN salary > 100000 THEN 'Top Earner'
    ELSE 'Regular'
  END AS category
FROM employees;
```

---

### 5. Using CASE in ORDER BY Clause

```sql
SELECT product_name, stock_quantity
FROM products
ORDER BY 
  CASE 
    WHEN stock_quantity = 0 THEN 1
    ELSE 0
  END,
  product_name;
```

> This places out-of-stock products at the bottom.

---

### 6. Using CASE in WHERE Clause

```sql
SELECT * FROM users
WHERE 
  CASE 
    WHEN country = 'India' THEN age >= 18
    ELSE age >= 21
  END;
```

---

### 7. Nested CASE Statements

```sql
CASE 
  WHEN role = 'Manager' THEN 
    CASE 
      WHEN experience > 5 THEN 'Senior Manager'
      ELSE 'Junior Manager'
    END
  ELSE 'Staff'
END
```

---

### 8. Handling NULLs with CASE

```sql
SELECT 
  name,
  CASE 
    WHEN last_login IS NULL THEN 'Never Logged In'
    ELSE 'Active'
  END AS login_status
FROM users;
```

---

### 9. Combining CASE with Aggregate Functions

```sql
SELECT 
  department,
  COUNT(CASE WHEN status = 'active' THEN 1 END) AS active_employees
FROM employees
GROUP BY department;
```

---

### 10. Real-World Use Cases with CASE

- Categorize products by price range
- Display customer tiers (Gold, Silver, Bronze)
- Create readable labels for codes/statuses
- Apply business logic for discounts or scoring
- Filter data dynamically based on conditions

---

## 🧪 Practice Scenarios

1. Categorize employees by salary range using CASE.
2. Reorder a product list showing out-of-stock items last.
3. Replace NULL review values with 'No Review' label.
4. Count how many active/inactive users exist per region.
5. Display discount logic based on customer type.

---

## 🧠 Tips

- Use **Searched CASE** for more flexibility.
- Don't forget the `ELSE` clause to avoid `NULL` results.
- Combine `CASE` with aggregates for powerful grouped insights.
- Keep complex CASE logic readable — break into subqueries if needed.

---

## 🔜 Next Up
On **Day 14**, it’s all about **JOINS** — combining rows from different tables using `INNER`, `LEFT`, `RIGHT`, and `FULL OUTER JOIN`. 🔗

Your relational data is about to come together beautifully!
# Day 13: CASE Statements – Conditional Logic in Queries 🧠⚙️

## 🧭 Navigation
- [Overview](#overview)
- [Objectives](#objectives)
- [CASE Statement Topics](#case-statement-topics)
  - [1. Introduction to Conditional Logic in SQL](#1-introduction-to-conditional-logic-in-sql)
  - [2. Basic Syntax of CASE Statement](#2-basic-syntax-of-case-statement)
  - [3. Simple CASE vs. Searched CASE](#3-simple-case-vs-searched-case)
  - [4. Using CASE in SELECT Clause](#4-using-case-in-select-clause)
  - [5. Using CASE in ORDER BY Clause](#5-using-case-in-order-by-clause)
  - [6. Using CASE in WHERE Clause](#6-using-case-in-where-clause)
  - [7. Nested CASE Statements](#7-nested-case-statements)
  - [8. Handling NULLs with CASE](#8-handling-nulls-with-case)
  - [9. Combining CASE with Aggregate Functions](#9-combining-case-with-aggregate-functions)
  - [10. Real-World Use Cases with CASE](#10-real-world-use-cases-with-case)
- [🧪 Practice Scenarios](#practice-scenarios)
- [🧠 Tips](#tips)
- [🔜 Next Up](#next-up)

---

## 📖 Overview
The `CASE` statement is a powerful SQL feature that allows conditional logic directly within queries. Whether you're transforming values, categorizing data, or creating dynamic ordering — `CASE` has you covered.

---

## 🎯 Objectives
- Understand how conditional logic works in SQL
- Write both simple and searched `CASE` expressions
- Use `CASE` across `SELECT`, `WHERE`, and `ORDER BY`
- Handle NULL values and integrate logic into aggregate functions

---

## 🧩 CASE Statement Topics

### 1. Introduction to Conditional Logic in SQL
SQL is declarative, but with `CASE`, you introduce decision-making within your queries, similar to `if-else` logic in programming.

---

### 2. Basic Syntax of CASE Statement

```sql
CASE 
  WHEN condition THEN result
  [WHEN ...]
  [ELSE default_result]
END
```

---

### 3. Simple CASE vs. Searched CASE

**Simple CASE** (compares a single expression):

```sql
CASE status
  WHEN 'new' THEN '🆕 New Order'
  WHEN 'shipped' THEN '🚚 Shipped'
  ELSE '❓ Unknown'
END
```

**Searched CASE** (evaluates multiple conditions):

```sql
CASE 
  WHEN amount > 1000 THEN 'High Value'
  WHEN amount > 500 THEN 'Medium Value'
  ELSE 'Low Value'
END
```

---

### 4. Using CASE in SELECT Clause

```sql
SELECT 
  name,
  salary,
  CASE 
    WHEN salary > 100000 THEN 'Top Earner'
    ELSE 'Regular'
  END AS category
FROM employees;
```

---

### 5. Using CASE in ORDER BY Clause

```sql
SELECT product_name, stock_quantity
FROM products
ORDER BY 
  CASE 
    WHEN stock_quantity = 0 THEN 1
    ELSE 0
  END,
  product_name;
```

> This places out-of-stock products at the bottom.

---

### 6. Using CASE in WHERE Clause

```sql
SELECT * FROM users
WHERE 
  CASE 
    WHEN country = 'India' THEN age >= 18
    ELSE age >= 21
  END;
```

---

### 7. Nested CASE Statements

```sql
CASE 
  WHEN role = 'Manager' THEN 
    CASE 
      WHEN experience > 5 THEN 'Senior Manager'
      ELSE 'Junior Manager'
    END
  ELSE 'Staff'
END
```

---

### 8. Handling NULLs with CASE

```sql
SELECT 
  name,
  CASE 
    WHEN last_login IS NULL THEN 'Never Logged In'
    ELSE 'Active'
  END AS login_status
FROM users;
```

---

### 9. Combining CASE with Aggregate Functions

```sql
SELECT 
  department,
  COUNT(CASE WHEN status = 'active' THEN 1 END) AS active_employees
FROM employees
GROUP BY department;
```

---

### 10. Real-World Use Cases with CASE

- Categorize products by price range
- Display customer tiers (Gold, Silver, Bronze)
- Create readable labels for codes/statuses
- Apply business logic for discounts or scoring
- Filter data dynamically based on conditions

---

## 🧪 Practice Scenarios

1. Categorize employees by salary range using CASE.
2. Reorder a product list showing out-of-stock items last.
3. Replace NULL review values with 'No Review' label.
4. Count how many active/inactive users exist per region.
5. Display discount logic based on customer type.

---

## 🧠 Tips

- Use **Searched CASE** for more flexibility.
- Don't forget the `ELSE` clause to avoid `NULL` results.
- Combine `CASE` with aggregates for powerful grouped insights.
- Keep complex CASE logic readable — break into subqueries if needed.

---

## 🔜 Next Up
On **Day 14**, it’s all about **JOINS** — combining rows from different tables using `INNER`, `LEFT`, `RIGHT`, and `FULL OUTER JOIN`. 🔗

Your relational data is about to come together beautifully!
