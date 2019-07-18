// Name: TSQL HW02c
// Author: James Smelser
// Date: July 8, 2019

--------------------------------------
# Chapter 02c, Single Table Queries
## ISTA-420, T-SQL Fundamentals
### 1 Readings
#### Read chapter 2, pages 73 - 93 in the T-SQL Fundamentals book.
##### 2 Homework questions
1. What is a data type? Why do we have data types?
- Information for the computer to translate, tells the computer how to read the data. regular and Unicode. Regular data types include CHAR and VARCHAR, and Unicode data types include NCHAR and NVARCHAR.
2. What is a collation? Name four elements of a collation.
- a property of character data that encapsulates several aspects: language support, sort order, case sensitivity, accent sensitivity, and more.
3. How would you strip whitespace from a string? For example, suppose you had \ Dave " but
wanted only \Dave".
- LTRIM('\ Dave').
4. Suppose you wanted to make a list of every college and university that was called an Institute from
the college table. Write the query.
- SELECT name FROM college WHERE name LIKE "%institute%".
5. How would yound out the index of the first space in a string? For example, the index of the first
space in \Barack Hussein Obama" would be 7.
- CHARINDEX(' ','\Barack Hussein Obama').
6. How would you select just the first name in a list of the presidents. First names can be an arbitrary
length, from \Cal" to \Benjamin."
- SELECT SUBSTRING('George Washington', 1, CHARINDEX('George Washington', ' ')).
7. Payments are due exactly 30 days from the date of the last function. Write a select query that calculates
the date of the next payment. Pretend we want to update a column in a database that contains the
date of the next payment. We will do this when we write UPDATE queries.
- SELECT DATEADD(day, 30, '20190708') AS paymentdate;
8. Suppose your son or daughter wants to run a query every day that tells them the number of days until
their 16th birthday. Write a select query that does this.
- SELECT DATEDIFF(day, '20190708', '20200531') AS bdaycount;
9. What function returns the current date? This is very useful in a table that maintains a log of events,
such as user logins.
- CURRENT_TIMESTAMP.
