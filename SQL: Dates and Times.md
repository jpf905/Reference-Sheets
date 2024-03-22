# SQL: Working with Dates and Times
Four SQL data types related to dates and times:
* *timestamp*
* *date*
* *time*
* *interval*

### Extracting the Components of a timestamp Value
```SQL
-- Extracting Components of timestamp value
date_part(text, value)

-- Another alternative but not widely supported with other DB managers
extract(time-name from value-name)
```

### Creating Datetime Values from timestamp Components
PostgreSQL functions to make datetime objects:
* **make_date(year, month, day)** Returns a value of type date.
* **make_time(hour, minute, seconds)** Returns a value of type time without time zone.
* **make_timestamptz(year, month, day, hour, minute, second, time zone)** Returns a timestamp with time zone.  
  
The variables for these three functions take integer types as input, with two exceptions:  
1. Seconds are of the type double precision because you can supply fractions of seconds,
2. Time zones must be specified with a text string that names the time zone.

### Retreiving the Current Data and Time
The following functions record the time as of the start of the query:
* **current_timestamp** Returns the current timestamp with time zone. A shorthand PostgreSQL-specific version is now().
* **localtimestamp** Returns the current timestamp without time zone.
  Avoid using localtimestamp, as a timestamp without a time zone can’t be placed in a global location and is thus meaningless.
* **current_date** Returns the date.
* **current_time** Returns the current time with time zone.
  Remember, though, without a date, the time alone with a time zone is useless.
* **localtime** Returns the current time without time zone.

### Working with Time Zones
```SQL
-- Finding your time zone setting
SHOW timezone;
SELECT current_setting('timezone');
```

## Performing Calculations with Dates and Times
more
