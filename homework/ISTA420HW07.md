// Name: TSQL HW 07
// Author: James Smelser
// Date: July 28, 2019

-----------------------------------------------------------
# Chapter 7, Beyond the fundamentals of querying
## ISTA-420, T-SQL Fundamentals
### Readings
#### Read chapter 7, pages 213 - 230 in the T-SQL Fundamentals book.
##### Homework questions
1. What is a window function?
- A window function is a function that, for each row, computes a scalar result value based on a calculation
against a subset of the rows from the underlying query.
2. What does PARTITION do?
- restricts the window to the subset of rows that have the same values in the partitioning columns as in the current row.
3. What does ORDER BY do?
- defines ordering, window ordering supports a frame specification.
4. What does ROWS BETWEEN do?
- filters a frame, or a subset, of rows from the window partition between the two specified delimiters.
5. What is a ranking window function? Why would you use it? Give an example.
- You use ranking window functions to rank each row with respect to others in the window.
To provide a unique sequential number to each row. If you wanted to return the employees
with the most sales in order.
6. What is an offset window function? Why would you use it? Give an example.
- You use offset window functions to return an element from a row that is at a certain offset from the
current row or at the beginning or end of a window frame. To compute differences between values. If
you wanted to compare the previous order values to the current order values of a customer.
7. What do LEAD and LAG DO.
- You use these functions to obtain an element from a row that is at a certain offset from
the current row within the partition, based on the indicated ordering.
8. What do FIRST VALUE and LAST VALUE do?
- To return an element from the first and last rows in the window frame, respectively.
9. What is an aggregate window function? Why would you use it? Give an example.
- You use aggregate window functions to aggregate the rows in the defined window.
In order to aggregate values of a specific row or rows. If you wanted the total value of
all orders.
10. What is a pivot table and what does it do?
- Pivoting data involves rotating data from a state of rows to a state of columns, possibly aggregating
values along the way.
