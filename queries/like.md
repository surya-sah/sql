## Customers Sample Input:

| customer_id | customer_name       | gender | age | zip_code | city             | state                         |
|-------------|----------------------|--------|-----|----------|------------------|-------------------------------|
| 1           | Ignace Whillock      | Male   | 30  | 5464     | Johnstonhaven    | Northern Territory            |
| 2           | Gray Eskrick         | Female | 69  | 8223     | New Zacharyfort  | South Australia               |
| 3           | Ellswerth Laurent    | Male   | 59  | 5661     | Aliburgh         | Australian Capital Territory  |
| ...         | ...                  | ...    | ... | ...      | ...              | ...                           |

---

## Query Requirement

- First name starts with **"F"**
- Last name ends with **"ck"**

---

### ✅ Correct SQL Query

```sql
SELECT *
FROM customers
WHERE customer_name LIKE 'F%'
  AND customer_name LIKE '%ck';
  
--------------------
## customers Sample Input:

| customer_id | customer_name       | gender | age | zip_code | city            | state                          |
|-------------|----------------------|--------|-----|----------|------------------|---------------------------------|
| 1           | Ignace Whillock      | Male   | 30  | 5464     | Johnstonhaven    | Northern Territory              |
| 2           | Gray Eskrick         | Female | 69  | 8223     | New Zacharyfort  | South Australia                 |
| 3           | Ellswerth Laurent    | Male   | 59  | 5661     | Aliburgh         | Australian Capital Territory    |
| ...         | ...                  | ...    | ... | ...      | ...              | ...                             |

---

## Query Requirement

Find all customers where the **2nd and 3rd letters in their name are "e"**.

**Example:**  
- Reece Smith → "R**ee**ce"

---

### ✅ Correct SQL Query

sql
SELECT *
FROM customers
WHERE customer_name LIKE '_ee%';