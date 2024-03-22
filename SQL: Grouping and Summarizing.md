# Grouping and Summarizing

## Exploring the Data Using Aggregate Functions

### Counting Rows with count()
```SQL
SELECT count(*)
FROM table-name;
```

### Counting Values Present in a Column
```SQL
SELECT count(specific-value)
FROM table-name;
```

### Counting Distinct Values in a Column
```SQL
SELECT count(DISTINCT specific-value)
FROM table-name;
-- DISTINCT is great for removing duplicates
```

### Finding Maximum and Minimum Values
```SQL
SELECT max(column-name), min(column-name
FROM table-name;
```
### Using GROUP BY
```SQL
SELECT column-name1
FROM table-name
GROUP BY column-name1
ORDER BY column-name1
```

### Combining GROUP BY with count()
```SQL
SELECT column-name1, count(*)
FROM table-name
GROUP BY columne-name1
ORDER BY count(*) DESC;
```

### Using GROUP BY on Multiple Columns with count()
```SQL
SELECT column1, column2, column3, count(*)
FROM table-name
GROUP BY column1, column2
ORDER BY column1, column2;
```
### Use a WHERE clause to filter out negative values
```SQL
-- Example
SELECT sum(visits) AS visits_2018
FROM table-name
WHERE visits >= 0;
```
### Filtering Aggregate Functions with HAVING
