// Name: TSQL HW02a
// Author: James Smelser
// Date: July 2, 2019

-----------------------
# Chapter 02a, Single Table Queries
## T-SQL Fundamentals
### Readings
#### Read chapter 2 of the textbook T-SQL Fundamentals, pages 27 through 49.
##### Homework questions
1. List the order of execution of a SQL query.
- FROM, WHERE, GROUP BY, HAVING, SELECT and ORDER BY.
2. What does the from clause do?
- The FROM clause is the very first query clause that is logically processed. In this clause, you specify the names of the tables you want to query and table operators that operate on those tables.
3. What does the where clause do?
- In the WHERE clause, you specify a predicate or logical expression to filter the rows returned by the FROM phase.
4. What does the group by clause do?
- You can use the GROUP BY phase to arrange the rows returned by the previous logical query processing phase in groups.
5. What does the having clause do?
- The HAVING clause is a group filter.
6. What does the select clause do?
- The SELECT clause is where you specify the attributes (columns) you want to return in the result table of the query.
7. What does the distinct keyword do?
- Remove duplicates and returns a relational result.
8. What does the order by clause do?
- You use the ORDER BY clause to sort the rows in the output for presentation purposes.
9. What does the limit clause do? This is not in the book.
- The LIMIT clause is used to set an upper limit on the number of tuples returned by SQL.
10. What does the top clause do?
- The TOP filter is a proprietary T-SQL feature you can use to limit the number or percentage of rows your query returns.
11. What do the offset . . . fetch . . . clauses do?
- The OFFSET-FETCH filter is considered an extension to the ORDER BY clause. With the OFFSET clause you indicate how many rows to skip, and with the FETCH clause you indicate how many rows to filter after the skipped rows.
