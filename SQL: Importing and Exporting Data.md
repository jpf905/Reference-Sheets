# Importing and Exporting Data

## Fundamental Steps for Importing
  1. Create DB
  2. Create table (column names and data types)
  3. IMport using COPY and WITH
  4. Inspect import

## Working with Delimited Text Files
 * A delimited text file contains rows of data, each of which represents one row in a table. In each row, each data column is separated (delimited) by a particular character.
 * A header row is a single row at the top (head) of the fle that lists the name of each data column. Often included in the export of the data file.

### Quoting Columns That Contain Delimiters
Delimited text files use an arbitrary character called a *text quantifier* to enclose a column that include the delimiter character. Most of the time in comma-delimited files the text quantifier used is the double quote.

## Using COPY to Import Data

```SQL
COPY table_name
FROM 'file path'
WITH (FORMAT CSV, HEADER);
-- Note that including HEADER excludes the heard row in the import
```
**Options you will commonly use in an import:**
1. Input and output file format
2. Presence of a header row
3. Delimiter
4. Quote character

## Inspecting the Import
It is always good to inspect the import for a few things:
* Does each column have the expected values?
* Are the data types correct and consistent?
* Null values


## Importing a Subset of Columns with COPY
```SQL
COPY table_name (column1, column2)
FROM 'file path'
WITH (FORMAT CSV, HEADER)
```
## Importing a Subset of Rows with COPY
```SQL
COPY table_name (column1, column2)
FROM 'file path'
WITH (FORMAT CSV, HEADER)
WHERE column_name = 'specific entry';
```

## Adding a Value to a Column During Import
**Temporary table** 


## Using COPY to Export Data
Same format as importing, except you use TO where you originally used FROM.
You can export in three different ways:
1. Export all data
2. Export particular columns
3. Export query results
