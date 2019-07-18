// Name: TSQL lab02b
// Author: James Smelser
// Date: July 8, 2019

--------------------------------------
# TSQL Lab 02b
1. Who are our customers in North America?
select customerid, companyname, country from customers where country in ('USA', 'Canada', 'Mexico');
```
CustomerID|CompanyName|Country
ANATR|Ana Trujillo Emparedados y helados|Mexico
ANTON|Antonio Moreno Taquería|Mexico
BOTTM|Bottom-Dollar Markets|Canada
CENTC|Centro comercial Moctezuma|Mexico
GREAL|Great Lakes Food Market|USA
HUNGC|Hungry Coyote Import Store|USA
LAUGB|Laughing Bacchus Wine Cellars|Canada
LAZYK|Lazy K Kountry Store|USA
LETSS|Let''s Stop N Shop|USA
LONEP|Lonesome Pine Restaurant|USA
MEREP|Mère Paillarde|Canada
OLDWO|Old World Delicatessen|USA
PERIC|Pericles Comidas clásicas|Mexico
RATTC|Rattlesnake Canyon Grocery|USA
SAVEA|Save-a-lot Markets|USA
SPLIR|Split Rail Beer & Ale|USA
THEBI|The Big Cheese|USA
THECR|The Cracker Box|USA
TORTU|Tortuga Restaurante|Mexico
TRAIH|Trail''s Head Gourmet Provisioners|USA
WHITC|White Clover Markets|USA
```

2. What orders were placed in April, 1998?
select orderid, orderdate from orders where orderdate like '1998-04%';
```
OrderID|OrderDate
10990|1998-04-01
10991|1998-04-01
10992|1998-04-01
10993|1998-04-01
10994|1998-04-02
10995|1998-04-02
10996|1998-04-02
10997|1998-04-03
10998|1998-04-03
10999|1998-04-03
11000|1998-04-06
11001|1998-04-06
11002|1998-04-06
11003|1998-04-06
11004|1998-04-07
11005|1998-04-07
11006|1998-04-07
11007|1998-04-08
11008|1998-04-08
11009|1998-04-08
11010|1998-04-09
11011|1998-04-09
11012|1998-04-09
11013|1998-04-09
11014|1998-04-10
11015|1998-04-10
11016|1998-04-10
11017|1998-04-13
11018|1998-04-13
11019|1998-04-13
11020|1998-04-14
11021|1998-04-14
11022|1998-04-14
11023|1998-04-14
11024|1998-04-15
11025|1998-04-15
11026|1998-04-15
11027|1998-04-16
11028|1998-04-16
11029|1998-04-16
11030|1998-04-17
11031|1998-04-17
11032|1998-04-17
11033|1998-04-17
11034|1998-04-20
11035|1998-04-20
11036|1998-04-20
11037|1998-04-21
11038|1998-04-21
11039|1998-04-21
11040|1998-04-22
11041|1998-04-22
11042|1998-04-22
11043|1998-04-22
11044|1998-04-23
11045|1998-04-23
11046|1998-04-23
11047|1998-04-24
11048|1998-04-24
11049|1998-04-24
11050|1998-04-27
11051|1998-04-27
11052|1998-04-27
11053|1998-04-27
11054|1998-04-28
11055|1998-04-28
11056|1998-04-28
11057|1998-04-29
11058|1998-04-29
11059|1998-04-29
11060|1998-04-30
11061|1998-04-30
11062|1998-04-30
11063|1998-04-30
 ```

--3. What sauces do we sell?
select productid, productname from products where productname like '%sauce%';
```
ProductID|ProductName
8|Northwoods Cranberry Sauce
65|Louisiana Fiery Hot Pepper Sauce
```

--4. You sell some kind of dried fruit that I liked very much. What is its name?
select productname from products where productname like '%dried%';
```
ProductName
Uncle Bob's Organic Dried Pears
Manjimup Dried Apples
```

--5. What employees ship products to Germany in December?
select employeeid, shipcountry from orders where shippeddate like '%-12-%' and shipcountry like 'germany' group by employeeid;
```
EmployeeID|ShipCountry
1|Germany
3|Germany
4|Germany
```

