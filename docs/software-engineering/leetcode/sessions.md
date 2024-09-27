## SQL

```sql
-- Write only the SQL statement that solves the problem and nothing else
SELECT userId, avg(duration)
FROM sessions
GROUP BY userId
HAVING count(id) > 1
```
