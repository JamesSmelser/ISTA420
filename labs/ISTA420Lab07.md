// Name: TSQL Lab 07
// Author: James Smelser
// Date: July 28, 2019

---------------------------------------------------------------------
# Microsoft SQL Server T-SQL Fundamentals
## Chapter 07 - Beyond the Fundamentals of Querying
### Exercises
#### © Itzik Ben-Gan

---------------------------------------------------------------------

##### All exercises for this chapter will involve querying the dbo.Orders table in the TSQLV4 database
##### that you created and populated earlier by running the code in Listing 7-1

1 Write a query against the dbo.Orders table that computes for each customer order, both a rank and a dense rank,
partitioned by custid, ordered by qty.
```
SELECT custid, orderid, qty,
RANK() OVER(PARTITION BY custid ORDER BY qty) AS rnk,
DENSE_RANK() OVER(PARTITION BY custid ORDER BY qty) AS drnk
FROM dbo.Orders;
```

2 The following query against the Sales.OrderValues view returns distinct values and their associated row numbers.
```
WITH C AS
(
SELECT DISTINCT val
FROM Sales.OrderValues
)
SELECT val
```

3 Write a query against the dbo.Orders table that computes for each
customer order:
the difference between the current order quantity and the customer's previous order quantity.
the difference between the current order quantity and the customer's next order quantity.
```
SELECT custid, orderid, qty,
qty - LAG(qty) OVER(PARTITION BY custid
ORDER BY orderdate, orderid) AS diffprev,
qty - LEAD(qty) OVER(PARTITION BY custid
ORDER BY orderdate, orderid) AS diffnext
FROM dbo.Orders;
```

4 Write a query against the dbo.Orders table that returns a row for each employee, a column
for each order year, and the count of orders for each employee and order year.
Tables involved: TSQLV4 database, dbo.Orders table.
```
SELECT empid,
COUNT(CASE WHEN orderyear = 2014 THEN orderyear END) AS cnt2014,
COUNT(CASE WHEN orderyear = 2015 THEN orderyear END) AS cnt2015,
COUNT(CASE WHEN orderyear = 2016 THEN orderyear END) AS cnt2016
FROM (SELECT empid, YEAR(orderdate) AS orderyear
FROM dbo.Orders) AS D
GROUP BY empid;
```

5 Write a query against the EmpYearOrders table that unpivots the data, returning a row for each
employee and order year with the number of orders.
Exclude rows where the number of orders is 0 (in our example, employee 3 in year 2016).
```
SELECT empid, orderyear, numorders
FROM dbo.EmpYearOrders
CROSS APPLY (VALUES(2014, cnt2014),
(2015, cnt2015),
(2016, cnt2016)) AS A(orderyear, numorders)
WHERE numorders <> 0;
```

6 Write a query against the dbo.Orders table that returns the
total quantities for each:
employee, customer, and order year.
employee and order year.
customer and order year.
Include a result column in the output that uniquely identifies the grouping set with which
the current row is associated.
Tables involved: TSQLV4 database, dbo.Orders table.
```
SELECT
GROUPING_ID(empid, custid, YEAR(Orderdate)) AS groupingset,
empid, custid, YEAR(Orderdate) AS orderyear, SUM(qty) AS sumqty
FROM dbo.Orders
GROUP BY
GROUPING SETS
(
(empid, custid, YEAR(orderdate)),
(empid, YEAR(orderdate)),
(custid, YEAR(orderdate))
);
```
