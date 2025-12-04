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

---
## Sample Table: reviews
review_id	user_id	submit_date	product_id	stars
6171	123	06/08/2022 00:00:00	50001	4
4582	562	06/15/2022 00:00:00	12580	4
7802	265	06/10/2022 00:00:00	69852	4
5293	362	06/18/2022 00:00:00	50001	3
6352	192	07/26/2022 00:00:00	69852	3
4517	981	07/05/2022 00:00:00	69852	2

--the review should have 4 or more stars,the review ID is less than 6000,the review ID is more than 2000,the review can't come from user 142
SELECT * FROM reviews where 
stars>4 AND
review_id<6000 AND
review_id>2000 AND
user_id !=142
;
--the start count is greater than 2, and less than or equal to 4 ,the review must come from either user 123, 265, or 362
SELECT * FROM reviews
WHERE stars>2 AND stars<=4  AND user_id IN (123,265,362);
