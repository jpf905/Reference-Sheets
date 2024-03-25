# Table Design
## Controlling Column Values with Constraints
**Primary key** is column or collection of columns whose values uniquely identify each row in a table.\
As a constraint it does the following:
* Values must be unque for each row.
* No column can have missing values.
  
Primary keys are in two forms:
* Natural key
* Surrogate key

*A **Natural key** uses one or more of the table's existing columns that meet the criteria for a primary key.\
  Values can change but the change cannot violate the constraint, e.g., a driver's license number.\
  A **surrogate key** is a single column that you fill with artificial values.\
  We use it when a table doesn't have data that supports creating a natural primary key.

There are two ways to declare a constraint:  as a column constraint or as a table constraint.
```SQL
-- Adding a Column Constraint
CREATE TABLE natural_key_example (
  column1-name text CONSTRAINT constraint-name PRIMARY KEY,
  column2-name text,
);


-- Adding a Table Constraint
CREATE TABLE natural_key_example (
  column1 text,
  column2 text,
  CONSTRAINT constraint-name PRIMARY KEY(column1)
);
```
#### Creating a Composite Primary Key
We create a composite primary key if a single column doesn't meet the requirements\
for a primary key.
```SQL
-- Creating a composite primary key
CREATE TABLE table_name (
  column1 text,
  column2 text,
  CONSTRAINT constraint-name PRIMARY KEY (column1, column2)
);
```
more
  
