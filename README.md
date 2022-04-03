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
|----------|----------------------------------------|-----------------------------------|
| ```BETWEEN```  | Matches value between two others (inc) | ```WHERE column BETWEEN 10 AND 20```       |
| ```DISTINCT``` | Takes out duplicate results            | ```SELECT DISTINCT column```       |
| ```IN```       | Matches to any value within a list     | ```WHERE category IN ('Example')```  |
| ```LIKE```     | Wildcard matching with _ or %          | ```WHERE column LIKE '%This%'```     |


## JOINS

| Keyword  | Usage                                  |
|----------|----------------------------------------|
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

<!-- ## Common Functions
| Keyword | Usage                                 | Format                                       |
|---------|---------------------------------------|----------------------------------------------|
|CAST     | 
|CEIL     |
|CONCAT   |
|FLOOR    |
|FLOOR    |
|GREATEST |
|INITCAP  |
|LEAST    |
|LOWER    |
|MOD      |
|NOW      |
|REPLACE  |
|ROUND    |
|TRIM     |
|UPPER    | -->

<!-- ## Aggregate Functions -->

## Hints and Tips

### Restarting the PSQL server
```
#restart PostgreSQL service
sudo service postgresql restart
```
And in case that's not enough, refer to [this](https://stackoverflow.com/questions/31645550/postgresql-why-psql-cant-connect-to-server)

### Case Conventions

You don't have to capitalise keywords, but convention dictates that they are capitalised, and values are not.

### Quote Marks

SQL likes single quotes. It really does not like double quotes.

### Semicolons

End your query with a semicolon to tell SQL you're done. You can get away with it if it's only a single query and nothing else, but really, it's not worth it.
