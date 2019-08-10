// Name: TSQL HW 08b
// Author: James Smelser
// Date: July 29, 2019

---------------------------------------------------------------
# Chapter 8b, Data Modication
## ISTA-420, T-SQL Fundamentals
### Readings
#### Read chapter 8, pages 266 - 287 in the T-SQL Fundamentals book.
##### Homework questions
1. The sales tax rate for a state just changed. How would you update the state sales tax table to reflect
the changes? Assume that this table has an ID column, an RATE column, and a STATE column.
- Using an UPDATE statement.
2. The Revenue Division has requested that you provide a report on what the actual sales taxes would
have been for all orders in the past year, assuming the retroactivity of the new sales tax rate. How
would you calculate this?
- Using an UPDATE with an OUTPUT clause.
3. Explain how the proprietary assignment update command works.
- Updates data in a table and assigns values to variables at the same time.
4. What is one very important purpose of the MERGE SQL statement? What is ETL (not in book)?
- Use to merge data from a source into a target, applying different actions (INSERT, UPDATE, and DELETE) based on conditional logic. ETL is a technique for loading data into databases, and shaping it to meet query requirements.
5. What are the semantics of MERGE?
- You specify the target table name in the MERGE clause and the source table name in the USING clause. You define a merge condition by specifying a predicate in the ON clause. The merge condition defines which rows in the source table have matches in the target and which don’t. You define the action to take when a match is found in a clause called WHEN MATCHED THEN, and the action to take when a match is not found in the WHEN NOT MATCHED THEN clause.
6. Write a typical INSERT OUTPUT statement.
- When you need to insert a row set into a table with an identity column, and you need to get back all identity values that
were generated.
7. Write a typical UPDATE OUTPUT statement.
- You can refer to both the state of the modified row before the change, and to the state after the change
8. Write a typical DELETE OUTPUT statement.
- Delete rows from a target table.
9. Write a typical MERGE OUTPUT statement.
- You can also use the OUTPUT clause with the MERGE statement, but remember that a single MERGE
statement can invoke multiple different DML actions.
10. What is nested DML?
- You can use to directly insert into the final target table only the subset of rows you need
from the full set of modified rows.
