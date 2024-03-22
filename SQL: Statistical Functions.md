# SQL: Statistical Functions

### Measuring Correlation with corr(Y,X)
```SQL
SELECT corr( column-name-dvariable, column-name-ivariable)
    AS alias-name
FROM table-name;
```
Interpreting Correlation Coefficients
* 0 => no relationship
* .01 to .29 => weak relationship
* .3 to .59 => moderate relationship
* .6 to .99 => strong realtionship
* 1 => perfect relationship

NOTE: 
1. A strong correlation does not imply causality. The change in one variable doesn't necessarily cause a change in the other variable.
The only thing we can say is the changes move together.
2. Correlations should be subject to testing to determin whether they're statistically significant.

```SQL
- Finding slope and Y-intercept
SELECT
    round(
        regr_slope( col1, col2)::numeric, 2
        ) AS slope,
    round(
        regr_intercept(col1, col2)::numeric, 2
        ) AS y_intercept
FROM table-name;
-- Results should be slope = 1016.55 and Y-int = 29651.42
-- Then you can find Y= 106.55(% found in problem) = 29651.42
```

