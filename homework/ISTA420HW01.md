// Name: TSQL HW01
// Author: James Smelser
// Date: July 1, 2019

----------------------------------
# Chapter 01, Background to T-SQL
## ISTA-420, T-SQL Fundamentals
### Readings
#### Read Chapter 1, pages 1 - 26, T-SQL Fundamentals.
###### Homework Questions
1. How does the book describe the difference between imperative and declarative languages?
-	SQL uses declarative language to define what you want to get, unlike other programming languages which use imperative language requiring you to define how to get what you want.
2. List three categories of command statements in SQL.
- Data Definition Language (DDL), Data Manipulation Language (DML), Data Control Language (DCL).
3. Give an informal definition of database as used in the expression \relational database management system." Give an informal definition of database as used in the expression \Human Resources database."
- RDMS- A database that uses the relational model which is based on set theory and predicate logic math. It is designed to provide the means to store, manage, enforce integrity and query data. Human Resources Database- A container of objects such as tables and other information.
4. How does SQL implement three-valued predicate logic?
- SQL uses three predicate logic meaning all data is defined as true, false or null.
5. How does SQL enforce entity integrity? How does SQL enforce referential integrity?
- Entity Integrity- SQL uses candidate keys which provide integrity through not allowing more than one occurrence in a row of the same relation. Referential Integrity- SQL uses foreign keys which provide integrity through referencing candidate keys in other or the same relation.
6. What is a relation as defined in the textbook? A one word answer to this question is sufficient.
- Members of a set, unique and atomic.
7. Is this table in first normal form? Why or why not? If it is not, how would you change it?
- No, facCreds cannot have multiple inputs in the same column. A new row for each credential must be made.
```
create table faculty (
facID int primary key,
facName text,
facCreds text);
```
```
facID facName facCreds
1 Alan Alda BA, MA
2 Bridgette Bardot BS, MS, PhD
3 Casey Cason AA, BBA, MBA, DEd
```
8. Is this table in second normal form? Why or why not? If it is not, how would you change it?
- No, you can find non key attributes from part of the candidate key. Split into two relations, pets and owners.
```
create table pets (
ownerID int primary key,
petID int primary key,
ownerFirstName text,
ownerLastName text,
petName text,
petType text);
```
```
ownerID petID ownerFirstName ownerLastName petName petType
1 1 Dom Delouise Rex German Shepherd
1 2 Dom Delouise Lacy Border Collie
2 3 Emilio Estevez Midnight Persian Cat
```
9. Is this table in third normal form? Why or why not? If it is not, how would you change it?
- No, make seperate table for address with postal code as the FK.
```
create table friends (
friendID int primary key,
friendName text,
friendStreet text,
friendCity text,
friendState text,
friendZip text);
```
```
ID FirstName LastName Street City State Zip
1 Fred Flintstone 123 Rock Quarry Rd Bedrock GA 31905
2 Greta Garbo 456 Starlit Ave Paris FL 30019
3 Harry Houdini 789 Hidden Glen Lane Alcatraz CA 00000
```
10. List the components of a four-part object name.
- Instance, database, schema, table.
11. What is the difference between declarative data integrity and procedural data integrity?
- Declarative integrity is enforced by the model and Procedural integrity is enforced by code.
