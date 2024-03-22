# Data Cleaning with SQL

## Step 1: Import

## Step 2: Interview
* Check for missing values.
  ```SQL
  -- Check for missing values
  SELECT col1,col2, col3, etc
  FROM table-name
  WHERE col1 IS NULL;
  ```
* Check for inconsistent values.
  ```SQL
  -- Check for inconsistent values with GROUP BY and count()
  SELECT column-name,
          count(*) AS alias-name
  FROM table-name
  GROUP BY column-name
  ORDER BY column-name;
  ```
* Check for malformed values.
  ```SQL
  -- Check for malformed values using length()
  SELECT length(col1)
          count(*) AS alias-name
  FROM table-name
  GROUP BY length(col1)
  ORDER BY length(col1);
  ```
## Step 3: Modfiying Tables, Columns, and Data

### Modifying Tables with ALTER TABLE
```SQL
-- Adding a column
ALTER TABLE table-name ADD COLUMN column-name data_type;

-- Deleting a column
ALTER TABLE table-name DROP COLUMN column-name;

-- Changing the data type of a column
ALTER TABLE table-name ALTER COLUMN column-name SET DATA TYPE data_type;

-- Adding a NOT NULL constraint
ALTER TABLE table-name ALTER COLUMN column-name SET NOT NULL;
```
### Modifying Values with UPDATE

```SQL
--Modfying a single column
UPDATE table-name
SET column-name = value;

-- Modifying multiple columns
UPDATE table-name
SET col1 = value,
    col2 = value;

--Resticting update to particular rows
UPDATE table-name
SET column-name = value
WHERE criteria-description;
```
### Viewing Modified Data with RETURNING
If you add an optional RETURNING clause to UPDATE, you can view the values that were modified  
without having to run a second, separate query.
```SQL
--Viewing modified data
UPDATE table-name
SET column1 = value
RETURNING column1, column2, column3;
```

### Creating Backup Tables
Before modifying a table it is a good idea to make a backup copy for reference.
```SQL
-- Creating a backup table
CREATE TABLE backup-table-name AS
SELECT * FROM table-name;

--NOTE: Indexes are not copied when creating a table using this method.
```

### Restoring Missing Column Values

  
