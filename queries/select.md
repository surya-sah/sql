# SELECT Statement
SQL SELECT queries to exactly tell the database what data we need to fetch and display.

Select each and every column in a table:
 you can use * instead of manually typing out all the column names:
```sql
SELECT *
 FROM table_name;
```
Select specific columns:
```sql
SELECT column1, column2 FROM table_name;