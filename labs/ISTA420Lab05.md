// Name: TSQL Lab05
// Author: James Smelser
// Date: July 23, 2019

---------------------------------------------------------------------
# Chapter 05 In-class Lab Assignment
## ISTA-420, T-SQL Fundamentals
### In-class Lab | Table expressions
#### Using the Northwind database
#### Use common table expressions or views to execute the following queries. Note that it may be possible to use joins and sets to do the same thing.

1. List the number of orders by each customer who lives in the United States using a CTE. Sort from
highest to lowest.
with USAcustomer as (select customerid from customers where country like 'USA')select o.customerid, count(o.customerid) as count from orders o where o.customerid in USAcustomer group by o.customerid order by count desc;
```
CustomerID|count
SAVEA|31
RATTC|18
WHITC|14
GREAL|11
OLDWO|10
SPLIR|9
LONEP|8
HUNGC|5
LETSS|4
THEBI|4
THECR|3
TRAIH|3
LAZYK|2
```

2. List the product name and the number of each product from a German supplier sold to a customer in
Germany using a CTE. Sort from highest to lowest.
with GERprod as (select s.supplierid, s.country, p.supplierid, p.productid as pid, p.productname from suppliers s join products p on s.supplierid = p.supplierid where s.country like 'Germany'), GERord as (select d.productid as pid, d.quantity, d.orderid, o.orderid, o.shipcountry from orders o join order_details d on o.orderid = d.orderid where o.shipcountry like 'Germany')select distinct gp.productname, sum(go.quantity) as TotalSold from GERprod gp join GERord as go on gp.pid = go.pid group by
gp.productname order by TotalSold desc;
```
productname|TotalSold
Wimmers gute Semmelknödel|208
Gumbär Gummibärchen|202
Original Frankfurter grüne Soße|198
Rhönbräu Klosterbier|156
Schoggi Schokolade|135
Nord-Ost Matjeshering|108
Thüringer Rostbratwurst|96
Rössle Sauerkraut|44
NuNuCa Nuß-Nougat-Creme|22
```

--3. Prepare an employee report showing the name of each employee, the number of employees they super-
--vise, and the name of their supervisor using a CTE. Sort by the number of employees supervised.
WITH EmployeeSubordinatesReport (EmployeeID, LastName, FirstName, NumberOfSubordinates, ReportsTo) AS (SELECT EmployeeID, LastName, FirstName, (SELECT COUNT(1) FROM Employees e2 WHERE e2.ReportsTo = e.EmployeeID) as NumberOfSubordinates, ReportsTo FROM Employees e) SELECT Employee.LastName, Employee.FirstName, Employee.NumberOfSubordinates, Manager.LastName as ManagerLastName , Manager.FirstName as ManagerFirstName FROM EmployeeSubordinatesReport Employee LEFT JOIN EmployeeSubordinatesReport Manager ON Employee.ReportsTo = Manager.EmployeeID order by Employee.NumberOfSubordinates desc;
```
LastName|FirstName|NumberOfSubordinates|ManagerLastName|ManagerFirstName
Fuller|Andrew|5||
Buchanan|Steven|3|Fuller|Andrew
Davolio|Nancy|0|Fuller|Andrew
Leverling|Janet|0|Fuller|Andrew
Peacock|Margaret|0|Fuller|Andrew
Suyama|Michael|0|Buchanan|Steven
King|Robert|0|Buchanan|Steven
Callahan|Laura|0|Fuller|Andrew
Dodsworth|Anne|0|Buchanan|Steven
```

--4. One purpose of views is to denormalize databases for the purpose of effeciency, both machine effeciency
--and programmer effeciency. Creating denormalized objects can turn complex queries into simple ones.
--For example, suppose you needed a list of all employees who took orders for a specific customer, or all
--customers who were served by a specific employee. You can create a \table" as a view that contains
--distinct pairs of customers and employees. This is somewhat complex, so do this in steps.

drop view if exists CustEmpPairs;
create view CustEmpPairs as with CustEmpPairs (cid, eid) as (select distinct customerid, employeeid from orders) select c.customerid, c.companyname, c.contactname, e.employeeid, e.firstname, e.lastname from customers c, employees e, CustEmpPairs o where o.eid = e.employeeid and o.cid = c.customerid;

