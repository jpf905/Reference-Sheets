# SQL: Advanced Query Techniques

## Using Subqueries

### Filtering subqueries in a WHERE clause
#### Generating values for a query expression
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
#### Using a subquery to identify rows to delete


### Creating Derived Tables with Subqueries
If your subquery returns rows and columns, you can place it in a FROM\
clause to create a new table known as a **derived table** that you can query\
or join other tables.
MORE

