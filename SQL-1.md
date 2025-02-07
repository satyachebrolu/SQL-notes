# SQL-NOTES

## Database

A database is a structured collection of data. To store, retrieve, and edit data in a database, you can use a database management system (DBMS). For example MySQL, Microsoft Access, Microsoft SQL Server, FileMaker Pro, Oracle Database, and dBASE.

## Relational Database

It defines relations between the tables stored in the database. Through these we can draw conclusions about the data housed in seperate tables in the database. These are far more powerful than Excel Spreadsheets despite being similar to them. They can store much more information and the data stored is safe due to encryption. Many people can store information at the same time and when a query is written the data inside the database does not get altered.

## Tables

We name the table name just like variables.
- Coloums -> Fields (No: of fields should be specified while creating the table ad is definite).
- Field name rules:
1. Follow variable naming rules.
2. The field names should not be plural.
- Rows -> Records (No: of rows is unlimited).

## Types of keys

1. Primary Key: A field that identifies each record in the table as unique.
2. Foreign Key : When the primary key of another table is called in the current view its called a foreign key.
3. Composite Key : When the combination of any two rows is used as a Primary key , the combination is known as a composite key.

## Datatype

1. INT-stores upto 2 billion positive and negative.
2. VARCHAR- Stores strings.
3. FLOAT.
4. NUMERIC- 38 digits.

## Schemas

Schemas in SQL refer to blueprints of the database. You get an idea of the relations between various tables , the datatypes used in different fields and also the number fields etc.

## Storage of data

The information we find in a database table is physically stored on the hard disk of a server. Servers are centralized computers that perform services via requests made over a network. In our case, the service performed is data access, but servers are also used to access websites or files stored on the server. Any computer can be a server if it is set up to provide a service, even a laptop! However, servers are generally very powerful and large machines, because they are best equipped to handle a high volume of requests and data.

## SQL Queries

SQL queries are used to retrieve, manipulate, and store data within a relational database, allowing users to perform actions like selecting specific data, updating existing records, inserting new data, and deleting records from tables, effectively acting as a communication tool between the user and the database to manage information within it. 

## Keywords and Their Syntax

### Syntax
```sql
SELECT field_name1, field_name2,....  
FROM table_name ;
```

### DISTINCT Syntax
```sql
SELECT DISTINCT field_name   
FROM table_name;
```

### ALIAS Syntax
```sql
SELECT field_name AS alias_name  
FROM table_name;
```

### VIEW Syntax
```sql
VIEW field_name1, field_name2 
FROM table_name;
```

### WHERE Syntax
```sql
SELECT field_name
FROM table_name
WHERE (condition);
```

### LIMIT Syntax
```sql
SELECT field_name
FROM table_name
LIMIT 10;
```

### These conditions can be given in different ways :  
- **WHERE** field = 34
- **WHERE** field = 'string'  
- **IN** statement i.e **WHERE** field_name **IN** (cond1, cond2)


`Make sure to capitalize the keywords to make the code easier to understand.`  
`The semicolon at the end is not necessary but its preferred to use it.`

### AND 
```SQL
WHERE field = 45 AND field = 23
```

### OR 
```SQL
WHERE num = 90 OR num = 86
```

### LIKE
```sql
WHERE name LIKE "%s"
```
This gives all the names ending with a s.
```sql
WHERE name LIKE "_s%"
```
This gives the names whose second letter is s.  
Similarly you can use **NOT LIKE** too.

### NULL
```sql
WHERE id IS NULL
```
Returns all the records with a null id.  
Similarly there is **IS NOT NULL** too.

## KEYWORD LIST : 

- SELECT : To retrieve information from the fields of various tables in the database.
  
- FROM : To select the table from which we want to select the data.

- DISTINCT : To select only the unique attributes present in the field chosen.
  
- AS : Aliasing the fieldname in the output panel.

- VIEW : Used to view the data of your specifications from the table.

- LIMIT : Used to limit the output to the number of rows required.

## SQL Flavors

SQL has a few different versions, or flavors. Some are free, while others have customer support and are made to complement major databases such as Microsoft's SQL Server or Oracle Database, which are used by many companies.

# Selecting data

## COUNT() :

This is used to count the number of required with the specifications you have entered.
### Syntax
```sql
SELECT COUNT(fieldname1), COUNT(DISTINCT fieldname2)
FROM tablename
```
This can also be used along with **DISTINCT** .  

## BETWEEN :

This is used to filter the records with the give condition.

### Example
```sql
SELECT roll_no
FROM students
WHERE roll_no BETWEEN 34 AND 78;
```

# Aggregate Functions

## AVG() , SUM() , MIN() , MAX() , COUNT() 
### Syntax
```sql
SELECT SUM(fieldname)
FROM tablename
```
Similar syntax can be used for the other functions. While AVG() and SUM() can only be used for numerical values the rest i.e MIN() , MAX() and COUNT() can be used for various datatypes. For alphabets the minimum value would be 'A', the maximum being 'Z' . 

## ROUND()
### Syntax
```sql
SELECT ROUND(AVG(fieldname), 2 ) AS aliasname
FROM tablename
```
This rounds off the value to 2 decimal places. When we don't specify a number it gets rounded off to a whole number (same happens when the number is 0).  
When the number is a negative number it gets rounded off to the tens (-1), hundreds (-2) , thousands (-3) and so on. 

