## SQL

```sql
-- Write only the SQL statement that solves the problem and nothing else
SELECT r.name as rname, avg(isnull(ss.amount, 0)) as average, (SELECT TOP 1 avg(ss.amount) as avgamount FROM regions as r LEFT JOIN states as s
  ON r.id = s.regionId
  LEFT JOIN employees as e
  ON s.id = e.stateId
  LEFT JOIN sales as ss
  ON e.id = ss.employeeId
  GROUP BY r.name
  ORDER BY avgamount desc) - avg(isnull(ss.amount, 0)) as difference
  FROM regions as r LEFT JOIN states as s
  ON r.id = s.regionId
  LEFT JOIN employees as e
  ON s.id = e.stateId
  LEFT JOIN sales as ss
  ON e.id = ss.employeeId
  GROUP BY r.name
```
