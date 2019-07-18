// Name: SQL Lab 2a
// Author: James Smelser
// Date: July 2, 2019

-----------------------------------------------
# TSQL Lab 02a
1. What are the regions?
```
select * from region;
RegionID|RegionDescription
1|Eastern
2|Western
3|Northern
4|Southern
```
2. What are the cities?
```
select * from territories;
TerritoryID|TerritoryDescription|RegionID
TerritoryID|TerritoryDescription|RegionID
01581|Westboro|1
01730|Bedford|1
01833|Georgetow|1
02116|Boston|1
02139|Cambridge|1
02184|Braintree|1
02903|Providence|1
03049|Hollis|3
03801|Portsmouth|3
06897|Wilton|1
07960|Morristown|1
08837|Edison|1
10019|NewYork|1
10038|NewYork|1
11747|Mellvile|1
14450|Fairport|1
19428|Philadelphia|3
19713|Neward|1
20852|Rockville|1
27403|Greensboro|1
27511|Cary|1
29202|Columbia|4
30346|Atlanta|4
31406|Savannah|4
32859|Orlando|4
33607|Tampa|4
40222|Louisville|1
44122|Beachwood|3
45839|Findlay|3
48075|Southfield|3
48084|Troy|3
48304|BloomfieldHills|3
53404|Racine|3
55113|Roseville|3
55439|Minneapolis|3
60179|HoffmanEstates|2
60601|Chicago|2
72716|Bentonville|4
75234|Dallas|4
78759|Austin|4
80202|Denver|2
80909|ColoradoSprings|2
85014|Phoenix|2
85251|Scottsdale|2
90405|SantaMonica|2
94025|MenloPark|2
94105|SanFrancisco|2
95008|Campbell|2
95054|SantaClara|2
95060|SantaCruz|2
98004|Bellevue|2
98052|Redmond|2
98104|Seattle|2
```
3. What are the cities in the Southern region?
```
select * from territories where regionid = 4;
TerritoryID|TerritoryDescription|RegionID
29202|Columbia|4
30346|Atlanta|4
31406|Savannah|4
32859|Orlando|4
33607|Tampa|4
72716|Bentonville|4
75234|Dallas|4
78759|Austin|4
```
4. How do you run this query with the fully qualified column name?
```
select territories.territoryid, territories.territorydescription, territories.regionid from territories where regionid = 4;
TerritoryID|TerritoryDescription|RegionID
29202|Columbia|4
30346|Atlanta|4
31406|Savannah|4
32859|Orlando|4
33607|Tampa|4
72716|Bentonville|4
75234|Dallas|4
78759|Austin|4
```
5. How do you run this query with a table alias?
```
select T.territoryid, T.territorydescription, T.regionid from territories T where regionid = 4;
TerritoryID|TerritoryDescription|RegionID
29202|Columbia|4
30346|Atlanta|4
31406|Savannah|4
32859|Orlando|4
33607|Tampa|4
72716|Bentonville|4
75234|Dallas|4
78759|Austin|4
```
6. What is the contact name, telephone number, and city for each customer?
```
select contactname, companyname, city, phone from customers;
ContactName|CompanyName|City|Phone
ContactName|CompanyName|City|Phone
Maria Anders|Alfreds Futterkiste|Berlin|030-0074321
Ana Trujillo|Ana Trujillo Emparedados y helados|México D.F.|(5) 555-4729
Antonio Moreno|Antonio Moreno Taquería|México D.F.|(5) 555-3932
Thomas Hardy|Around the Horn|London|(171) 555-7788
Christina Berglund|Berglunds snabbköp|Luleå|0921-12 34 65
Hanna Moos|Blauer See Delikatessen|Mannheim|0621-08460
Frédérique Citeaux|Blondesddsl père et fils|Strasbourg|88.60.15.31
Martín Sommer|Bólido Comidas preparadas|Madrid|(91) 555 22 82
Laurence Lebihan|Bon app''|Marseille|91.24.45.40
Elizabeth Lincoln|Bottom-Dollar Markets|Tsawassen|(604) 555-4729
Victoria Ashworth|B''s Beverages|London|(171) 555-1212
Patricio Simpson|Cactus Comidas para llevar|Buenos Aires|(1) 135-5555
Francisco Chang|Centro comercial Moctezuma|México D.F.|(5) 555-3392
Yang Wang|Chop-suey Chinese|Bern|0452-076545
Pedro Afonso|Comércio Mineiro|Sao Paulo|(11) 555-7647
Elizabeth Brown|Consolidated Holdings|London|(171) 555-2282
Sven Ottlieb|Drachenblut Delikatessen|Aachen|0241-039123
Janine Labrune|Du monde entier|Nantes|40.67.88.88
Ann Devon|Eastern Connection|London|(171) 555-0297
Roland Mendel|Ernst Handel|Graz|7675-3425
Aria Cruz|Familia Arquibaldo|Sao Paulo|(11) 555-9857
Diego Roel|FISSA Fabrica Inter. Salchichas S.A.|Madrid|(91) 555 94 44
Martine Rancé|Folies gourmandes|Lille|20.16.10.16
Maria Larsson|Folk och fä HB|Bräcke|0695-34 67 21
Peter Franken|Frankenversand|München|089-0877310
Carine Schmitt|France restauration|Nantes|40.32.21.21
Paolo Accorti|Franchi S.p.A.|Torino|011-4988260
Lino Rodriguez|Furia Bacalhau e Frutos do Mar|Lisboa|(1) 354-2534
Eduardo Saavedra|Galería del gastrónomo|Barcelona|(93) 203 4560
José Pedro Freyre|Godos Cocina Típica|Sevilla|(95) 555 82 82
André Fonseca|Gourmet Lanchonetes|Campinas|(11) 555-9482
Howard Snyder|Great Lakes Food Market|Eugene|(503) 555-7555
Manuel Pereira|GROSELLA-Restaurante|Caracas|(2) 283-2951
Mario Pontes|Hanari Carnes|Rio de Janeiro|(21) 555-0091
Carlos Hernández|HILARION-Abastos|San Cristóbal|(5) 555-1340
Yoshi Latimer|Hungry Coyote Import Store|Elgin|(503) 555-6874
Patricia McKenna|Hungry Owl All-Night Grocers|Cork|2967 542
Helen Bennett|Island Trading|Cowes|(198) 555-8888
Philip Cramer|Königlich Essen|Brandenburg|0555-09876
Daniel Tonini|La corne d''abondance|Versailles|30.59.84.10
Annette Roulet|La maison d''Asie|Toulouse|61.77.61.10
Yoshi Tannamuri|Laughing Bacchus Wine Cellars|Vancouver|(604) 555-3392
John Steel|Lazy K Kountry Store|Walla Walla|(509) 555-7969
Renate Messner|Lehmanns Marktstand|Frankfurt a.M.|069-0245984
Jaime Yorres|Let''s Stop N Shop|San Francisco|(415) 555-5938
Carlos González|LILA-Supermercado|Barquisimeto|(9) 331-6954
Felipe Izquierdo|LINO-Delicateses|I. de Margarita|(8) 34-56-12
Fran Wilson|Lonesome Pine Restaurant|Portland|(503) 555-9573
Giovanni Rovelli|Magazzini Alimentari Riuniti|Bergamo|035-640230
Catherine Dewey|Maison Dewey|Bruxelles|(02) 201 24 67
Jean Fresnière|Mère Paillarde|Montréal|(514) 555-8054
Alexander Feuer|Morgenstern Gesundkost|Leipzig|0342-023176
Simon Crowther|North/South|London|(171) 555-7733
Yvonne Moncada|Océano Atlántico Ltda.|Buenos Aires|(1) 135-5333
Rene Phillips|Old World Delicatessen|Anchorage|(907) 555-7584
Henriette Pfalzheim|Ottilies Käseladen|Köln|0221-0644327
Marie Bertrand|Paris spécialités|Paris|(1) 42.34.22.66
Guillermo Fernández|Pericles Comidas clásicas|México D.F.|(5) 552-3745
Georg Pipps|Piccolo und mehr|Salzburg|6562-9722
Isabel de Castro|Princesa Isabel Vinhos|Lisboa|(1) 356-5634
Bernardo Batista|Que Delícia|Rio de Janeiro|(21) 555-4252
Lúcia Carvalho|Queen Cozinha|Sao Paulo|(11) 555-1189
Horst Kloss|QUICK-Stop|Cunewalde|0372-035188
Sergio Gutiérrez|Rancho grande|Buenos Aires|(1) 123-5555
Paula Wilson|Rattlesnake Canyon Grocery|Albuquerque|(505) 555-5939
Maurizio Moroni|Reggiani Caseifici|Reggio Emilia|0522-556721
Janete Limeira|Ricardo Adocicados|Rio de Janeiro|(21) 555-3412
Michael Holz|Richter Supermarkt|Genève|0897-034214
Alejandra Camino|Romero y tomillo|Madrid|(91) 745 6200
Jonas Bergulfsen|Santé Gourmet|Stavern|07-98 92 35
Jose Pavarotti|Save-a-lot Markets|Boise|(208) 555-8097
Hari Kumar|Seven Seas Imports|London|(171) 555-1717
Jytte Petersen|Simons bistro|Kobenhavn|31 12 34 56
Dominique Perrier|Spécialités du monde|Paris|(1) 47.55.60.10
Art Braunschweiger|Split Rail Beer & Ale|Lander|(307) 555-4680
Pascale Cartrain|Suprêmes délices|Charleroi|(071) 23 67 22 20
Liz Nixon|The Big Cheese|Portland|(503) 555-3612
Liu Wong|The Cracker Box|Butte|(406) 555-5834
Karin Josephs|Toms Spezialitäten|Münster|0251-031259
Miguel Angel Paolino|Tortuga Restaurante|México D.F.|(5) 555-2933
Anabela Domingues|Tradição Hipermercados|Sao Paulo|(11) 555-2167
Helvetius Nagy|Trail''s Head Gourmet Provisioners|Kirkland|(206) 555-8257
Palle Ibsen|Vaffeljernet|Århus|86 21 32 43
Mary Saveley|Victuailles en stock|Lyon|78.32.54.86
Paul Henriot|Vins et alcools Chevalier|Reims|26.47.15.10
Rita Müller|Die Wandernde Kuh|Stuttgart|0711-020361
Pirkko Koskitalo|Wartian Herkku|Oulu|981-443655
Paula Parente|Wellington Importadora|Resende|(14) 555-8122
Karl Jablonski|White Clover Markets|Seattle|(206) 555-4112
Matti Karttunen|Wilman Kala|Helsinki|90-224 8858
Zbyszek Piestrzeniewicz|Wolski  Zajazd|Warszawa|(26) 642-7012
```
7. What are the products currently out of stock?
```
select productid, productname, unitsinstock from products where unitsinstock = 0;
ProductID|ProductName|UnitsInStock
5|Chef Anton's Gumbo Mix|0
17|Alice Mutton|0
29|Thüringer Rostbratwurst|0
31|Gorgonzola Telino|0
53|Perth Pasties|0
```
8. What are the ten products currently in stock with the least amount on hand?
```
select productid, productname, unitsinstock from products where unitsinstock > 0 order by unitsinstock limit 10;
ProductID|ProductName|UnitsInStock
21|Sir Rodney's Scones|3
66|Louisiana Hot Spiced Okra|4
74|Longlife Tofu|4
45|Rogede sild|5
8|Northwoods Cranberry Sauce|6
68|Scottish Longbreads|6
32|Mascarpone Fabioli|9
30|Nord-Ost Matjeshering|10
49|Maxilaku|10
37|Gravad lax|11
```
9. What are the five most expensive products in stock?
```
select productid, productname, unitprice from products where unitsinstock > 0 order by unitprice desc limit 5;
ProductID|ProductName|UnitPrice
38|Côte de Blaye|263.5
9|Mishi Kobe Niku|97.0
20|Sir Rodney's Marmalade|81.0
18|Carnarvon Tigers|62.5
59|Raclette Courdavault|55.0
 ```
10. How many products does Northwind have? How many customers? How many suppliers?
```
select count(*) from products;
count(*)
77
select count(*) as number_of_customers from customers;
number_of_customers
92
select count(*) as number_of_suppliers from suppliers;
number_of_suppliers
29
```
