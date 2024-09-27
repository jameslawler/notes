## SQL

Union two tables and select distinct names of pets

```sql
-- Write only the SQL statement that solves the problem and nothing else
SELECT distinct(name)
FROM dogs
UNION
SELECT distinct(name)
FROM cats
```