--6. We have an issue with product 19. I need to know the total amount and the net amount of all orders
--for product 19 where the customer took a discount.
select productid, unitprice, quantity, unitprice * quantity as totalprice discount,
((unitprice * quantity) - (unitprice * quantity * discount)) as netprice
from order_details where productid = 19 and discount > 0;

--7. I need a list of employees by title, first name, and last name, with the employee's position under their
--names, and a line separating each employee.
select titleofcourtesy || '' || firstname || '' || lastname || '' || '
' || title || '
' from employees order by lastname;
titleofcourtesy || '' || firstname || '' || lastname || '' || '
' || title || '
'
```
Mr.StevenBuchanan
Sales Manager

Ms.LauraCallahan
Inside Sales Coordinator

Ms.NancyDavolio
Sales Representative

Ms.AnneDodsworth
Sales Representative

Dr.AndrewFuller
Vice President-Sales

Mr.RobertKing
Sales Representative

Ms.JanetLeverling
Sales Representative

Mrs.MargaretPeacock
Sales Representative

Mr.MichaelSuyama
Sales Representative
```

--8. I need a list of our customers and the first name only of the customer representative.
select substr(contactname,1,instr(contactname, ' ')-1), companyname from customers order by substr(contactname,instr(contactname,' ')+1);
substr(contactname,1,instr(contactname, ' ')-1)|CompanyName
```
Paolo|Franchi S.p.A.
Pedro|Comércio Mineiro
Maria|Alfreds Futterkiste
Miguel|Tortuga Restaurante
Victoria|B''s Beverages
Bernardo|Que Delícia
Helen|Island Trading
Christina|Berglunds snabbköp
Jonas|Santé Gourmet
Marie|Paris spécialités
Art|Split Rail Beer & Ale
Elizabeth|Consolidated Holdings
Alejandra|Romero y tomillo
Pascale|Suprêmes délices
Lúcia|Queen Cozinha
Francisco|Centro comercial Moctezuma
Frédérique|Blondesddsl père et fils
|CompanyName
Philip|Königlich Essen
Simon|North/South
Aria|Familia Arquibaldo
Ann|Eastern Connection
Catherine|Maison Dewey
Anabela|Tradição Hipermercados
Guillermo|Pericles Comidas clásicas
Alexander|Morgenstern Gesundkost
André|Gourmet Lanchonetes
Peter|Frankenversand
Jean|Mère Paillarde
Carlos|LILA-Supermercado
Sergio|Rancho grande
Thomas|Around the Horn
Paul|Vins et alcools Chevalier
Carlos|HILARION-Abastos
Michael|Richter Supermarkt
Palle|Vaffeljernet
Felipe|LINO-Delicateses
Karl|White Clover Markets
Karin|Toms Spezialitäten
Matti|Wilman Kala
Horst|QUICK-Stop
Pirkko|Wartian Herkku
Hari|Seven Seas Imports
Janine|Du monde entier
Maria|Folk och fä HB
Yoshi|Hungry Coyote Import Store
Laurence|Bon app''
Janete|Ricardo Adocicados
Elizabeth|Bottom-Dollar Markets
Patricia|Hungry Owl All-Night Grocers
Roland|Ernst Handel
Renate|Lehmanns Marktstand
Yvonne|Océano Atlántico Ltda.
Hanna|Blauer See Delikatessen
Antonio|Antonio Moreno Taquería
Maurizio|Reggiani Caseifici
Rita|Die Wandernde Kuh
Helvetius|Trail''s Head Gourmet Provisioners
Liz|The Big Cheese
Sven|Drachenblut Delikatessen
Paula|Wellington Importadora
Jose|Save-a-lot Markets
José|Godos Cocina Típica
Manuel|GROSELLA-Restaurante
Dominique|Spécialités du monde
Jytte|Simons bistro
Henriette|Ottilies Käseladen
Rene|Old World Delicatessen
Zbyszek|Wolski  Zajazd
Georg|Piccolo und mehr
Mario|Hanari Carnes
Martine|Folies gourmandes
Lino|Furia Bacalhau e Frutos do Mar
Diego|FISSA Fabrica Inter. Salchichas S.A.
Annette|La maison d''Asie
Giovanni|Magazzini Alimentari Riuniti
Eduardo|Galería del gastrónomo
Mary|Victuailles en stock
Carine|France restauration
Patricio|Cactus Comidas para llevar
Howard|Great Lakes Food Market
Martín|Bólido Comidas preparadas
John|Lazy K Kountry Store
Yoshi|Laughing Bacchus Wine Cellars
Daniel|La corne d''abondance
Ana|Ana Trujillo Emparedados y helados
Yang|Chop-suey Chinese
Fran|Lonesome Pine Restaurant
Paula|Rattlesnake Canyon Grocery
Liu|The Cracker Box
Jaime|Let''s Stop N Shop
Isabel|Princesa Isabel Vinhos
```

