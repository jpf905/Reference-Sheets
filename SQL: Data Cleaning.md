# Data Cleaning with SQL

## Step 1: Import

## Step 2: Interview

### Check for missing values.
* Involves checking for NULL values.
  ```SQL
  -- Check for missing values
  SELECT col1,col2, col3, etc
  FROM table-name
  WHERE col1 IS NULL;
  ```
### Check for inconsistent values.
* This will often times be variation in spelling of names or other attributes.
  ```SQL
  -- Check for inconsistent values with GROUP BY and count()
  SELECT column-name,
          count(*) AS alias-name
  FROM table-name
  GROUP BY column-name
  ORDER BY column-name;
  ```
### Check for malformed values using length()
* This involves cheking for unexpected values in a column that should be consistently formatted.
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
* This occurs when you have missing values in a column.
**1.** Creating a Column Copy.
     Good idea do to make a column copy first so you don't lose the original.
     Do this even if you have already made a backup copy of the table.
```SQL
-- Creating a column copy
ALTER TABLE table-name ADD COLUMN column-copy-name data-type;

UPDATE tabl-name
SET column-copy-name = original-col-values;
```
  **2.** Updating Rows Where Values Are Missing
```SQL
-- Example
UPDATE meat_poultry_egg_establishments
SET st = 'MN'
WHERE establishment_number = 'V18677A';
```
  **3.** Restoring Original Values
      Useful if we botch an update by providing the wrong values or updating the wrong rows.
      We simply copy the data from either the full table backup or the column backup.
      
### Updating Values for Consistency
  * Can use UPDATE statement to standardize spelling in a column.
  * Repair zip codes with concatenation

## Deleteing Unneeded Data
ALWAYS backup your data! SQL has options to remove row and columns along with options to delete an entire table or database.

### Deleting Rows from a Table
```SQL
-- Deleting rows from a table
DELETE FROM table-name;

-- Deleting only selected rows from a table
DELETE FROM table-name WHERE expression;

-- Deleting large tables
TRUNCATE table_name;

-- Reset an IDENTITY sequence (one you created as a surrogate primary key)
TRUNCATE table-name RESTART IDENTITY;
```

### Deleting a Column from a Table
```SQL
-- Deleting a column from a table
ALTER TABLE table-name DROP COLUMN column-name;
```

### Deleting a Table from a Database
Useful when you have a collection of backups that are no longer needed.  It is also useful  
when you need to change the structure of a table significantly. Rather than so many ALTER TABLE  
statements, you can just remove the table and create a fresh one.
```SQL
DROP TABLE table_name;
```

## Using Transactions to Save or Revert Changes
The alterations above are final.  Here we have a way to check our changes before finalizing them  
and cancel the change if it isn't what we need. There is a way to check your changes before finalizing them and cancel the change if it’s not what you intended. You do this by enclosing the SQL statement within a transaction, which includes keywords that allow you to commit your changes if they are successful or roll them back if not. You define a transaction using the following keywords at the beginning and end of the query:

START TRANSACTION: Signals the start of the transaction block. In PostgreSQL,  
you can also use the non-ANSI SQL BEGIN keyword.  

COMMIT: Signals the end of the block and saves all changes. 

ROLLBACK: Signals the end of the block and reverts all changes.

```SQL
--Example
-- Start transaction and perform update
START TRANSACTION;

UPDATE meat_poultry_egg_establishments
SET company = 'AGRO Merchantss Oakland LLC'
WHERE company = 'AGRO Merchants Oakland, LLC';

-- view changes
SELECT company
FROM meat_poultry_egg_establishments
WHERE company LIKE 'AGRO%'
ORDER BY company;

-- Revert changes
ROLLBACK;

-- See restored state
SELECT company
FROM meat_poultry_egg_establishments
WHERE company LIKE 'AGRO%'
ORDER BY company;

-- Alternately, commit changes at the end:
START TRANSACTION;

UPDATE meat_poultry_egg_establishments
SET company = 'AGRO Merchants Oakland LLC'
WHERE company = 'AGRO Merchants Oakland, LLC';

COMMIT;
```

## Improving Perfomance When Updating Large Tables

