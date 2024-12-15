SQL-NOTES

Database

A database is a structured collection of data. To store, retrieve, and edit data in a database, you can use a database management system (DBMS), such as MySQL, Microsoft Access, Microsoft SQL Server, FileMaker Pro, Oracle Database, and dBASE.

Relational Database

A relational database defines relationships between tables stored in the database. These relationships allow us to draw conclusions about the data housed in separate tables. Relational databases are far more powerful than Excel spreadsheets, although they may appear similar. They can store significantly more information, ensure data safety through encryption, and support simultaneous access by multiple users without altering the data during queries.

Tables

Tables in databases are named similarly to variables.

Columns -> Fields (The number of fields must be specified during table creation and is fixed.)

Field Name Rules:

Follow variable naming rules.

Avoid plural field names.

Rows -> Records (The number of rows is unlimited.)

Types of Keys

Primary Key: A field that uniquely identifies each record in the table.

Foreign Key: A field that refers to the primary key of another table.

Composite Key: A combination of two or more fields used as a primary key.

Datatypes

INT: Stores integers up to ±2 billion.

VARCHAR: Stores strings.

FLOAT: Stores decimal numbers.

NUMERIC: Stores up to 38 digits.

Schemas

Schemas in SQL are blueprints of the database, providing information about relationships between tables, datatypes used in fields, and the number of fields.

Storage of Data

Data in a database table is physically stored on the hard disk of a server. Servers are centralized computers that perform services via network requests. In this case, the service involves data access. Servers are typically powerful machines designed to handle high volumes of requests and data, but any computer can act as a server when set up to provide services.

SQL Queries

SQL queries are used to retrieve, manipulate, and store data within a relational database. They enable actions like selecting specific data, updating records, inserting new data, and deleting records, acting as a communication tool between users and the database.

Keywords and Syntax

SELECT Syntax

SELECT field_name1, field_name2
FROM table_name;

DISTINCT Syntax

SELECT DISTINCT field_name
FROM table_name;

ALIAS Syntax

SELECT field_name AS alias_name
FROM table_name;

VIEW Syntax

VIEW field_name1, field_name2
FROM table_name;

WHERE Syntax

SELECT field_name
FROM table_name
WHERE condition;

LIMIT Syntax

SELECT field_name
FROM table_name
LIMIT 10;

Conditions

WHERE field = 34

WHERE field = 'string'

WHERE field_name IN (cond1, cond2)

Note: Capitalize keywords for better readability and include a semicolon at the end of statements (preferred but not mandatory).

AND

WHERE field = 45 AND field = 23

OR

WHERE num = 90 OR num = 86

LIKE

WHERE name LIKE "%s"

Matches names ending with "s".

WHERE name LIKE "_s%"

Matches names where the second letter is "s". Similarly, you can use NOT LIKE.

NULL

WHERE id IS NULL

Returns records with a NULL value in the id field. Similarly, IS NOT NULL can be used.

Keyword List

SELECT: Retrieves information from the fields of various tables in the database.

FROM: Specifies the table from which data is to be selected.

DISTINCT: Ensures only unique values are selected.

AS: Creates an alias for a field name in the output.

VIEW: Displays data based on specific criteria.

LIMIT: Limits the number of rows returned in the output.

SQL Flavors

SQL has multiple versions or flavors, some of which are free, while others include customer support and are designed to complement major database systems like Microsoft SQL Server or Oracle Database, widely used by companies.

Selecting Data

COUNT()

Counts the number of records that match the specified criteria.

SELECT COUNT(field_name1), COUNT(DISTINCT field_name2)
FROM table_name;

BETWEEN

Filters records within a specified range.

SELECT roll_no
FROM students
WHERE roll_no BETWEEN 34 AND 78;

Aggregate Functions

Aggregate functions allow summarization of data but are not detailed here.

