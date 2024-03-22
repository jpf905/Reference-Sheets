# SQL: Advanced Query Techniques

## Using Subqueries

```SQL
-- Using a subquery in a WHERE clause
SELECT column1,
       column2,
       column3
FROM table-name
WHERE column3 >= (
    SELECT percentile_cont(.9) WITHIN GROUP (ORDER BY column3)
    FROM table-name
    )
ORDER By column3 DESC;
```

MORE