### We can use arithmetic functions to do operations on the fields too.
### Syntax
```sql
SELECT (field1 * field2) AS aliasname
FROM tablename
```
# Sorting Results
## ORDER BY 
### Syntax
```sql
SELECT fieldname1, fieldname2
FROM tablename
ORDER BY fieldname1
```
We can also choose the order in which it is order , for example 
### Example
```sql
SELECT title, budget
FROM theatre
ORDER BY budget ASC , title ASC
```
ASC or DESC can be used.
## GROUP BY 
### Syntax
```sql
SELECT field1 , field3, COUNT(field2)
FROM tablename
GROUP BY field1
```
This shows the count of unique combinations of entities of field1 and field3. 
## HAVING 
### Syntax
```sql
SELECT field1, COUNT(field2) AS aliasname
FROM tablename
GROUP BY field1
HAVING COUNT(field2) > 10
```
WHERE filters individual records whereas HAVING filters grouped records.
# Joining Data
## INNER JOIN 
looks for records on both tables wich match on a given field.
### Syntax
```sql
SELECT table2.f1 , table2.f2 , field1, field2
FROM table1
INNER JOIN table2
ON table1.field = table2.f1
```
### Example
```sql
SELECT p2.country , p2.continent , prime_minister , president
FROM presidents AS p1
INNER JOIN prime_minister AS p2
ON p1.country = p2.country                          
```
```sql
SELECT p2.country , p2.continent , prime_minister , president
FROM presidents AS p1
INNER JOIN prime_minister AS p2
USING(country)
```
Both of them give the same result.
## Relationships
### One-to-Many
one record is related to many records in the other table.  
Example : Author and books written by the author.
### One-to-One
one record is related on to only one record on the other table 
Example : Finger and fingerprint.
### Many-to-Many 
Many records are related to many other records in the other table.
Example : Languages spoken in different countries.
## Multiple Joins
### Join on Joins
### Syntax
```sql
SELECT *
FROM left_table
INNER JOIN right_table
ON left_table.id = right_table.id
   AND left_table.terms = right_table.terms
INNER JOIN another_table
ON left_table.id = another_table.id
```
## OUTER JOINS
### Left Join 
It will return all the values of the left table , and those records of the right table that match on the joining field provided.
### Syntax
```sql
SELECT p2.country , p2.continent , prime_minister , president
FROM presidents AS p1
LEFT JOIN prime_minister AS p2
USING(country)
```
LEFT JOIN can also be written as LEFT OUTER JOIN .
### Right Join
It will return all the values of the right table , and those records of the left table that match on the joining field provided.
### Syntax
```sql
SELECT p2.country , p2.continent , prime_minister , president
FROM presidents AS p1
RIGHT JOIN prime_minister AS p2
USING(country)
```
It can also be written as RIGHT OUTER JOIN .  
Any Right Join can be written as a Left Join.
### Full Join
It is a combination of Right Join and Left Join.
### Syntax
```sql
SELECT p2.country , p2.continent , prime_minister , president
FROM presidents AS p1
FULL JOIN prime_minister AS p2
USING(country)
```
FULL OUTER JOIN can also be used.
### Cross Join
It creates all the possible combinations between left table and right table.
### Syntax
```sql
SELECT id1, id2
FROM table1
CROSS JOIN table2
```
### Self Join 
They are used to compare parts of the same table
### Syntax
```sql
SELECT
   p1.country AS country1
   p2.country AS country2
   p1.continent
FROM prime_ministers AS p1
SELF JOIN prime_ministers as p2
USING(continent)
   AND p1.country <> p2.country
```
'<>' is not equal to symbol
## SET THEORY IN SQL
### UNION
It takes two tables as input and return all the records from  both tables.
### Syntax
```sql
SELECT field1.1, field2
FROM table1
UNION 
SELECT field1.2,field2
FROM table2
```
### UNION ALL
It does the same as above but also returns the duplicate values.
### Syntax
```sql
SELECT *
FROM table1
UNION ALL
SELECT *
FROM table2
```
### INTERSECT
Return the records that are the same in both the tables.
### Syntax
```sql
SELECT field1.1, field2
FROM table1
INTERSECT
SELECT field1.2,field2
FROM table2
```
### EXCEPT 
Return records on the first table that are not there on the second table.
### Syntax
```sql
SELECT field1.1, field2
FROM table1
EXCEPT
SELECT field1.2,field2
FROM table2
```
## Subqueries
### SEMI JOIN 
Chooses records in the first table where a condition is met in the second table.
### Syntax
```sql
SELECT president, country, continent
FROM presidents
WHERE country IN
    ( SELECT country
      FROM states
      WHERE indep_year < 1800 )
```
### ANTI JOIN 
It is the opposite of a SEMI JOIN 
### Syntax
```sql
SELECT president, country, continent
FROM presidents
WHERE country NOT IN
    ( SELECT country
      FROM states
      WHERE indep_year < 1800 )
```
" NOT IN " is used.
### Subqueries inside WHERE
The type we have seen above.
### Syntax
```sql
SELECT *
FROM some_table
WHERE some_field IN
       ( include subquery here )
```
### Subqueries inside SELECT 
### Example
```sql
SELECT continent,
      (SELECT COUNT(*)
       FROM monarchs
       WHERE state.continent = monarch.continent)
FROM states
```
### Subqueries inside FROM 
### Example
```sql
SELECT DISTINCT monarch.continent , sub.recent
FROM monarch
     ( SELECT continent , MAX(indep_year) AS recent
       FROM states
       GROUP BY continent) AS sub
WHERE sub.continent = monarch.continent
```
# Data Manipulation 
## CASE Statements 
Contains WHEN , THEN , ELSE , END
