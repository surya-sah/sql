# SQL WHERE Clause Notes

## 1. Purpose
The `WHERE` clause is used to **filter rows** in a table based on specified conditions.

---
## Sample Table: Employees

| id | name    | department | salary | manager_id |
|----|--------|-----------|--------|------------|
| 1  | Alice  | HR        | 55000  | NULL       |
| 2  | Bob    | Finance   | 48000  | 1          |
| 3  | Charlie| IT        | 60000  | 1          |
| 4  | David  | HR        | 45000  | 2          |
| 5  | Eve    | Finance   | 50000  | NULL       |
| 6  | Amy    | HR        | 70000  | 3          |

---

## WHERE Clause Examples (with Results)

```sql
-- 1. Equality Check
SELECT * FROM Employees WHERE department = 'HR';
-- Result: Alice, David, Amy

-- 2. Comparison
SELECT * FROM Employees WHERE salary > 50000;
-- Result: Alice, Charlie, Amy

-- 3. Multiple Values (IN)
SELECT * FROM Employees WHERE department IN ('HR','Finance');
-- Result: Alice, Bob, David, Eve, Amy

-- 4. Pattern Matching (LIKE)
SELECT * FROM Employees WHERE name LIKE 'A%';
-- Result: Alice, Amy

-- 5. Range Check (BETWEEN)
SELECT * FROM Employees WHERE salary BETWEEN 40000 AND 60000;
-- Result: Alice, Bob, Charlie, David, Eve

-- 6. NULL Check
SELECT * FROM Employees WHERE manager_id IS NULL;
-- Result: Alice, Eve


--Combine conditions with AND / OR:

SELECT * FROM Employees
WHERE department = 'HR' AND salary > 50000;
-- Result: Alice, Amy