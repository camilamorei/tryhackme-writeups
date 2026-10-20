# TryHackMe: SQL Fundamentals

## Overview

This room introduces the fundamentals of SQL and relational databases. It covers database structures, SQL statements, CRUD operations, clauses, logical and comparison operators, and functions.

These concepts are important for understanding how applications store and retrieve information and how database vulnerabilities, such as SQL injection, can affect web applications.

## Topics Covered

- Database fundamentals
- Relational and non-relational databases
- Tables, rows, and columns
- Primary keys and foreign keys
- Database Management Systems (DBMS)
- SQL syntax and database management
- CRUD operations
- SQL clauses
- Logical and comparison operators
- String and aggregate functions

## Task 1: Introduction

Introduction to SQL Fundamentals and the role of databases in computing and cybersecurity.

## Task 2: Databases 101

Learned the differences between relational and non-relational databases and how relational databases organize information.

Key concepts:

- Relational databases store structured data in tables.
- Non-relational databases support flexible data structures.
- Rows represent individual records.
- Columns represent attributes.
- Primary keys uniquely identify records.
- Foreign keys establish relationships between tables.

Answers:

1. Non-relational database
2. Relational database
3. Row
4. Foreign key
5. Primary key

## Task 3: SQL

Learned how SQL interacts with relational databases through a Database Management System (DBMS).

Key concepts:

- A DBMS provides an interface for managing databases.
- SQL stands for Structured Query Language.
- SQL can retrieve, insert, update, and delete data.

Answers:

1. DBMS
2. SQL

## Task 4: Database and Table Statements

Learned how to create, select, inspect, modify, and delete databases and tables.

Important commands:

```sql
CREATE DATABASE database_name;

SHOW DATABASES;

USE database_name;

CREATE TABLE example_table (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    publication_date DATE
);

SHOW TABLES;

DESCRIBE example_table;

ALTER TABLE example_table
ADD page_count INT;

DROP TABLE table_name;
```

The task also involved inspecting database contents to locate flags.

Answers recorded:

1. `THM{575a947132312f97b30ee5aeebba629b723d30f9}`
2. `THM{692aa7eaec2a2a827f4d1a8bed1f90e5e49d2410}`

## Task 5: CRUD Operations

CRUD stands for Create, Read, Update, and Delete. These are the four basic operations used to manage database records.

Create:

```sql
INSERT INTO books (id, name, published_date, description)
VALUES (1, 'Android Security Internals', '2014-10-14',
        'An In-Depth Guide to Android Security');
```

Read:

```sql
SELECT * FROM books;

SELECT name, description
FROM books;
```

Update:

```sql
UPDATE books
SET description = 'Updated description'
WHERE id = 1;
```

Delete:

```sql
DELETE FROM books
WHERE id = 1;
```

Answers recorded:

1. Wi-Fi Pineapple
2. USB attacks

## Task 6: Clauses

Learned how SQL clauses filter, group, and sort query results.

DISTINCT removes duplicate values:

```sql
SELECT DISTINCT name
FROM books;
```

GROUP BY groups records:

```sql
SELECT name, COUNT(*)
FROM books
GROUP BY name;
```

ORDER BY sorts records:

```sql
SELECT *
FROM books
ORDER BY published_date ASC;
```

Descending order:

```sql
SELECT *
FROM books
ORDER BY published_date DESC;
```

HAVING filters grouped results:

```sql
SELECT name, COUNT(*)
FROM books
GROUP BY name
HAVING name LIKE '%Hack%';
```

Answers recorded:

1. 6
2. Bash Bunny
3. Wi-Fi Pineapple

## Task 7: Operators

Learned how logical and comparison operators filter database results.

Logical operators:

- LIKE: matches a text pattern.
- AND: requires all conditions to be true.
- OR: requires at least one condition to be true.
- NOT: reverses a condition.
- BETWEEN: checks whether a value falls within a range.

Comparison operators:

- `=` checks equality.
- `!=` checks inequality.
- `<` checks whether a value is smaller.
- `>` checks whether a value is larger.
- `<=` checks whether a value is smaller than or equal to another value.
- `>=` checks whether a value is larger than or equal to another value.

Example:

```sql
SELECT *
FROM books
WHERE published_date > '2020-01-01'
AND category = 'Offensive Security';
```

Answers recorded:

1. Flipper Zero
2. RFID cloning
3. Lan Turtle

## Task 8: Functions

Learned how SQL functions manipulate strings and calculate aggregate values.

String functions:

```sql
SELECT CONCAT(name, ' - ', category)
FROM books;

SELECT GROUP_CONCAT(name SEPARATOR ' & ')
FROM books;

SELECT SUBSTRING(published_date, 1, 4)
FROM books;

SELECT LENGTH(name)
FROM books;
```

Aggregate functions:

```sql
SELECT COUNT(*)
FROM books;

SELECT SUM(price)
FROM books;

SELECT MAX(published_date)
FROM books;

SELECT MIN(published_date)
FROM books;
```

Answers recorded:

1. USB Rubber Ducky
2. 1444
3. Flipper Zero & iCopy-XS

## Task 9: Conclusion

Completed the SQL Fundamentals room and reviewed the main concepts of relational databases and SQL.

## Key Takeaways

- Databases organize and store information.
- Relational databases use tables and relationships.
- Primary and foreign keys support data integrity and relationships.
- SQL provides commands for retrieving and modifying data.
- CRUD operations manage database records.
- Clauses and operators help filter and organize query results.
- SQL functions simplify string manipulation and data analysis.
- Understanding SQL is useful when studying web application security and SQL injection.

## Next Steps

- Practice SQL queries in a local lab.
- Learn more about SQL injection in authorized training environments.
- Continue studying web application security.
- Document future TryHackMe rooms and practical exercises.

## Disclaimer

This write-up is for educational purposes and documents learning activities performed in the TryHackMe training environment. The recorded answers should be verified against the room before publication.
