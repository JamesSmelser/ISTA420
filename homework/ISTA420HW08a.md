// Name: TSQL HW 08a
// Author: James Smelser
// Date: July 29, 2019

---------------------------------------------------------------
# Chapter 8a, Data Modication
## ISTA-420, T-SQL Fundamentals
### Readings
#### Read chapter 8, pages 249 { 266 in the T-SQL Fundamentals book.
##### Homework questions
1. When using INSERT, is the list of columns necessary? Why or why not?
- You do not have to use columns if the amount of data is the same number as columns.
2. When using INSERT SELECT, do you use a subquery (derived table)? Under what circumstances do
you not use a subquery?
- The standard INSERT SELECT statement inserts a set of rows returned by a SELECT query into a target
table.
3. What is the operand for the INSERT EXEC statement?
- A stored procedure, A named block of code that optionally takes parameters.
4. How would you use the INSERT INTO statement?
- Creates a target table and populates it with the result set of a query.
5. What are the parameters to the BULK INSERT statement?
```
- Specify the target table, source file, (data file type, field terminator, row terminator.)
```
6. Does IDENTITY guarantee uniqueness? If not, how do you guarantee uniqueness?
- No, using a primary key constraint.
7. How do you create a SEQUENCE object?
- Sequence object as an alternative key-generating mechanism for identity.
8. How do you use a SEQUENCE object?
- Sequence name, data type, min value, max value, allows cycling.
9. How do you alter a SEQUENCE object?
- You can change any of the sequence properties except the data type with the ALTER SEQUENCE
command.
10. What is the difference between DELETE and TRUNCATE?
- DELETE deletes row by row, TRUNCATE deletes all data from table.
11. What is the difference between DELETE and DROP TABLE?
- DELETE deletes row by row, DROP TABLE deletes the entire table.
