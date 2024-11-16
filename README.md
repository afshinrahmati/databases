# databases()
sql and No-sql
DBMS( database management system) ==>postgresql , mongoose,SQLITE(file),mySQL,Oracel
# POSTGRESQL
## psql
psql is a terminal-based front-end to POSTGRESQL ,comand-line interface to POSTGRESQL
CRUD()==> CREATE,READ,Update,DELETE

## NOSQL
key-value,GRAPH,Document,column-family(casendra)
without good structure
## 🌟SQL(structured query language)🌟
SQL stands for Structured Query Language. It is a standard programming language used to interact with relational databases. SQL is used for querying, manipulating, 
and managing data stored in relational database management systems (RDBMS).

## TABLE(TYPE:https://www.postgresql.org/docs/current/datatype.html)
* SERIAL TYPE are those type that insert auto.
* CREATE TABLE name(email VARCHAR<variable charecter>(60),password VARCHAR(25), age smallint,address VARCHAR(2000));
* ALTER TABLE name ADD COLUMN lastname VARCHAR(410) UNIQUE;
1) Attribute ==> ID,AGE,NAME
2) Tuples(Entities) ==> {name:"afshin",age:900}


### Key SQL Concepts to Master
1) Basic SQL Commands:
SELECT: Retrieve data from a database,INSERT: Add new rows into a table,UPDATE: Modify existing data in a table.DELETE: Remove data from a table
WHERE name IN("afshin","sara,"amir") 
ORDER BY (ASC<A,B,C>ASNDEING,DESC<z,y,z>DESENDEING)
WHERE username LIKE 'A_f%'==>_ sure exist more than 2 world,% each empty or full.
LIMIT 30
```
SELECT * FROM users;
INSERT INTO users (name, email) VALUES ('afshin', 'afi@example.com');
UPDATE users SET email = 'afi.doe@example.com' WHERE name = 'afshin';
DELETE FROM users WHERE name = 'afshin';

```
####################################################################################################################################################################################################################################################################################################################
2) Joins
Combining rows from two or more tables based on a related column.
INNER JOIN: Returns only matching records.
LEFT JOIN (LEFT OUTER JOIN): Returns all records from the left table and matched records from the right table.
RIGHT JOIN (RIGHT OUTER JOIN): Similar to LEFT JOIN, but returns all records from the right table.
FULL JOIN: Returns all records when there is a match in either left or right table
   ##########################################################################################################################################################
3) GROUP BY & Aggregation Functions
GROUP BY & Aggregation Functions
GROUP BY is used to group rows that have the same values into summary rows.
Common aggregation use for calculations functions include COUNT(), SUM(), AVG(), MAX(), and MIN().
HAVING we can define some order like if ,HAVING age > 120
   ##########################################################################################################################################################
4) Subqueries
A subquery is a query within another query. It can be used in the SELECT, FROM, WHERE, and HAVING clauses.
    ```
    SELECT name FROM employees WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'IT');
    
    ```
   ##########################################################################################################################################################
5) Indexes
Indexes speed up retrieval of records but can slow down data modification operations (like INSERT, UPDATE, and DELETE).defualt on Primary key
Primary Key: Uniquely identifies each record.
Foreign Key: Ensures referential integrity between tables.
 ##########################################################################################################################################################
6) primary key = those Validator are unique that can delete or update like PRODUCT_ID ,user_ID
primary key == UNIQUE ,NOT NULL
    ```
        USER_ID SERIAL PRIMARY KEY
    ```
   ##########################################################################################################################################################
7) FOREIGN KEY
A foreign key (FK) is a column or combination of columns that is used to establish and enforce a link between the data in two 
tables to control the data that can be stored in the foreign key table.
    ```
        CREATE TABLE users(ID PRIMARY KEY)
        CREATE TABLE orders(user_id integert REFRENCES users(ID))
    ```
  ##########################################################################################################################################################
8) Normalization and Denormalization
* ANOMALY == problem
Normalization Normalization is a process in database design that aims to reduce data redundancy (repetition) and avoid data anomalies (inconsistencies) during data insertion, updating, or deletion.
It involves organizing data into tables in a way that eliminates undesirable dependencies and ensures efficient storage.
*** we have 11 type normal design <WIKI> but 7 of them is most necessary
1) FIRST NORMAL FORM (1NF)
   if you have relation database so you should behaving with relation
   • Each column must have a unique name.
   • The order of the row and column doesn't matter.
   • Each column must have a single data type.
   • No Two rows can contain identical Value.<repeate>
   • each column must contain a single Value.
   • Columns cannot contain repeating groups.
2) SECOND NORMAL FORM (2NF)
   • all thin in First Norma Form 
   • All of the non-key fields depend on all of the key fields <Donot insert> mean all of the key should refer to the table
match table<wrong> ==> time,wrestler,class,rank ==> we should seprate the table time or class and not conde in one
and it is good for stop this wrong ==> insert and update and delete Anomaly.

3) THIRD NORMAL FORM (3NF)
   • all in 2
   • each column has self information
wrong if delete one user we do not delete the product that his order
4) Boyce-Codd Normal Form (BCNF):
   A stricter version of 3NF. Each determinant (attribute determining another) must be a candidate key.
5) FOURTH NORMAL FORM (4NF)
   ##########################################################################################################################################################
9) Transactions
those unit of work (واحدی از عملیات) on Database like transform Money.
* Start ----> Operation1,Operation2,Operation3,.... ---> Commit OR RoleBack
1) ACID ,
* A----> Atomicity (all Operation should be successful if one of them got fall all of them should destroy)lost money from a but not incress on b
* C----> Consistency (do all role) like the price not -,or if we have 3 server and to each service we come and change and we sure it update to all server
* I----> ISOLATION(all Operation focuse on self not an other)
* D----> Durability(if the system crash and we should maintain the stated like implement the log)
2) COMMIT:Finalizes a transaction <run the all operation>,
3) ROLLBACK: Reverts a transaction.
10Views
A view is a virtual table based on the result of a query. It simplifies complex queries and can improve security by limiting direct access to underlying tables.
virtual tables created using a SELECT statement.

