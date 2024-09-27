## SQL

```sql
-- Write only the SQL statement that solves the problem and nothing else
SELECT name
FROM employees as e1
WHERE id NOT IN (SELECT managerId FROM employees as e2 WHERE e2.managerId = e1.id)
```