select * from CustEmpPairs where employeeid = 7;
```
CustomerID|CompanyName|ContactName|EmployeeID|FirstName|LastName
ANATR|Ana Trujillo Emparedados y helados|Ana Trujillo|7|Robert|King
ANTON|Antonio Moreno Taquería|Antonio Moreno|7|Robert|King
BONAP|Bon app''|Laurence Lebihan|7|Robert|King
BOTTM|Bottom-Dollar Markets|Elizabeth Lincoln|7|Robert|King
BSBEV|B''s Beverages|Victoria Ashworth|7|Robert|King
CACTU|Cactus Comidas para llevar|Patricio Simpson|7|Robert|King
CHOPS|Chop-suey Chinese|Yang Wang|7|Robert|King
CONSH|Consolidated Holdings|Elizabeth Brown|7|Robert|King
DRACD|Drachenblut Delikatessen|Sven Ottlieb|7|Robert|King
DUMON|Du monde entier|Janine Labrune|7|Robert|King
EASTC|Eastern Connection|Ann Devon|7|Robert|King
ERNSH|Ernst Handel|Roland Mendel|7|Robert|King
FAMIA|Familia Arquibaldo|Aria Cruz|7|Robert|King
FOLKO|Folk och fä HB|Maria Larsson|7|Robert|King
GODOS|Godos Cocina Típica|José Pedro Freyre|7|Robert|King
GOURL|Gourmet Lanchonetes|André Fonseca|7|Robert|King
HILAA|HILARION-Abastos|Carlos Hernández|7|Robert|King
HUNGO|Hungry Owl All-Night Grocers|Patricia McKenna|7|Robert|King
LAMAI|La maison d''Asie|Annette Roulet|7|Robert|King
LEHMS|Lehmanns Marktstand|Renate Messner|7|Robert|King
MAGAA|Magazzini Alimentari Riuniti|Giovanni Rovelli|7|Robert|King
MAISD|Maison Dewey|Catherine Dewey|7|Robert|King
MEREP|Mère Paillarde|Jean Fresnière|7|Robert|King
OCEAN|Océano Atlántico Ltda.|Yvonne Moncada|7|Robert|King
PERIC|Pericles Comidas clásicas|Guillermo Fernández|7|Robert|King
PICCO|Piccolo und mehr|Georg Pipps|7|Robert|King
PRINI|Princesa Isabel Vinhos|Isabel de Castro|7|Robert|King
QUEEN|Queen Cozinha|Lúcia Carvalho|7|Robert|King
QUICK|QUICK-Stop|Horst Kloss|7|Robert|King
REGGC|Reggiani Caseifici|Maurizio Moroni|7|Robert|King
RICSU|Richter Supermarkt|Michael Holz|7|Robert|King
SANTG|Santé Gourmet|Jonas Bergulfsen|7|Robert|King
SAVEA|Save-a-lot Markets|Jose Pavarotti|7|Robert|King
SEVES|Seven Seas Imports|Hari Kumar|7|Robert|King
SIMOB|Simons bistro|Jytte Petersen|7|Robert|King
SPLIR|Split Rail Beer & Ale|Art Braunschweiger|7|Robert|King
SUPRD|Suprêmes délices|Pascale Cartrain|7|Robert|King
THECR|The Cracker Box|Liu Wong|7|Robert|King
TORTU|Tortuga Restaurante|Miguel Angel Paolino|7|Robert|King
TRADH|Tradição Hipermercados|Anabela Domingues|7|Robert|King
VAFFE|Vaffeljernet|Palle Ibsen|7|Robert|King
WANDK|Die Wandernde Kuh|Rita Müller|7|Robert|King
WELLI|Wellington Importadora|Paula Parente|7|Robert|King
WHITC|White Clover Markets|Karl Jablonski|7|Robert|King
WILMK|Wilman Kala|Matti Karttunen|7|Robert|King
```

select * from CustEmpPairs where customerid like 'CHOPS';
```
CustomerID|CompanyName|ContactName|EmployeeID|FirstName|LastName
CHOPS|Chop-suey Chinese|Yang Wang|5|Steven|Buchanan
CHOPS|Chop-suey Chinese|Yang Wang|6|Michael|Suyama
CHOPS|Chop-suey Chinese|Yang Wang|7|Robert|King
CHOPS|Chop-suey Chinese|Yang Wang|1|Nancy|Davolio
CHOPS|Chop-suey Chinese|Yang Wang|4|Margaret|Peacock
CHOPS|Chop-suey Chinese|Yang Wang|3|Janet|Leverling
```

drop view if exists CustEmpPairs;
