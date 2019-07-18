// Name: TSQL HW02b
// Author: James Smelser
// Date: July 6, 2019

-------------------------------------
# Chapter 02b, Single Table Queries
## T-SQL Fundamentals
### 1 Readings
#### Read chapter 2 of the textbook T-SQL Fundamentals, pages 49 through 73.
##### 2 Homework Questions
1. What is a data type? Why do we have data types?
- Information for the computer to translate, tells the computer how to read the data. regular and Unicode. Regular data types include CHAR and VARCHAR, and Unicode data types include NCHAR and NVARCHAR.
2. What is a collation? Name four elements of a collation.
- a property of character data that encapsulates several aspects: language support, sort order, case sensitivity, accent sensitivity, and more.
3. How would you strip whitespace from a string? For example, suppose you had \ Dave " but wanted only \Dave".
- LTRIM('\ Dave').
4. Suppose you wanted to make a list of every college and university that was called an Institute from the college table. Write the query.
- SELECT name FROM college WHERE name LIKE "%institute%".
5. How would you find out the index of the first space in a string? For example, the index of thefirst space in \Barack Hussein Obama" would be 7.
- CHARINDEX(' ','\Barack Hussein Obama').
6. How would you select just thefirst name in a list of the presidents. Each record looks like the: "George Washington", "John Adams". First names can be an arbitrary length, from \Cal" to \Benjamin." (e.g.,
Cal College, Benjamin Harrison)
- SELECT SUBSTRING('George Washington', 1, CHARINDEX('George Washington', ' ')).
7. What is the order of precedence for the logical operators?
- ( ) (Parentheses), =, >, <, >=, <=, <>, !=, !>, !< (Comparison operators), NOT, AND, BETWEEN, IN, LIKE, OR.
8. What is the order of precedence for the math operators?
- x (Multiplication), / (Division), % (Modulo), + (Positive), – (Negative), + (Addition), + (Concatenation), – (Subtraction).
9. What is the difference between a simple and a searched CASE expression?
- Simple returns the first match of the comparison, searched CASE expression returns the value in the THEN clause.
10. How would you turn a list of names like this: \LASTNAME, FIRSTNAME", to a list like this: \FIRSTNAME LASTNAME"?
- SELECT SUBSTRING('Smelser, James', CHARINDEX('Smelser, James', ' ')+ 1) + ' ' + SUBSTRING('Smelser, James', 1, CHARINDEX('Smelser, James', ',')-1);
11. How would you turn a list of names like this: \FIRSTNAME LASTNAME", to a list like this: \LASTNAME, FIRSTNAME"?
- SELECT SUBSTRING('Sean Zitzer', CHARINDEX('Sean Zitzer',' ') + 1) + ', ' SUBSTRING('Sean Zitzer', 1 CHARINDEX('Sean Zitzer', ' '));

'James' || '
' || 'Aaron' || '
' || 'Smelser';
