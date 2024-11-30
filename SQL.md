# ~ 📒 Notes on SQL & DBMS ~

---

### **Data Types for Table Columns**
- Each column (attribute) in a table must have a specific data type.

### **Basic SQL Queries**

#### **CREATE TABLE**
Creates a new database table.

**Syntax:**
```sql
CREATE TABLE table_name (
    column_name data_type,
    ...
);
```

**Example:**
```sql
CREATE TABLE students (
    s_id INT,
    name VARCHAR(50),
    cgpa FLOAT
);
```
- First, declare the column name, followed by its data type.

---

#### **SELECT**
Retrieves data from the table.

**Syntax:**
```sql
SELECT * FROM table_name;
```
- `*` selects all columns.

**Example:**
```sql
SELECT name FROM students;
```
- Retrieves only the "name" column.

---

#### **INSERT**
Inserts data into the table.

**Syntax:**
```sql
INSERT INTO table_name
VALUES (value1, value2, ...);
```

**Example:**
```sql
INSERT INTO students
VALUES (1, "Alice", 3.8);
```
- Values must match the order and data type defined in the `CREATE` statement.

---

### **SQL Syntax Rules**
- **Keywords:** Standard practice uses uppercase (e.g., `SELECT`, `FROM`).
- **Semicolon:** End each statement with `;`.

### **Common Data Types**
| Data Type | Description           |
|-----------|-----------------------|
| `INT`     | Integer               |
| `VARCHAR` | String (max length)   |
| `FLOAT`   | Floating-point number |

Reference: [SQL Keywords](https://www.w3schools.com/sql/sql_ref_keywords.asp)

---

### **Importance of Databases in Interviews**
- **Focus Areas:** 
  - Coding: 35%
  - Databases: 35%
  - OOP: 30%

---

### **Key Commands**

#### **DISTINCT**
Displays unique values for a column.

**Syntax:**
```sql
SELECT DISTINCT column_name
FROM table_name;
```

---

#### **AS (Alias)**
Renames a column in the result.

**Syntax:**
```sql
SELECT column_name AS alias_name
FROM table_name;
```

**Example:**
```sql
SELECT name AS "Student Name"
FROM students;
```

---

#### **CONCAT**
Combines strings with column data.

**Syntax:**
```sql
SELECT CONCAT(column1, "string", column2)
FROM table_name;
```

**Example:**
```sql
SELECT CONCAT(name, " belongs to the ", department)
AS "Student Info"
FROM students;
```

---

#### **WHERE**
Filters rows based on conditions.

**Syntax:**
```sql
SELECT *
FROM table_name
WHERE condition;
```

**Operators:**
- **Logical:** `AND`, `OR`, `NOT`
- **Comparison:** `=`, `>`, `<`, `>=`, `<=`, `<>`

**Example:**
```sql
SELECT *
FROM students
WHERE cgpa > 3.5 AND department = "CSE";
```

---

### **Additional Clauses**

#### **IN**
Simplifies comparisons with multiple values.

**Syntax:**
```sql
SELECT *
FROM table_name
WHERE column_name IN (value1, value2, ...);
```

**Example:**
```sql
SELECT *
FROM students
WHERE section IN ("A", "B", "C");
```

---

#### **BETWEEN**
Filters rows within a range (inclusive).

**Syntax:**
```sql
SELECT *
FROM table_name
WHERE column_name BETWEEN lower_bound AND upper_bound;
```

**Example:**
```sql
SELECT *
FROM students
WHERE cgpa BETWEEN 3.0 AND 4.0;
```

---

#### **LIKE**
Filters rows matching a string pattern.

**Wildcards:**
- `%` - Matches any sequence of characters.
- `_` - Matches a single character.

**Syntax Examples:**
```sql
SELECT *
FROM students
WHERE name LIKE "A%"; -- Names starting with A
WHERE name LIKE "_A%"; -- Second character is A
WHERE name LIKE "%A"; -- Names ending with A
```

---

### **ORDER BY**
Sorts data in ascending or descending order.

**Syntax:**
```sql
SELECT *
FROM table_name
ORDER BY column_name [ASC|DESC];
```

**Example:**
```sql
SELECT *
FROM students
ORDER BY cgpa DESC;
```

---

### **Joins**

#### **Equijoins**
Combines related tables using a foreign key.

**Syntax:**
```sql
SELECT e.col1, d.col2
FROM employees AS e, departments AS d
WHERE e.deptid = d.deptid;
```

#### **JOIN Types**
1. **INNER JOIN:** Matches rows in both tables.
2. **LEFT JOIN:** Includes all rows from the left table.
3. **RIGHT JOIN:** Includes all rows from the right table.

**Example:**
```sql
SELECT *
FROM employees AS e
LEFT JOIN departments AS d
ON e.deptid = d.deptid;
```

---

### **Aggregate Functions**
Perform calculations on columns.

| Function | Description                  |
|----------|------------------------------|
| `AVG`    | Average value                |
| `COUNT`  | Number of rows               |
| `MAX`    | Maximum value                |
| `MIN`    | Minimum value                |
| `SUM`    | Total value                  |

**Example:**
```sql
SELECT AVG(salary), COUNT(employeeid)
FROM employees;
```

---

### **GROUP BY**
Groups rows by a column.

**Syntax:**
```sql
SELECT column_name, COUNT(*)
FROM table_name
GROUP BY column_name;
```

**Example:**
```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department;
```

#### **HAVING**
Filters grouped data.

**Example:**
```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

---

### **Subqueries**
Nested queries for advanced filtering.

**Example:**
```sql
SELECT *
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

---

### **ANY & ALL**
Filters using conditions against subqueries.

**ANY Example:**
```sql
SELECT *
FROM employees
WHERE salary > ANY (SELECT salary FROM employees WHERE department = "Finance");
```

**ALL Example:**
```sql
SELECT *
FROM employees
WHERE salary > ALL (SELECT salary FROM employees WHERE department = "Finance");
```

---

### **UPDATE**
Updates data in a table.

**Syntax:**
```sql
UPDATE table_name
SET column_name = value
WHERE condition;
```

**Example:**
```sql
UPDATE students
SET cgpa = 4.0
WHERE name = "Alice";
```

---

### **Regular Expressions**
Alternative to `LIKE` for pattern matching.

**Syntax Example:**
```sql
SELECT *
FROM students
WHERE name REGEXP "^A.*s$";
```
- Matches names starting with "A" and ending with "s."

---