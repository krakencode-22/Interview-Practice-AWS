Certainly! Below is the previous answer in **Markdown format**. You can copy and save this as a `.md` file for easy reference.

```markdown
# SQL Study Guide

Here are a few **sample SQL queries** and **quick-reference tables** that can be added to the study guide. These will be helpful for quick lookup during the interview and can be printed for easy reference.

---


### 1. Basic SELECT Query
```sql
SELECT * FROM employees;
```
- Retrieves all columns and rows from the `employees` table.

---

### 2. Filtering with WHERE
```sql
SELECT * FROM employees WHERE salary > 50000;
```
- Retrieves employees with a salary greater than 50,000.

---

### 3. Sorting with ORDER BY
```sql
SELECT * FROM employees ORDER BY last_name ASC;
```
- Retrieves all employees sorted by `last_name` in ascending order.

---

### 4. Grouping with GROUP BY
```sql
SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department;
```
- Groups employees by department and counts the number of employees in each department.

---

### 5. Filtering Groups with HAVING
```sql
SELECT department, AVG(salary) AS avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 70000;
```
- Retrieves departments with an average salary greater than 70,000.

---

### 6. Joining Tables with INNER JOIN
```sql
SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments ON employees.department_id = departments.id;
```
- Retrieves employee names and their department names by joining `employees` and `departments` tables.

---

### 7. Using Subqueries
```sql
SELECT name FROM employees
WHERE department_id = (SELECT id FROM departments WHERE department_name = 'Sales');
```
- Retrieves names of employees who work in the 'Sales' department.

---

### 8. Using UNION
```sql
SELECT name FROM employees
UNION
SELECT name FROM contractors;
```
- Combines names from `employees` and `contractors` tables, removing duplicates.

---

### 9. Creating a View
```sql
CREATE VIEW high_salary_employees AS
SELECT * FROM employees WHERE salary > 100000;
```
- Creates a view that stores employees with a salary greater than 100,000.

---

### 10. Using Transactions
```sql
BEGIN TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```
- Transfers 100 units from account 1 to account 2 as a single transaction.

---

## Quick-Reference Tables

### SQL Clauses and Their Uses
| Clause         | Purpose                                                                 |
|----------------|-------------------------------------------------------------------------|
| `SELECT`       | Retrieves data from a table.                                           |
| `WHERE`        | Filters rows based on a condition.                                     |
| `GROUP BY`     | Groups rows with the same values.                                      |
| `HAVING`       | Filters groups based on a condition.                                   |
| `ORDER BY`     | Sorts the result set.                                                  |
| `JOIN`         | Combines rows from two or more tables.                                 |
| `LIMIT`        | Limits the number of rows returned.                                    |
| `DISTINCT`     | Removes duplicate rows from the result set.                            |

---

### Types of Joins
| Join Type      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `INNER JOIN`   | Returns only matching rows from both tables.                               |
| `LEFT JOIN`    | Returns all rows from the left table and matching rows from the right table.|
| `RIGHT JOIN`   | Returns all rows from the right table and matching rows from the left table.|
| `FULL JOIN`    | Returns all rows when there is a match in either table.                    |
| `CROSS JOIN`   | Returns the Cartesian product of both tables.                              |

---

### Aggregate Functions
| Function       | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `COUNT()`      | Counts the number of rows.                                                 |
| `SUM()`        | Calculates the sum of a numeric column.                                    |
| `AVG()`        | Calculates the average of a numeric column.                                |
| `MIN()`        | Finds the minimum value in a column.                                       |
| `MAX()`        | Finds the maximum value in a column.                                       |

---

### Common Data Types
| Data Type      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `INT`          | Integer values.                                                            |
| `VARCHAR(n)`   | Variable-length string with a maximum length of `n`.                       |
| `CHAR(n)`      | Fixed-length string with a length of `n`.                                  |
| `DATE`         | Stores date values (YYYY-MM-DD).                                           |
| `FLOAT`        | Stores floating-point numbers.                                             |

---

## Tips for Using the Study Guide
1. **Print the Guide**: Print this document for easy reference during the interview.
2. **Practice Queries**: Run the sample queries in a SQL environment to understand how they work.
3. **Memorize Key Concepts**: Familiarize yourself with the quick-reference tables for fast recall.
4. **Stay Calm**: Use the guide as a tool to support your answers, not as a crutch.

Good luck with your interview! 🚀
```

---
