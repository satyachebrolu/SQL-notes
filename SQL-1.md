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
**SELECT** field_name1, field_name2,....  
**FROM** table_name ;

### DISTINCT Syntax
**SELECT** **DISTINCT** field_name   
**FROM** table_name;

### ALIAS Syntax
**SELECT** field_name **AS** alias_name  
**FROM** table_name;

### VIEW Syntax
**VIEW** field_name1, field_name2 
**FROM** table_name;

### WHERE Syntax
**SELECT** fiel_name
**FROM** table_name
**WHERE** (condition);

```SQL
These conditions can be given in different ways :  
-equal to sign(=)  
-IN statement i.e WHERE field_name IN (cond1, cond2)
```
`Make sure to capitalize the keywords to make the code easier to understand.`

## List of all the keywords

- SELECT : To retrieve information from the fields of various tables in the database.
- FROM : To select the table from which we want to select the data.
- DISTINCT : To select only the unique attributes present in the field chosen.
- AS : Aliasing the fieldname in the output panel.
- VIEW : Used to view the data of your specifications from the table.
