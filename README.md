# databases
sql and No-sql
## SQL
SQL stands for Structured Query Language. It is a standard programming language used to interact with relational databases. SQL is used for querying, manipulating, 
and managing data stored in relational database management systems (RDBMS).



### Key SQL Concepts to Master
1) Basic SQL Commands: SELECT: Retrieve data from a database,INSERT: Add new rows into a table,UPDATE: Modify existing data in a table.DELETE: Remove data from a table
```
SELECT * FROM users;
INSERT INTO users (name, email) VALUES ('afshin', 'afi@example.com');
UPDATE users SET email = 'afi.doe@example.com' WHERE name = 'afshin';
DELETE FROM users WHERE name = 'afshin';

```
2) Joins
Combining rows from two or more tables based on a related column.
INNER JOIN: Returns only matching records.
LEFT JOIN (LEFT OUTER JOIN): Returns all records from the left table and matched records from the right table.
RIGHT JOIN (RIGHT OUTER JOIN): Similar to LEFT JOIN, but returns all records from the right table.
FULL JOIN: Returns all records when there is a match in either left or right table
3) GROUP BY & Aggregation Functions
GROUP BY & Aggregation Functions
GROUP BY is used to group rows that have the same values into summary rows.
Common aggregation functions include COUNT(), SUM(), AVG(), MAX(), and MIN().
4) Subqueries
A subquery is a query within another query. It can be used in the SELECT, FROM, WHERE, and HAVING clauses.
```
SELECT name FROM employees WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'IT');

```
5) Indexes
Indexes speed up retrieval of records but can slow down data modification operations (like INSERT, UPDATE, and DELETE).defualt on Primary key
Primary Key: Uniquely identifies each record.
Foreign Key: Ensures referential integrity between tables.
6) Normalization and Denormalization
Normalization Normalization is a process in database design that aims to reduce data redundancy (repetition) and avoid data anomalies (inconsistencies) during data insertion, updating, or deletion. It involves organizing data into tables in a way that eliminates undesirable dependencies and ensures efficient storage.
7) Transactions
1) ACID ,COMMIT:Finalizes a transaction ,ROLLBACK: Reverts a transaction.
8) Views
A view is a virtual table based on the result of a query. It simplifies complex queries and can improve security by limiting direct access to underlying tables.
```
A view is a virtual table based on the result of a query. It simplifies complex queries and can improve security by limiting direct access to underlying tables.
```




















##########################################################3
# ACID
ACID is a set of properties that ensure the reliable processing of database transactions.
### Transaction
1) A collection of queries.
2)  A transaction ensures that a group of operations either completely succeeds or fails.

## Key Of Transaction

## Atomicity

1) all queries must succeed if one fails all should be rollback.


## Isolation
2) each tranaction it for himseldf forexample db A not intrupt fot transcation B

## Consistency

3) A tranaction must bring the database from one  valid state to another  valid state,
example: a bank has 900$ and in there from account a send 300$ to account b it delete 300 - 9-- but not ++ 300 to data and it is false
less 300 but not add 300 .
or: If a database has a rule that every account must have a positive balance, any transaction that would lead to a negative balance should fail.
## Durability
4) for example you have trancaction and to that moment power out age and we store the data on the dist event that we do that transcaction





# POSTGRESQL
## psql
psql is a terminal-based front-end to POSTGRESQL ,comand-line interface to POSTGRESQL