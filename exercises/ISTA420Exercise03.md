// Name: TSQL Exercise 03
// Author: James Smelser
// Date: July 19, 2019

-----------------------------------------------------------
# Programming Exercise 03
## Joins and Subqueries
### T-SQL Fundamentals
1. Using SQLite and the Northwind database, create a line item report that contains a line for each
product in the order with the following columns: the order id, the product id, the unit price, the
quantity sold, the line item price, and the percent of that line item constitutes of the total amount of
the order.
select orderid, productid, unitprice, quantity, (unitprice * quantity) as linetotal, round(100*((unitprice * quantity)/(select sum(unitprice * quantity) from order_details as od2 where od2.orderid = od1.orderid)), 2) pctoftotalorder from order_details as od1 limit 25;
```
OrderID|ProductID|UnitPrice|Quantity|linetotal|pctoftotalorder
10248|11|14.0|12|168.0|38.18
10248|42|9.8|10|98.0|22.27
10248|72|34.8|5|174.0|39.55
10249|14|18.6|9|167.4|8.98
10249|51|42.4|40|1696.0|91.02
10250|41|7.7|10|77.0|4.25
10250|51|42.4|35|1484.0|81.85
10250|65|16.8|15|252.0|13.9
10251|22|16.8|6|100.8|15.03
10251|57|15.6|15|234.0|34.88
10251|65|16.8|20|336.0|50.09
10252|20|64.8|40|2592.0|69.49
10252|33|2.0|25|50.0|1.34
10252|60|27.2|40|1088.0|29.17
10253|31|10.0|20|200.0|13.84
10253|39|14.4|42|604.8|41.86
10253|49|16.0|40|640.0|44.3
10254|24|3.6|15|54.0|8.64
10254|55|19.2|21|403.2|64.49
10254|74|8.0|21|168.0|26.87
10255|2|15.2|20|304.0|12.21
10255|16|13.9|35|486.5|19.53
10255|36|15.2|25|380.0|15.26
10255|59|44.0|30|1320.0|53.0
10256|53|26.2|15|393.0|75.9
```

2. I want to know the unique (distinct) cities, regions, and postal codes: (a) where we have both customers
and employees, (b) where we have customers but no employees AND both customers ad employees,
and (c) where we have employees but no customers AND both customers and employees. Write three
queries, using inner and outer joins. Report the results of the queries. There is no need for any further
reporting.
select distinct e.city, e.region, e.postalcode, c.city, c.region, c.postalcode from employees as e left join customers as c limit 25;
```
City|Region|PostalCode|City|Region|PostalCode
Seattle|WA|98122|City|Region|PostalCode
Seattle|WA|98122|Berlin||12209
Seattle|WA|98122|México D.F.||05021
Seattle|WA|98122|México D.F.||05023
Seattle|WA|98122|London||WA1 1DP
Seattle|WA|98122|Luleå||S-958 22
Seattle|WA|98122|Mannheim||68306
Seattle|WA|98122|Strasbourg||67000
Seattle|WA|98122|Madrid||28023
Seattle|WA|98122|Marseille||13008
Seattle|WA|98122|Tsawassen|BC|T2F 8M4
Seattle|WA|98122|London||EC2 5NT
Seattle|WA|98122|Buenos Aires||1010
Seattle|WA|98122|México D.F.||05022
Seattle|WA|98122|Bern||3012
Seattle|WA|98122|Sao Paulo|SP|05432-043
Seattle|WA|98122|London||WX1 6LT
Seattle|WA|98122|Aachen||52066
Seattle|WA|98122|Nantes||44000
Seattle|WA|98122|London||WX3 6FW
Seattle|WA|98122|Graz||8010
Seattle|WA|98122|Sao Paulo|SP|05442-030
Seattle|WA|98122|Madrid||28034
Seattle|WA|98122|Lille||59000
Seattle|WA|98122|Bräcke||S-844 67
```

select distinct e.city, e.region, e.postalcode, c.city, c.region, c.postalcode from employees as e left join customers as c where c.customerid is not null limit 25;
```
City|Region|PostalCode|City|Region|PostalCode
Seattle|WA|98122|City|Region|PostalCode
Tacoma|WA|98401|City|Region|PostalCode
Kirkland|WA|98033|City|Region|PostalCode
Redmond|WA|98052|City|Region|PostalCode
London|NULL|SW1 8JR|City|Region|PostalCode
London|NULL|EC2 7JR|City|Region|PostalCode
London|NULL|RG1 9SP|City|Region|PostalCode
Seattle|WA|98105|City|Region|PostalCode
London|NULL|WG2 7LT|City|Region|PostalCode
Seattle|WA|98122|Berlin||12209
Tacoma|WA|98401|Berlin||12209
Kirkland|WA|98033|Berlin||12209
Redmond|WA|98052|Berlin||12209
London|NULL|SW1 8JR|Berlin||12209
London|NULL|EC2 7JR|Berlin||12209
London|NULL|RG1 9SP|Berlin||12209
Seattle|WA|98105|Berlin||12209
London|NULL|WG2 7LT|Berlin||12209
Seattle|WA|98122|México D.F.||05021
Tacoma|WA|98401|México D.F.||05021
Kirkland|WA|98033|México D.F.||05021
Redmond|WA|98052|México D.F.||05021
London|NULL|SW1 8JR|México D.F.||05021
London|NULL|EC2 7JR|México D.F.||05021
London|NULL|RG1 9SP|México D.F.||05021
```

