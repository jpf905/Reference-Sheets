# SQL Data Types

## I. Characters
Character types include:
*text*
*varchar()*

## II. Numbers
Two number types:
**1. Integers**
      Three types of integers:
      *smallint*
      *intger*
      *bigint*
**2. Decimals**
      Two types of decimals:
      Fixed-point
        *numeric (precision, scale)*
        *decimal*
      Floating-point
        *real*
        *double precision*
### Choosing Your Number Type
* Use integers when possible.
* If working with decimal data and need exact calculations, use *numeric* or *decimal*.
* Choose a big enough data type. Unless you're working on a huge database, err on the side of larger data types.

## III. Dates and Times
Four data types for times and dates:
*timestamp* = record date and time
*date* = records just date
*time* = records just time
*interval* = records value of a unit of time in the format *quantity unit*.
      
