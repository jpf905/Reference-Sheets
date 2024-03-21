## Linking Tables Using JOIN
```SQL
SELECT *
FROM table_1 JOIN table_2
ON table_1.key_column = table_2.key_column

/* Use when you are working with well-structured, 
well-maintained data sets and need to find rows
that exist in only one of the tables.*/
```

### Relating Tables with Key Columns 
**Primary key**= a column or collection of columns whose values uniquely identify each row in a table.

## JOIN Types

### **JOIN with USING**
```SQL
-- JOIN with USING
SELECT *
FROM table1 JOIN table2
USING (id)
ORDER BY table1-key-column1;

/* If you are using identical names for columns in a
JOIN's ON clause, you can reduce redundant output
and simplify the query suntax by substituting
a USING clause in place of the ON clause.*/
```

### **LEFT and RIGHT JOIN**
```SQL
SELECT *
FROM table_1 LEFT JOIN|RIGHT JOIN table_2
ON table_1.key_column = table_2.key_column
ORDER BY table_1.key_column
```

### FULL OUTER JOIN
```SQL
-- FULL OUTER JOIN
SELECT *
FROM table-1 FULL OUTER JOIN table-2
ON table1-key-column1 = table1-key-column2
ORDER BY table1-key-column1;

/* A full outer join is admittedly less useful and used less 
often than inner and left or right joins. Still, you can 
use it for a couple of tasks: to link two data sources that 
partially overlap or to visualize the degree to which 
tables share matching values.*/
```

### CROSS JOIN
```SQL
--CROSS JOIN
SELECT *
FROM district_2020 CROSS JOIN district_2035
ORDER BY district_2020.id, district_2035.id;

/* The result lines up each row in the left table with each row
in the right table to present all possible combinations of rows.
Avoid using a CROSS JOIN query on larg tables! */
```

## Using NULL to Find Rows with Missing Values
```SQL
-- Filtering to show missing values with IS NULL
SELECT *
FROM district_2020 LEFT JOIN district_2035
ON district_2020.id = district_2035.id
WHERE district_2035.id IS NULL;
```

## Selecting Specific Columns in a Join
```SQL
-- Selecting specific columns in a join
SELECT district_2020.id,
         district_2020.school_2020,
         district_2035.school_2035
FROM district_2020 LEFT JOIN district_2035
ON district_2020.id = district_2035.id
ORDER BY district_2020.id;
```

## Simplifying JOIN Syntax with Table Aliases
```SQL
-- Simplifying code with table aliases
SELECT d20.id,
       d20.school_2020,
			 d35.school_2035
FROM district_2020 AS d20 LEFT JOIN district_2035 AS d35
ON d20.id = d35.id
ORDER BY d20.id;
```

## Joining Multiple Tables


## Combining Query Results with Set Operators

```SQL
-- Combining query results with UNION
SELECT * FROM table_1
UNION
SELECT * FROM table_2
ORDER BY specific_column;
```

```SQL
-- Combining query results with  INTERSECT
SELECT * FROM table_1
INTERSECT
SELECT * FROM table_2
ORDER BY specific_column;

/* INTERSECT returns just the rows that exist in the results
of both queries and eliminates duplicates.*/
```

```SQL
-- Combining query results with EXCEPT
SELECT * FROM table_1
EXCEPT
SELECT * FROM table_2
ORDER BY specific_column;

/* EXCEPT returns rows that exist in the first query but not in the second.*/
```