--9. Give me a list of our customer contacts alphabetically by last name.
select contactname from customers order by substr(contactname, instr(contactname, ' ')+1) collate nocase;
```
ContactName
Paolo Accorti
Pedro Afonso
Maria Anders
Miguel Angel Paolino
Victoria Ashworth
Bernardo Batista
Helen Bennett
Christina Berglund
Jonas Bergulfsen
Marie Bertrand
Art Braunschweiger
Elizabeth Brown
Alejandra Camino
Pascale Cartrain
Lúcia Carvalho
Francisco Chang
Frédérique Citeaux
ContactName
Philip Cramer
Simon Crowther
Aria Cruz
Isabel de Castro
Ann Devon
Catherine Dewey
Anabela Domingues
Guillermo Fernández
Alexander Feuer
André Fonseca
Peter Franken
Jean Fresnière
Carlos González
Sergio Gutiérrez
Thomas Hardy
Paul Henriot
Carlos Hernández
Michael Holz
Palle Ibsen
Felipe Izquierdo
Karl Jablonski
Karin Josephs
Matti Karttunen
Horst Kloss
Pirkko Koskitalo
Hari Kumar
Janine Labrune
Maria Larsson
Yoshi Latimer
Laurence Lebihan
Janete Limeira
Elizabeth Lincoln
Patricia McKenna
Roland Mendel
Renate Messner
Yvonne Moncada
Hanna Moos
Antonio Moreno
Maurizio Moroni
Rita Müller
Helvetius Nagy
Liz Nixon
Sven Ottlieb
Paula Parente
Jose Pavarotti
José Pedro Freyre
Manuel Pereira
Dominique Perrier
Jytte Petersen
Henriette Pfalzheim
Rene Phillips
Zbyszek Piestrzeniewicz
Georg Pipps
Mario Pontes
Martine Rancé
Lino Rodriguez
Diego Roel
Annette Roulet
Giovanni Rovelli
Eduardo Saavedra
Mary Saveley
Carine Schmitt
Patricio Simpson
Howard Snyder
Martín Sommer
John Steel
Yoshi Tannamuri
Daniel Tonini
Ana Trujillo
Yang Wang
Fran Wilson
Paula Wilson
Liu Wong
Jaime Yorres
```

