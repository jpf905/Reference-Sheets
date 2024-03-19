# Basic Data Exploration with SQL

## Using SELECT
  
  ``` SQL
  SELECT * FROM  table-name;
```

## Querying a Subset of Columns
``` SQL
SELECT some_column, another_column, amazing_column FROM table_name;
```
  
## Sort Data with ORDER BY
```SQL
SELECT column_name, another_column, yet_another_column
FROM table-name
ORDER BY column(s)_u_want_to_order | or_index_of_column_listed_above ; 
```
## Using DISTINCT to Find Unique Values
``` SQL
SELECT  DISTINCT column_name(s)
FROM table_name
ORDER BY column_name(s);
```

## Filtering Rows with WHERE
``` SQL
SELECT column_name(s)
FROM table_name
WHERE column_name  =\<\>\<> (any operator) column_name;
```
## Using ILIKE with WHERE
``` SQL
SELECT column_name
FROM table_name
WHERE column_name ILIKE 'something%' ;
```

## Combining Operators with  AND and OR

## Order of Keywords in SQL
``` SQL
SELECT column_names
FROM table_name
WHERE criteria
ORDER BY column_names;
```
