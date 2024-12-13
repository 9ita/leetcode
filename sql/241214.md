https://leetcode.com/problems/managers-with-at-least-5-direct-reports/?envType=study-plan-v2&envId=top-sql-50

## 내 풀이
```sql
select name from Employee where id in (select sub.managerId from (select managerId, count(*) cnt from Employee group by managerId having cnt >= 5) sub)
```

## 다른 풀이
```sql
SELECT b.name
FROM Employee a
JOIN Employee b ON a.managerId = b.id
GROUP BY b.id
HAVING COUNT(*) >= 5
```