--10. `I need a report telling me the most common pairing of customers and employees with the greatest
--order volume (by the number of orders placed). Exclude pairings with minimal orders.
select employeeid, customerid, count(orderid) as volume from orders group by employeeid, customerid having volume > 1;
```
EmployeeID|CustomerID|volume
1|ALFKI|2
1|AROUT|3
1|BERGS|4
1|BONAP|3
1|BOTTM|2
1|DRACD|2
1|EASTC|2
1|ERNSH|5
1|FRANK|5
1|FURIB|2
1|HANAR|3
1|HILAA|2
1|KOENE|4
1|LILAS|3
1|LINOD|2
1|MAGAA|2
1|MEREP|3
1|QUICK|4
1|RATTC|5
1|REGGC|2
1|RICAR|2
1|SANTG|2
1|SAVEA|6
1|SEVES|2
1|SPLIR|2
1|TORTU|4
1|TRADH|2
1|VAFFE|4
1|VICTE|2
1|WOLZA|2
2|BOTTM|2
2|ERNSH|3
2|FOLKO|3
2|FRANS|2
2|HUNGO|3
2|KOENE|2
2|LAMAI|2
2|LAUGB|2
2|LINOD|2
2|MAGAA|3
2|OTTIK|2
2|PERIC|2
2|PICCO|3
2|QUEDE|2
2|QUICK|6
2|REGGC|2
2|RICAR|2
2|SAVEA|4
2|SIMOB|2
2|SUPRD|2
2|TORTU|2
2|VINET|2
2|WARTH|3
2|WILMK|3
3|ANATR|2
3|ANTON|3
3|AROUT|2
3|BERGS|6
3|BLONP|2
3|BONAP|3
3|BOTTM|4
3|BSBEV|2
3|ERNSH|4
3|FOLKO|2
3|GODOS|2
3|GREAL|3
3|HANAR|4
3|HILAA|2
3|HUNGC|2
3|HUNGO|5
3|KOENE|2
3|LEHMS|4
3|LILAS|3
3|LINOD|3
3|MEREP|4
3|MORGK|2
3|NORTS|2
3|OLDWO|3
3|QUICK|5
3|RATTC|4
3|RICSU|2
3|SAVEA|2
3|SPLIR|2
3|TOMSP|2
3|VICTE|3
3|WELLI|3
3|WHITC|3
4|ALFKI|2
4|AROUT|4
4|BLONP|3
4|BOLID|2
4|BONAP|4
4|BOTTM|2
4|BSBEV|2
4|CHOPS|2
4|COMMI|2
4|EASTC|2
4|ERNSH|5
4|FAMIA|2
4|FOLKO|2
4|FRANK|4
4|FRANS|2
4|FURIB|3
4|GOURL|2
4|GREAL|4
4|HANAR|3
4|HILAA|5
4|ISLAT|4
4|LACOR|2
4|LAMAI|2
4|LEHMS|3
4|LINOD|2
4|LONEP|2
4|MAISD|2
4|OTTIK|4
4|QUEDE|2
4|QUEEN|2
4|QUICK|5
4|RANCH|2
4|RATTC|2
4|REGGC|3
4|RICAR|3
4|RICSU|2
4|ROMEY|3
4|SAVEA|4
4|SIMOB|2
4|SUPRD|4
4|TRADH|2
4|VICTE|2
4|WANDK|2
4|WARTH|2
4|WELLI|2
4|WHITC|4
4|WOLZA|2
5|BERGS|2
5|GODOS|2
5|LILAS|2
5|MAISD|2
5|PRINI|2
5|QUICK|2
5|RATTC|2
5|RICAR|2
5|SAVEA|3
5|SEVES|2
5|SUPRD|2
5|WARTH|2
6|BLONP|2
6|BOTTM|2
6|BSBEV|2
6|CHOPS|2
6|ERNSH|2
6|FOLKO|2
6|FRANK|2
6|GOURL|3
6|GREAL|2
6|HUNGO|3
6|LAMAI|3
6|LONEP|2
6|OTTIK|2
6|PICCO|2
6|QUEDE|2
6|QUEEN|3
6|SAVEA|4
6|TOMSP|2
7|ANTON|2
7|DUMON|2
7|EASTC|2
7|ERNSH|4
7|FOLKO|2
7|GODOS|3
7|HILAA|3
7|HUNGO|2
7|LAMAI|2
7|LEHMS|3
7|OCEAN|2
7|PICCO|2
7|QUEEN|3
7|RICSU|2
7|SANTG|2
7|SAVEA|3
7|SIMOB|3
7|WELLI|2
7|WHITC|2
8|BERGS|2
8|BONAP|2
8|CACTU|2
8|EASTC|2
8|ERNSH|4
8|FOLKO|6
8|FRANK|3
8|GALED|2
8|HILAA|3
8|LAMAI|2
8|LEHMS|3
8|LILAS|3
8|LINOD|2
8|MAGAA|2
8|MEREP|2
8|OLDWO|3
8|QUEDE|2
8|QUEEN|3
8|QUICK|4
8|RATTC|2
8|RICAR|2
8|SAVEA|4
8|SPLIR|2
8|VAFFE|2
8|VICTE|2
8|WANDK|4
8|WARTH|4
8|WHITC|2
9|AROUT|2
9|BERGS|2
9|BLAUS|3
9|BONAP|2
9|ERNSH|3
9|HUNGO|3
9|KOENE|4
9|REGGC|2
9|RICSU|2
```
