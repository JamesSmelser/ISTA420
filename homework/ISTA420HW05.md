// Name: TSQL HW05
// Author: James Smelser
// Date: July 21, 2019

-------------------------------------------------------------
# Chapter 5, Table expressions
## ISTA-420, T-SQL Fundamentals
### Readings
#### Read chapter 5, pages 161 { 183 in the T-SQL Fundamentals book.
##### Discussion questions
1. What is a table expression? Can you give a technical definition of a table expression?
- A table expression is a named query expression that represents a valid relational table. The outer query and the inner
query are merged into one query directly against the underlying objects.
2. In what SQL clause are derived tables (table valued subqueries) located?
- In the FROM clause.
3. Why can you refer to column aliases in an outer query that you defined in an inner table valued
subquery?
- Because the inner query defining aliases is processed first which allows the outer query to use those aliases.
4. What SQL key word defines a common table expression?
- The WITH statement.
5. When using common table expressions, can a subsequent derived table use a table alias declared in a
preceding table expression?
- Each CTE can refer to all previously defined CTEs, and the outer query can refer to all CTEs.
6. Can a main query refer to a previously defined common table expression by multiple aliases?
- Each CTE can refer to all previously defined CTEs, and the outer query can refer to all CTEs.
7. In SQL, is a view a durable object?
- Views and inline table-valued functions (inline TVFs) are two types of table expressions whose definitions are stored as permanent objects in the database, making them reusable.
8. In a view, what does WITH CHECK OPTION do? Why is this important?
- CHECK OPTION is to prevent modifications through the view that conflict with the view’s filter. Keeps the view from being manipulated outside its original parameter.
9. In a view, what does SCHEMABINDING do? Why is this important?
- It binds the schema of referenced objects and columns to the schema of the referencing object. Keeps referenced objects from being dropped or altered.
10. What is a table valued function?
- Reusable table expressions that support input parameters and returns the value.
11. What does the APPLY operator do?
- The APPLY operator operates on two input tables it applies the right table to each row from the left table and produces a result
table with the unified result sets.
12. What are the two forms of the APPLY operator? Give an example of each.
- CROSS APPLY, OUTER APPLY. A CROSS APPLY implements only one logical-query phase and a OUTER APPLY implements a two logical-query phase.
