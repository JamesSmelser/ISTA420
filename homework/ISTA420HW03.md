// Name: TSQL HW03
// Author: James Smelser
// Date: July 12, 2019

--------------------------------------
# Chapter 3, Joins
## ISTA-420, T-SQL Fundamentals
### Readings
#### Chapter 3, Pages 103 { 123.
##### Homework questions
1. In general, why would you even want to join two (or more) tables together? This is a good time to
think about the nature of relational algebra.
- To combine all possible combination and pairs from two or more different tables
2. Describe in your own words the output from an inner join.
- Combines all rows from two tables then filters based on the ON predicate.
3. Describe in your own words the output from an outer join.
- An outer join returns joined tables specified in the query as well as preserving
the table joined on that respective side identified in the join (left, right, full).
4. Describe in your own words the output from an cross join.
- A one phased join that takes one complete row from a table and matches it with
a complete row from another table.
5. A convenient mnemonic for remembering the various joins is Ohio." Why is this true?
- Outer left, Inner, Outer right. because it matches the venn diagram explanation
for joins.
6. Give an example of a composite join.
- you have a foreign key defined on dbo.Table2, columns col1, col2, referencing
dbo.Table1, columns col1, col2, and you need to write a query that joins the two
based on this relationship.
7. What is the difference between the following two queries? The business problem is, How many orders
do we have from each customer?"
- The COUNT* function can not detect if a row really represents an order whereas
the COUNT(column) ignores outer rows with a NULL in the column. Query 1 = 832, Query 2 = 830
```
================first query===============
SELECT C.custid, COUNT(*) AS numorders
FROM Sales.Customers AS C
LEFT OUTER JOIN Sales.Orders AS O
ON C.custid = O.custid
GROUP BY C.custid;
```
```
================second query===============
SELECT C.custid, COUNT(O.orderid) AS numorders
FROM Sales.Customers AS C
LEFT OUTER JOIN Sales.Orders AS O
ON C.custid = O.custid
GROUP BY C.custid;
```
8. What might be one reason the following query does not return the column custID in this query?
- It does return custid, because it was filtered out by the WHERE clause.
```
SELECT C.custid, C.companyname, O.orderid, O.orderdate
FROM Sales.Customers AS C
LEFT OUTER JOIN Sales.Orders AS O
ON C.custid = O.custid
WHERE O.orderdate >= '20160101';
```