select distinct e.city, e.region, e.postalcode, c.city, c.region, c.postalcode from employees as e left join customers as c where e.employeeid is not null limit 25;
```
City|Region|PostalCode|City|Region|PostalCode
Seattle|WA|98122|City|Region|PostalCode
Seattle|WA|98122|Berlin||12209
Seattle|WA|98122|México D.F.||05021
Seattle|WA|98122|México D.F.||05023
Seattle|WA|98122|London||WA1 1DP
Seattle|WA|98122|Luleå||S-958 22
Seattle|WA|98122|Mannheim||68306
Seattle|WA|98122|Strasbourg||67000
Seattle|WA|98122|Madrid||28023
Seattle|WA|98122|Marseille||13008
Seattle|WA|98122|Tsawassen|BC|T2F 8M4
Seattle|WA|98122|London||EC2 5NT
Seattle|WA|98122|Buenos Aires||1010
Seattle|WA|98122|México D.F.||05022
Seattle|WA|98122|Bern||3012
Seattle|WA|98122|Sao Paulo|SP|05432-043
Seattle|WA|98122|London||WX1 6LT
Seattle|WA|98122|Aachen||52066
Seattle|WA|98122|Nantes||44000
Seattle|WA|98122|London||WX3 6FW
Seattle|WA|98122|Graz||8010
Seattle|WA|98122|Sao Paulo|SP|05442-030
Seattle|WA|98122|Madrid||28034
Seattle|WA|98122|Lille||59000
Seattle|WA|98122|Bräcke||S-844 67
```

3. Using subqueries, create a report that lists the ten most expensive products.
select o1.productid, o1.productname, o1.unitprice from products as o1 where (select o2.unitprice from products as o2) order by o1.unitprice desc limit 10;
```
ProductID|ProductName|UnitPrice
38|Côte de Blaye|263.5
29|Thüringer Rostbratwurst|123.79
9|Mishi Kobe Niku|97.0
20|Sir Rodney's Marmalade|81.0
18|Carnarvon Tigers|62.5
59|Raclette Courdavault|55.0
51|Manjimup Dried Apples|53.0
62|Tarte au sucre|49.3
43|Ipoh Coffee|46.0
28|Rössle Sauerkraut|45.6
```

4. Using subqueries, create a report that shows the date of the last order by all employees.
select o1.orderdate, o1.employeeid from orders as o1 where o1.orderdate = (select max(orderdate) from orders as o2 where o2.employeeid = o1.employeeid) group by o1.employeeid order by o1.employeeid;
```
OrderDate|EmployeeID
1998-05-06|1
1998-05-05|2
1998-04-30|3
1998-05-06|4
1998-04-22|5
1998-04-23|6
1998-05-06|7
1998-05-06|8
1998-04-29|9
```

5. Using subqueries, create a line item report that contains a line for each product in the order with the
following columns: the order id, the product id, the unit price, the quantity sold, the line item price,
and the percent of that line item constitutes of the total amount of the order.
select orderid, productid, unitprice, quantity, (unitprice * quantity) as linetotal, round(100*((unitprice * quantity)/(select sum(unitprice * quantity) from order_details as od2 where od2.orderid = od1.orderid)), 2) pctoftotalorder from order_details as od1 limit 25;
```
OrderID|ProductID|UnitPrice|Quantity|linetotal|pctoftotalorder
10248|11|14.0|12|168.0|38.18
10248|42|9.8|10|98.0|22.27
10248|72|34.8|5|174.0|39.55
10249|14|18.6|9|167.4|8.98
10249|51|42.4|40|1696.0|91.02
10250|41|7.7|10|77.0|4.25
10250|51|42.4|35|1484.0|81.85
10250|65|16.8|15|252.0|13.9
10251|22|16.8|6|100.8|15.03
10251|57|15.6|15|234.0|34.88
10251|65|16.8|20|336.0|50.09
10252|20|64.8|40|2592.0|69.49
10252|33|2.0|25|50.0|1.34
10252|60|27.2|40|1088.0|29.17
10253|31|10.0|20|200.0|13.84
10253|39|14.4|42|604.8|41.86
10253|49|16.0|40|640.0|44.3
10254|24|3.6|15|54.0|8.64
10254|55|19.2|21|403.2|64.49
10254|74|8.0|21|168.0|26.87
10255|2|15.2|20|304.0|12.21
10255|16|13.9|35|486.5|19.53
10255|36|15.2|25|380.0|15.26
10255|59|44.0|30|1320.0|53.0
10256|53|26.2|15|393.0|75.9
```
