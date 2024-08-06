# MySQL Interview Q&A Cheatsheet

## Table of Contents
1. [General Concepts](#general-concepts)
   - [SQL vs MySQL](#sql-vs-mysql)
   - [What is SQL?](#what-is-sql)
   - [What is MySQL?](#what-is-mysql)
2. [Basic Queries](#basic-queries)
   - [SELECT](#select)
   - [WHERE](#where)
   - [AND, OR, NOT](#and-or-not)
   - [ORDER BY](#order-by)
   - [INSERT INTO](#insert-into)
   - [NULL Values](#null-values)
   - [UPDATE](#update)
   - [DELETE](#delete)
   - [LIMIT](#limit)
3. [Aggregate Functions](#aggregate-functions)
   - [MIN and MAX](#min-and-max)
   - [COUNT, AVG, SUM](#count-avg-sum)
4. [String Functions](#string-functions)
   - [LIKE](#like)
   - [Wildcards](#wildcards)
5. [Advanced Queries](#advanced-queries)
   - [IN](#in)
   - [BETWEEN](#between)
   - [Aliases](#aliases)
   - [Joins](#joins)
   - [INNER JOIN](#inner-join)
   - [LEFT JOIN](#left-join)
   - [RIGHT JOIN](#right-join)
   - [CROSS JOIN](#cross-join)
   - [Self Join](#self-join)
   - [UNION](#union)
   - [GROUP BY](#group-by)
   - [HAVING](#having)
   - [EXISTS](#exists)
   - [ANY, ALL](#any-all)
6. [Other Important Concepts](#other-important-concepts)
   - [INSERT SELECT](#insert-select)
   - [CASE](#case)
   - [Null Functions](#null-functions)
   - [Comments](#comments)
   - [Operators](#operators)
7. [Data Science-Specific Questions](#data-science-specific-questions)
   - [Normalization vs Denormalization](#normalization-vs-denormalization)
   - [Indexes](#indexes)
   - [Views](#views)
   - [Stored Procedures](#stored-procedures)
   - [Transactions](#transactions)
   - [Window Functions](#window-functions)
   - [CTEs (Common Table Expressions)](#ctes-common-table-expressions)
   - [Temporary Tables](#temporary-tables)
8. [Security Concepts](#security-concepts)
   - [SQL Injection](#sql-injection)
9. [Important Data Science Interview Questions](#important-data-science-interview-questions)

## General Concepts

### SQL vs MySQL
**Q:** What is the difference between SQL and MySQL?  
**A:** SQL (Structured Query Language) is a standard language for managing and manipulating databases. MySQL is a relational database management system (RDBMS) that uses SQL to query databases.

### What is SQL?
**Q:** What is SQL?  
**A:** SQL (Structured Query Language) is a programming language used to manage and manipulate relational databases.

### What is MySQL?
**Q:** What is MySQL?  
**A:** MySQL is an open-source relational database management system (RDBMS) that uses SQL to manage databases.

## Basic Queries

### SELECT
**Q:** What does the SELECT statement do?  
**A:** The SELECT statement is used to select data from a database.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name;
```

### WHERE
**Q:** What is the purpose of the WHERE clause?  
**A:** The WHERE clause is used to filter records.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### AND, OR, NOT
**Q:** How are AND, OR, and NOT used in SQL?  
**A:** They are logical operators used to combine multiple conditions in a WHERE clause.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2;
```

### ORDER BY
**Q:** What does the ORDER BY clause do?  
**A:** The ORDER BY clause is used to sort the result set.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC|DESC];
```

### INSERT INTO
**Q:** How do you insert new data into a table?  
**A:** Using the INSERT INTO statement.

**Syntax:**
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

### NULL Values
**Q:** What are NULL values?  
**A:** NULL values represent missing or unknown data.

### UPDATE
**Q:** How do you update existing data in a table?  
**A:** Using the UPDATE statement.

**Syntax:**
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### DELETE
**Q:** How do you delete data from a table?  
**A:** Using the DELETE statement.

**Syntax:**
```sql
DELETE FROM table_name
WHERE condition;
```

### LIMIT
**Q:** What does the LIMIT clause do?  
**A:** The LIMIT clause specifies the number of records to return.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
LIMIT number;
```

## Aggregate Functions

### MIN and MAX
**Q:** What do the MIN and MAX functions do?  
**A:** MIN returns the smallest value and MAX returns the largest value in a set.

**Syntax:**
```sql
SELECT MIN(column_name) FROM table_name;
SELECT MAX(column_name) FROM table_name;
```

### COUNT, AVG, SUM
**Q:** What do the COUNT, AVG, and SUM functions do?  
**A:** COUNT returns the number of rows, AVG returns the average value, and SUM returns the total sum of a numeric column.

**Syntax:**
```sql
SELECT COUNT(column_name) FROM table_name;
SELECT AVG(column_name) FROM table_name;
SELECT SUM(column_name) FROM table_name;
```

## String Functions

### LIKE
**Q:** What does the LIKE operator do?  
**A:** The LIKE operator is used for pattern matching in a WHERE clause.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column LIKE pattern;
```

### Wildcards
**Q:** What are SQL wildcards?  
**A:** Wildcards are used with the LIKE operator to search for a specified pattern in a column.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column LIKE '%value%';
```

## Advanced Queries

### IN
**Q:** What does the IN operator do?  
**A:** The IN operator allows you to specify multiple values in a WHERE clause.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column IN (value1, value2, ...);
```

### BETWEEN
**Q:** What does the BETWEEN operator do?  
**A:** The BETWEEN operator selects values within a given range.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column BETWEEN value1 AND value2;
```

### Aliases
**Q:** What are SQL aliases?  
**A:** Aliases are used to give a table or a column a temporary name.

**Syntax:**
```sql
SELECT column_name AS alias_name
FROM table_name;
```

### Joins
**Q:** What is a SQL JOIN?  
**A:** JOINs are used to combine rows from two or more tables based on a related column.

### INNER JOIN
**Q:** What does the INNER JOIN do?  
**A:** The INNER JOIN keyword selects records that have matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### LEFT JOIN
**Q:** What does the LEFT JOIN do?  
**A:** The LEFT JOIN keyword returns all records from the left table and the matched records from the right table.

**Syntax:**
```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```

### RIGHT JOIN
**Q:** What does the RIGHT JOIN do?  
**A:** The RIGHT JOIN keyword returns all records from the right table and the matched records from the left table.

**Syntax:**
```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```

### CROSS JOIN
**Q:** What does the CROSS JOIN do?  
**A:** The CROSS JOIN returns the Cartesian product of the two tables.

**Syntax:**
```sql
SELECT columns
FROM table1
CROSS JOIN table2;
```

### Self Join
**Q:** What is a Self Join?  
**A:** A self join is a regular join, but the table is joined with itself.

**Syntax:**
```sql
SELECT a.column_name, b.column_name
FROM table_name a, table_name b
WHERE condition;
```

### UNION
**Q:** What does the UNION operator do?  
**A:** The UNION operator is used to combine the result sets of two or more SELECT statements.

**Syntax:**
```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s

) FROM table2;
```

### GROUP BY
**Q:** What does the GROUP BY statement do?  
**A:** The GROUP BY statement groups rows that have the same values into summary rows.

**Syntax:**
```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1;
```

### HAVING
**Q:** What does the HAVING clause do?  
**A:** The HAVING clause is used to filter records after the GROUP BY clause.

**Syntax:**
```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1
HAVING condition;
```

### EXISTS
**Q:** What does the EXISTS operator do?  
**A:** The EXISTS operator is used to test for the existence of any record in a subquery.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE EXISTS (SELECT column1 FROM table_name WHERE condition);
```

### ANY, ALL
**Q:** What do the ANY and ALL operators do?  
**A:** The ANY and ALL operators are used with a WHERE or HAVING clause to compare a value to a set of values.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE column operator ANY (SELECT column FROM table_name WHERE condition);
```

## Other Important Concepts

### INSERT SELECT
**Q:** What does the INSERT SELECT statement do?  
**A:** The INSERT INTO SELECT statement copies data from one table and inserts it into another table.

**Syntax:**
```sql
INSERT INTO table2 (column1, column2, ...)
SELECT column1, column2, ...
FROM table1
WHERE condition;
```

### CASE
**Q:** What does the CASE statement do?  
**A:** The CASE statement goes through conditions and returns a value when the first condition is met.

**Syntax:**
```sql
SELECT column1, 
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ...
    ELSE result
END
FROM table_name;
```

### Null Functions
**Q:** What are Null Functions in SQL?  
**A:** Functions like ISNULL(), COALESCE() are used to handle NULL values in SQL.

**Syntax:**
```sql
SELECT column_name, ISNULL(column_name, value)
FROM table_name;
```

### Comments
**Q:** How do you add comments in SQL?  
**A:** Comments can be added using -- for single line comments and /* */ for multi-line comments.

**Syntax:**
```sql
-- This is a single-line comment
SELECT * FROM table_name;

/*
This is a multi-line comment
SELECT * FROM table_name;
*/
```

### Operators
**Q:** What are SQL Operators?  
**A:** SQL operators are used to specify conditions in an SQL statement and to serve as conjunctions for multiple conditions.

**Syntax:**
```sql
SELECT column1, column2
FROM table_name
WHERE column1 = value;
```

## Data Science-Specific Questions

### Normalization vs Denormalization
**Q:** What is the difference between normalization and denormalization?  
**A:** Normalization is the process of organizing data to reduce redundancy, while denormalization is the process of combining normalized tables to improve read performance.

### Indexes
**Q:** What are indexes and why are they used?  
**A:** Indexes are used to speed up the retrieval of rows by creating a data structure that allows quick lookups.

**Syntax:**
```sql
CREATE INDEX index_name ON table_name (column1, column2, ...);
```

### Views
**Q:** What is a view in SQL?  
**A:** A view is a virtual table based on the result-set of an SQL statement.

**Syntax:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### Stored Procedures
**Q:** What are stored procedures?  
**A:** Stored procedures are a set of SQL statements that can be stored and executed on the database server.

**Syntax:**
```sql
CREATE PROCEDURE procedure_name (parameters)
BEGIN
    SQL statements;
END;
```

### Transactions
**Q:** What is a transaction in SQL?  
**A:** A transaction is a sequence of one or more SQL operations treated as a single unit of work.

**Syntax:**
```sql
START TRANSACTION;
SQL statements;
COMMIT;
```

### Window Functions
**Q:** What are window functions?  
**A:** Window functions perform calculations across a set of table rows related to the current row.

**Syntax:**
```sql
SELECT column1, 
       aggregate_function(column2) OVER (PARTITION BY column3 ORDER BY column4) 
FROM table_name;
```

### CTEs (Common Table Expressions)
**Q:** What are Common Table Expressions (CTEs)?  
**A:** CTEs are a temporary result set that you can reference within a `SELECT`, `INSERT`, `UPDATE`, or `DELETE` statement.

**Syntax:**
```sql
WITH cte_name AS (
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition
)
SELECT *
FROM cte_name;
```

### Temporary Tables
**Q:** What are temporary tables?  
**A:** Temporary tables are tables that are created and used during the session and automatically dropped at the end of the session.

**Syntax:**
```sql
CREATE TEMPORARY TABLE temp_table_name (
    column1 datatype,
    column2 datatype,
    ...
);
```

## Security Concepts

### SQL Injection
**Q:** What is SQL injection?  
**A:** SQL injection is a type of security vulnerability that allows attackers to interfere with the queries that an application makes to its database.

**Prevention Techniques:**
1. Use prepared statements and parameterized queries.
2. Use stored procedures.
3. Validate and sanitize user inputs.
4. Use ORM (Object Relational Mapping) frameworks.
5. Implement proper error handling.

## Important Data Science Interview Questions

### Pattern Matching
**Q:** What is Pattern Matching in SQL?  
**A:** Pattern matching in SQL is done using the LIKE operator to search for a specified pattern in a column.

### Creating Empty Tables
**Q:** How to create empty tables with the same structure as another table?  
**A:** Use the CREATE TABLE statement with the AS clause and a false condition.

**Syntax:**
```sql
CREATE TABLE new_table AS SELECT * FROM existing_table WHERE 1=0;
```

### Recursive Stored Procedure
**Q:** What is a Recursive Stored Procedure?  
**A:** A recursive stored procedure is a stored procedure that calls itself until a boundary condition is met.

### Collation
**Q:** What is Collation? What are the different types of Collation Sensitivity?  
**A:** Collation specifies how data is sorted and compared. Types include case sensitivity, accent sensitivity, kana sensitivity, and width sensitivity.

### OLTP vs OLAP
**Q:** What are the differences between OLTP and OLAP?  
**A:** OLTP (Online Transaction Processing) is used for transactional applications, while OLAP (Online Analytical Processing) is used for analytical and data warehousing applications.

### User-defined Function
**Q:** What is a User-defined function? What are its various types?  
**A:** A user-defined function is a function created by the user. Types include scalar functions, inline table-valued functions, and multi-statement table-valued functions.

### UNIQUE Constraint
**Q:** What is a UNIQUE constraint?  
**A:** A UNIQUE constraint ensures all values in a column are unique.

### Query
**Q:** What is a Query?  
**A:** A query is a request for data or information from a database.

### Data Integrity
**Q:** What is Data Integrity?  
**A:** Data integrity refers to the accuracy and consistency of data stored in a database.

### Clustered vs Non-clustered Index
**Q:** What is the difference between Clustered and Non-clustered index?  
**A:** A clustered index determines the physical order of data in a table, while a non-clustered index does not alter the physical order of data.

### Index
**Q:** What is an Index? Explain its different types.  
**A:** An index is a database object used to speed up data retrieval. Types include unique, non-unique, clustered, and non-clustered indexes.

### Cross-Join
**Q:** What is a Cross-Join?  
**A:** A cross-join returns the Cartesian product of two tables, combining all rows from the first table with all rows from the second table.

### Self-Join
**Q:** What is a Self-Join?  
**A:** A self-join is a join that is used to join a table with itself.

### Foreign Key
**Q:** What is a Foreign Key?  
**A:** A foreign key is a column or set of columns that establishes a link between data in two tables.

### Subquery
**Q:** What is a Subquery? What are its types?  
**A:** A subquery is a query nested within another query. Types include single-row subquery, multiple-row subquery, and correlated subquery.

### Primary Key
**Q:** What is a Primary Key?  
**A:** A primary key is a column or set of columns that uniquely identifies each row in a table.

### Constraints
**Q:** What are Constraints in SQL?  
**A:** Constraints are rules applied to table columns to enforce data integrity.

### Tables and Fields
**Q:** What are Tables and Fields?  
**A:** Tables are collections of related data entries, and fields are columns in a table.

### RDBMS vs DBMS
**

Q:** What is RDBMS? How is it different from DBMS?  
**A:** RDBMS (Relational Database Management System) stores data in related tables, whereas DBMS (Database Management System) does not necessarily use a tabular structure.

### DBMS
**Q:** What is DBMS?  
**A:** DBMS is software for creating and managing databases.

### Database
**Q:** What is a Database?  
**A:** A database is an organized collection of structured data.

### SELECT Statement
**Q:** What is the SELECT statement?  
**A:** The SELECT statement is used to query the database and retrieve data.

### Common Clauses with SELECT
**Q:** What are some common clauses used with SELECT query in SQL?  
**A:** Common clauses include WHERE, ORDER BY, GROUP BY, HAVING, and LIMIT.

### UNION, MINUS, INTERSECT
**Q:** What are UNION, MINUS and INTERSECT commands?  
**A:** UNION combines results of two queries, MINUS returns the difference, and INTERSECT returns the intersection of two queries.

### Cursor
**Q:** What is a Cursor?  
**A:** A cursor is a database object used to retrieve, manipulate, and navigate through a result set row by row.

### Entities and Relationships
**Q:** What are Entities and Relationships?  
**A:** Entities are objects stored in tables, and relationships define how entities are related.

### Types of Relationships
**Q:** List the different types of relationships in SQL.  
**A:** Types include one-to-one, one-to-many, and many-to-many relationships.

### Alias
**Q:** What is an Alias in SQL?  
**A:** An alias is a temporary name for a table or column.

### View
**Q:** What is a View?  
**A:** A view is a virtual table based on the result-set of a query.

### Normalization
**Q:** What is Normalization?  
**A:** Normalization is the process of organizing data to minimize redundancy.

### Denormalization
**Q:** What is Denormalization?  
**A:** Denormalization is the process of combining normalized tables to improve read performance.

### Forms of Normalization
**Q:** What are the various forms of Normalization?  
**A:** Forms include 1NF, 2NF, 3NF, BCNF, and 4NF.

### TRUNCATE, DELETE, DROP
**Q:** What are the TRUNCATE, DELETE and DROP statements?  
**A:** TRUNCATE removes all rows from a table, DELETE removes rows based on a condition, and DROP removes the table and its data.

### Aggregate vs Scalar Functions
**Q:** What are Aggregate and Scalar functions?  
**A:** Aggregate functions operate on a set of values and return a single value. Scalar functions operate on a single value and return a single value.

### Ranking Functions
**Q:** What are Ranking Functions in SQL?  
**A:** Ranking functions return a ranking value for each row in a partition.

**Syntax:**
```sql
SELECT column_name, RANK() OVER (PARTITION BY column_name ORDER BY column_name) AS rank
FROM table_name;
```

### DDL, DML, DCL, TCL
**Q:** What are the different types of SQL commands?  
**A:** SQL commands can be categorized into four main types: Data Definition Language (DDL), Data Manipulation Language (DML), Data Control Language (DCL), and Transaction Control Language (TCL).

### SQL Injection
**Q:** What is SQL Injection?  
**A:** SQL Injection is a security vulnerability that allows attackers to interfere with SQL queries made to a database.

### Recursive Stored Procedure
**Q:** What is a Recursive Stored Procedure?  
**A:** A recursive stored procedure calls itself until a boundary condition is met.

### Collation
**Q:** What is Collation?  
**A:** Collation determines how data is sorted and compared in a database.

### OLTP
**Q:** What is OLTP?  
**A:** OLTP (Online Transaction Processing) is a category of data processing that supports transaction-oriented applications.

### ACID Properties
**Q:** What are ACID properties in the context of database transactions?  
**A:** ACID stands for Atomicity, Consistency, Isolation, Durability, which are the key properties that ensure reliable transaction processing.

### Constraints
**Q:** What are Constraints in SQL?  
**A:** Constraints are rules enforced on data columns on a table to ensure the validity and integrity of data.

### Transactions
**Q:** What is a Transaction in SQL?  
**A:** A transaction is a sequence of SQL operations that are executed as a single unit of work.

### Triggers
**Q:** What is a Trigger in SQL?  
**A:** A trigger is a database object that automatically executes a predefined action when certain events occur.

### Events
**Q:** What is an Event in SQL?  
**A:** An event is a task that runs according to a schedule.

