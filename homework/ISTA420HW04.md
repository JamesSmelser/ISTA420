// Name: TSQL HW04
// Author: James Smelser
// Date: July 15, 2019

-------------------------------
# Chapter 4, Subqueries
## ISTA-420, T-SQL Fundamentals
### Readings
#### Read pages, Chapter 4, 133 - 149 in the T-SQL Fundamentals book.
##### Homework questions
1. In your own words, what is a subquery?
- A subquery acts in place of an expression that is based on constants or variables
and is evaluated at run time.
2. In your own words, what is a self contained subquery?
- Self-contained subqueries are subqueries that are independent of the tables in
the outer query.
3. In your own words, what is a correlated subquery?
- Correlated subqueries are subqueries that refer to attributes from the tables
that appear in the outer query.
4. Give an example of a subquery that returns a single value. When would you use this kind of subquery?
- A self contained scalar subquery, for example if you needed to return information about the
order that has the maximum orderid in a table.
5. Give an example of a subquery that returns multiple values. When would you use this kind of subquery?
- A self contained multivalued subquery, for example if you needed to return
orders that were handled by employees with the last name starting with N.
6. Give an example of a subquery that returns table values. When would you use this kind of subquery?
- Correlated subqueries, for example if you needed to return the maximum orderid's
for employees.
7. What does the exists predicate do? Give an example.
- A predicate that accepts a subquery as input and returns TRUE if the subquery
returns any rows and FALSE otherwise. If you needed to return all customers
from Spain that placed an order.
8. What happens if we use the not operator before a predicate? Give an example.
- The NOT operator negates the predicate, if an IN predicate table returns as true for a
customer that placed an order the NOT operator then negates it and returns as false
which discards the customer.
9. When you use exists or not exists with respect to a row in a database, does it return two or three
values? Explain your answer.
- Two, EXISTS uses two-valued predicate logic it always returns TRUE or FALSE
and never UNKNOWN.
10. How would you subquery to calculate aggregates? For example, you want to calculate yearly sales
of a product, and you also want to keep a running sum of total sales. Explain how you would use a
subquery to do this.
- You query one instance of the view (call it O1) to return for each year the current year and quantity.
You use a correlated subquery against a second instance of the view (call it O2) to calculate the
running-total quantity. The subquery should filter all rows in O2 where the order year is smaller than or
equal to the current year in O1, and sum the quantities from O2.
