// Name: TSQL HW06
// Author: James Smelser
// Date: July 25, 2019

-----------------------------------------------------------
# Chapter 6, Set operators
## ISTA-420, T-SQL Fundamentals
### Readings
#### Read chapter 6, pages 193 - 204 in the T-SQL Fundamentals book.
##### Homework questions
1. What does a set operator do?
- Operators that combine rows from two query result sets (or multisets).
2. What are the general requirements of a set operator.
- The two input queries must produce results with the same number of columns, and corresponding columns must have compatible data types.
3. What is a Venn Diagram? This is not in the book.
- A diagram representing mathematical or logical sets pictorially as circles or closed curves within an enclosing rectangle.
4. Draw a Venn Diagram of the UNION operator. What does it do?
- The shaded area represents the result of the operator. The nonshaded areas reflect the fact
that the operator doesn’t have to include all attributes of the original relations, the UNION
operator unifies the results of two input queries.
5. Draw a Venn Diagram of the UNION ALL operator. What does it do?
- The UNION ALL operator unifies the two input query results without attempting to remove duplicates
from the result, the UNION ALL operator unifies and returns all rows of both tables.
6. Draw a Venn Diagram of the INTERSECT operator. What does it do?
- INTERSECT returns only distinct rows that appear in both input query results.
7. If SQL Server supported the INTERSECT ALL operator, what would it do?
- INTERSECT ALL operator means that duplicate intersections will not be removed.
8. Draw a Venn Diagram of the EXCEPT operator. What does it do?
- The EXCEPT operator implements set differences. It operates on the results of two input queries and
returns rows that appear in the first input but not the second.
9. If SQL Server supported the EXCEPT ALL operator, what would it do?
- The EXCEPT ALL operator is similar to the EXCEPT operator, but it also takes into account the number of
occurrences of each row.
10. What is the precedence of the set operators?
- The INTERSECT operator precedes UNION and EXCEPT, and UNION and EXCEPT are evaluated in order of appearance.