##########################################################################################################################################################
# SQL Constraints

* Rules applied to columns for maintaining data integrity.
Common constraints include:
NOT NULL: Ensures that a column cannot have a NULL value.
UNIQUE: Ensures all values in a column are unique.
CHECK: Ensures values in a column meet a specific condition.
DEFAULT: Sets a default value for a column if no value is provided.
FOREIGN KEY: Maintains referential integrity between tables.

10)  Stored Procedures and Functions ,Triggers,Data Manipulation and Data Definition Languages (DML & DDL)

##########################################################
# RELATIONS
1) MANY TO ONE(DEFAULT)
![Alt text](./manyTOone1.png)
father can relation with each child But the child just have one father
```
 afshin can buy bnana and car and mobile ==> afshin is user<father> that product that store in order that relation with user
 - for each product we create a order tabele that has one father in product afshin and not amir and afshin
```
2) ONE TO ONE
![Alt text](./OntToOne1.png)
a parent just can has one child. ==> each country just has one capital.
```
IRAN = TEHRAN;
JAPAN = TOKUP;
CREATE TABLE COUNTRY (ID...)
CREATE TABLE CAPITAL(COuntri_ID integer REFENCE counrty(ID) UNIQUE)
```
3) MANY TO MANY(x,y,z that z is middleman between x,y)
![Alt text](./ManyToMany.png)
   a parent can has a lot child and a child can has a lot parent writer and book,a witer has al lot book or a book has many writter
```
CREATE TABLE Book(id)
CREATE TABLE author(Id)
CREATE TABLE book_author(
bookId REF
authorId REF
PRIMARY KEY(Book,author)
)
```
![Alt text](./manyTomany2.png)
```
INSERT INTO book (name) VALUES ('harry patter'),('joker');
INSERT INTO author (name) VALUES ('kevin'),('jack');
INSERT INTO book_author (book,author) VALUES(1,2)
INSERT INTO book_author  (book,author) VALUES(2,1)
INSERT INTO book_author (book,author) VALUES(2,2)
// hary patter write iust by jevin But joker write with kevin and jack
```
![Alt text](./manytomany3.png)

# JOIN
### Relation between Tables
SELECT * FROM users INNER JOIN orders ON orders.user_id= user.user_id INNER JOIN employees ON orders.em_id  = employees.em_id
SELECT USERID FROM customers RIGHT JOIN orders ON orders.customersid =
left => the table write on the left name <customers>
right ==> the table is on the right <orders>
And we have 4 type of  join:
1) INNER JOIN: command information
2) LEFT JOIN:all command information + all information table left
3) RIGHT JOIN:all command information + all information table قهلاف
4) FULL JOIN:all command information
##########################################################
# KEYS
1) Primary Key
   The primary key in SQL is a single, or a group of fields or columns that can uniquely identify a row in a table. 
    Putting it simply, it is a column that accepts unique values for each row.
2) Candidate Key <prime attributes>
   each column that has qualification to be Primary key that we say Candidate key.
   It is used to ensure that there are no duplicate or ambiguous records in a table
3) Alternate Key <non-prime attribute>
   you have 3 column that has qualification for Primary key <A,B,C> and we choice A.
   and we do not choice B and  C so we call them AlternateKey.
   Alternate keys are those candidate keys which are not the Primary key.
4) Super Key
   A Super key is a single key or a group of multiple keys that can uniquely identify tuples in a table.and you can find a 
value in table with theme forExample phonenumber or nantionalCode are unique and you can find a person with theme  phoneumber + nantionalcode == primarykey of user_id
5) Foreign Key
   A FOREIGN KEY is a field (or collection of fields) in one table, that refers to the PRIMARY KEY in another table.
6) Surrogate <saryGyt>Key that mean on own table and donot  valueable in public place.
   A surrogate key on a table is a column with a unique identifier for each row.
    The key is not generated from the table data. Data modelers like to create surrogate keys on their tables when they design data warehouse models.
   ForExample 14,25 taht mean true or fale in my businse
7) Natural key
   that all structure that has identify in real world like Ir is iran or 1,0 that mean true or false.
8) Simple Key
   a column that can be primary key alone we called it simple key like Student_Id
9) Composite Key
   that mean we have Combine any <2 or 3 or 4 ,...> colum Combine together that hapend a primary key like (firstname and Last name and age)
10) Compound Key
   that is composite key that one row is ref .like (Role and Last name and age)
11) Intelligent Key<smart>
    • do not use it
    ID =  20010816Ir1785
    Birthday ==> 2001/08/15
    Counrty = Ir
    postCode = 1785
##########################################################
# UNION,UNION ALL,INTERSECT,EXCEPT
that is look like join But without need primary key and foregin key.
query1+query2
1) UNION<DISTINCT ==> DELETE common value;All ==> bring all data even common>query1+query2
   all information in query One and Two with out command data.
   SELECT city from Admin;
   UNION
   SELECT city form USER;
   result is ==> match all city in admin and user in one column with out common
   if UNION ALL
   result ==> bring all data even common
2) UNION ALL
   return all information in query One and Two.
3) INTERSECT
   return just common data in query one and two.
4) Except
   return all in query one provided that that data not exist on query two.
   iran is in query two and in query one is italy and iran and return italy
##########################################################
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



👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽
🌟REDIS🌟

👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽👽
🌟MONGO🌟