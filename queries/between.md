## pharmacy_sales Sample Input:

| product_id | units_sold | total_sales |   cogs     | manufacturer |        drug         |
|------------|------------|-------------|------------|--------------|----------------------|
|     9      |   37410    | 293452.54   | 208876.01  | Eli Lilly    | Zyprexa             |
|     34     |   94698    | 600997.19   | 521182.16  | AstraZeneca  | Surmontil           |
|     61     |   77023    | 500101.61   | 419174.97  | Biogen       | Varicose Relief     |
|    136     |  144814    | 1084258     | 1006447.73 | Biogen       | Burkhart            |

---

### **Query Requirement**
- Sold **between 100,000 and 105,000 units**
- Manufactured by **Biogen**, **AbbVie**, or **Eli Lilly**

### ✅ Correct SQL Query (PostgreSQL)

```sql
SELECT manufacturer, drug, units_sold
FROM pharmacy_sales
WHERE manufacturer IN ('Biogen', 'AbbVie', 'Eli Lilly')
  AND units_sold BETWEEN 100000 AND 105000;

## **Query Requirement 2**

Manufactured by Roche, Bayer, or AstraZeneca

Did NOT sell between 55,000 and 550,000 units

### ✅ Correct SQL Query (PostgreSQL)

```sql
SELECT manufacturer, drug, units_sold
FROM pharmacy_sales
WHERE manufacturer IN ('Biogen', 'AbbVie', 'Eli Lilly')
  AND units_sold BETWEEN 100000 AND 105000;