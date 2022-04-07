# PostgreSQL Cheat Sheet

## SELECT Query
```
SELECT table1.*, table2.column2
FROM table1
JOIN table2 ON table1.column2 = table2.column2
WHERE condition
GROUP BY column_name
HAVING condition
ORDER BY table2.column1 ASC|DESC;
```

## SELECT Keywords

| Keyword  | Usage                                  | Format
|:---------|:---------------------------------------|:----------------------------------|
| ```BETWEEN```  | Matches value between two others (inc) | ```WHERE column BETWEEN 10 AND 20```       |
| ```DISTINCT``` | Takes out duplicate results            | ```SELECT DISTINCT column```       |
| ```IN```       | Matches to any value within a list     | ```WHERE category IN ('Example')```  |
| ```LIKE```     | Wildcard matching with _ or %          | ```WHERE column LIKE '%This%'```     |


## JOINS

| Keyword  | Usage                                  |
|:---------|:---------------------------------------|
| ```INNER JOIN```  | Shows matching records in both tables (Shortcut keyword: ```JOIN```) |
| ```LEFT JOIN``` | Shows all records from left (first) table and matching ones from the right |
| ```RIGHT JOIN```       | Shows all records from right (second) table and matching ones from the left |
| ```FULL OUTER JOIN```     | Sows all records from both tables whether they have a match in the other table or not |

![Joins Venn Diagram](https://github.com/ZanClifton/postgresql-cheat-sheet/blob/main/images/sql-joins.png)

## CASE Statement

```
CASE
  WHEN column1=value1 THEN value3
  WHEN column1=value2 THEN value4
  ELSE 'Unknown'
END
```

## Common Functions
| Keyword | Usage                                 | Format                                       |
|:--------|:--------------------------------------|:---------------------------------------------|
|```CAST```     | Converts expression to data type specified | ```CAST(expression AS DATATYPE)```            |
|```CEIL```     | Rounds up to nearest integer | ```CEIL(input_value)``` |
|```CONCAT```   | Combines two or more strings into one | ```CONCAT('string1 ', 'string2 ', 'string 3')```
|```FLOOR```    | Rounds down to nearest integer | ```FLOOR(input_value)``` |
|```GREATEST``` | Returns greatest of a list of expressions | ```GREATEST(1,2,3,4,5)``` 
|```INITCAP```  | Capitalises the first letter of each word in a string | ```INITCAP('firstword secondword')``` |
|```LEAST```    | Returns least of a list of expressions | ```LEAST(1,2,3,4,5)``` |
|```LENGTH```   | Returns number of characters in a string | ```LENGTH('string')``` |
|```LOWER```    | Converts all characters in a string to lowercase | ```LOWER('STRING')``` |
|```MOD```      | Returns the remainder of a division (modulo) | ```MOD(number, divisor)``` 
|```NOW```      | Returns the current date and time | ```NOW```
|```REPLACE```  | Replaces all or part of a string with another | ```REPLACES('string', 'string to replace' or 0, 'replacement')``` |
|```ROUND```    | Rounds floating point number mathematically | ```ROUND(input_value)``` |
|```TRIM```     | Trims strings of excess spaces at the start and end | ```TRIM('  string    ')``` |
|```TRUNC```    | Truncates a number to specified decimal places | ```TRUNC(input_value, decimals)``` |
|```UPPER```    | Converts all characters in a string to uppercase | ```UPPER('string')``` |

## Aggregate Functions

Where an aggregate function is used and additional columns are selected, you must ```GROUP BY``` the other columns you wish to return. If you ```GROUP BY``` a ```PRIMARY KEY``` it is not required to include the other columns.

| Keyword | Usage                                 | Format                                       |
|:--------|:--------------------------------------|:---------------------------------------------|
|```AVG```     | Returns the average of a set of values  | ```AVG(set)``` |
|```COUNT``` | Returns the number of rows in a specified table or view | ```COUNT(rows)``` |
|```MAX``` | Returns the maximum value in a set of values | ```MAX(set)``` |
|```MIN``` | Returns the minimum value in a set of values | ```MIN(set)``` |
|```SUM``` | Returns the sum of a set of values | ```SUM(set)``` |
|```  

### DISTINCT / ALL

```aggregate_function (DISTINCT | ALL expression)```

If you use the ```ALL``` modifier, the aggregate function will use all available values in the set for its calculation or evaluation. In contrast, ```DISTINCT``` causes the aggregate function to ignore duplicate values and only consider the unique ones.

<!-- ## Constraints -->

## Hints and Tips

### Restarting the PSQL server
```
#restart PostgreSQL service
sudo service postgresql restart
```
And in case that's not enough, refer to [this](https://stackoverflow.com/questions/31645550/postgresql-why-psql-cant-connect-to-server).

### Case Conventions

You don't have to capitalise keywords, but convention dictates that they are capitalised, and values are not.

### Quote Marks

SQL likes single quotes. It really does not like double quotes.

### Semicolons

End your query with a semicolon to tell SQL you're done.
