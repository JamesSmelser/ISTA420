// Name: TSQL lab04
// Author: James Smelser
// Date: July 16, 2019

------------------------------------------------------------------------
# TSQL Lab 04
1. Create a report that shows all orders taken by Janet.
select o.employeeid, o.orderid from orders o where o.employeeid in (select e.employeeid from employees e where firstname = "Janet");
```
EmployeeID|OrderID
3|10251
3|10253
3|10256
3|10266
3|10273
3|10283
3|10309
3|10321
3|10330
3|10332
3|10346
3|10352
3|10362
3|10365
3|10375
3|10381
3|10384
3|10391
3|10409
3|10410
3|10413
3|10415
3|10420
3|10429
3|10432
3|10433
3|10434
3|10436
3|10438
3|10441
3|10442
3|10444
3|10445
3|10449
3|10468
3|10479
3|10484
3|10492
3|10495
3|10505
3|10514
3|10517
3|10530
3|10536
3|10540
3|10547
3|10548
3|10568
3|10570
3|10572
3|10576
3|10581
3|10582
3|10592
3|10594
3|10619
3|10625
3|10638
3|10644
3|10662
3|10681
3|10682
3|10684
3|10693
3|10697
3|10699
3|10700
3|10712
3|10715
3|10723
3|10732
3|10739
3|10742
3|10748
3|10751
3|10753
3|10758
3|10759
3|10762
3|10763
3|10765
3|10768
3|10769
3|10772
3|10778
3|10779
3|10793
3|10796
3|10806
3|10814
3|10817
3|10820
3|10831
3|10838
3|10839
3|10854
3|10855
3|10856
3|10860
3|10879
3|10895
3|10897
3|10903
3|10904
3|10911
3|10918
3|10924
3|10925
3|10934
3|10936
3|10938
3|10947
3|10948
3|10960
3|10964
3|10974
3|10988
3|11003
3|11004
3|11006
3|11011
3|11021
3|11041
3|11049
3|11052
3|11057
3|11063
```

2. Create a report that shows all products by name that are in the Seafood category.
select p.categoryid, p.productname from products p where p.categoryid in (select c.categoryid from categories c where categoryid = 8);
```
CategoryID|ProductName
8|Ikura
8|Konbu
8|Carnarvon Tigers
8|Nord-Ost Matjeshering
8|Inlagd Sill
8|Gravad lax
8|Boston Crab Meat
8|Jack's New England Clam Chowder
8|Rogede sild
8|Spegesild
8|Escargots de Bourgogne
8|Röd Kaviar
```

3. Create a report that shows all orders taken by any employee whose last name begins with A."
select o.employeeid, o.orderid from orders o where o.employeeid in (select e.employeeid from employees e where lastname like 'D%');
```
EmployeeID|OrderID
9|10255
1|10258
9|10263
1|10270
1|10275
1|10285
1|10292
1|10293
1|10304
1|10306
1|10311
1|10314
1|10316
9|10324
1|10325
9|10331
1|10340
1|10351
1|10357
1|10361
1|10364
1|10371
1|10374
1|10376
1|10377
1|10385
9|10386
1|10387
1|10393
1|10394
1|10396
1|10400
1|10401
1|10405
9|10411
1|10453
1|10461
1|10465
1|10469
1|10473
9|10475
1|10482
1|10486
9|10501
9|10506
1|10508
1|10524
1|10525
1|10537
9|10538
1|10542
1|10546
9|10557
1|10558
1|10562
9|10566
1|10567
9|10577
1|10579
9|10586
1|10587
1|10591
1|10598
1|10604
1|10605
1|10612
1|10616
1|10618
1|10626
1|10630
9|10646
1|10653
1|10655
1|10664
1|10665
1|10668
1|10671
9|10672
1|10677
1|10680
9|10687
1|10689
1|10690
9|10705
1|10709
1|10710
1|10713
1|10717
1|10718
1|10733
9|10736
1|10743
9|10745
1|10746
9|10750
9|10771
1|10773
1|10776
9|10782
1|10785
1|10788
1|10789
1|10792
9|10799
1|10800
1|10813
1|10821
1|10825
1|10827
9|10828
9|10829
1|10834
1|10835
9|10837
1|10842
9|10849
1|10850
9|10853
1|10859
9|10871
1|10877
1|10886
1|10888
9|10889
9|10893
1|10894
1|10900
1|10902
9|10905
1|10909
1|10910
1|10916
1|10921
1|10928
9|10942
1|10946
1|10950
9|10951
1|10952
9|10953
9|10963
1|10968
1|10969
9|10970
1|10975
1|10976
9|10978
1|10981
1|10984
1|10991
1|10992
1|10995
1|11012
9|11016
9|11017
9|11022
1|11023
1|11027
1|11038
1|11039
9|11058
1|11064
1|11067
1|11069
1|11071
1|11077
```

4. Create a report that shows the product name and supplier id for all products supplied by Exotic
Liquids, Grandma Kelly's Homestead, and Tokyo Traders.
select p.supplierid, p.productname from products p where p.supplierid in (select s.supplierid from suppliers s where companyname in ("Exotic Liquids", "Grandma Kelly's Homestead", "Tokyo Traders"));
```
SupplierID|ProductName
1|Chai
1|Chang
1|Aniseed Syrup
3|Grandma's Boysenberry Spread
3|Uncle Bob's Organic Dried Pears
3|Northwoods Cranberry Sauce
4|Mishi Kobe Niku
4|Ikura
4|Longlife Tofu
```

5. Create a report that shows all products supplied from the Pacific Ocean region.
select productname from products where supplierid in (select supplierid from suppliers where country in ("Japan", "Australia", "Singapore"));
```
Mishi Kobe Niku
Ikura
Konbu
Tofu
Genen Shouyu
Pavlova
Alice Mutton
Carnarvon Tigers
Singaporean Hokkien Fried Mee
Ipoh Coffee
Gula Malacca
Manjimup Dried Apples
Filo Mix
Perth Pasties
Vegie-spread
Outback Lager
Longlife Tofu
```

6. Create a report that shows all companies by name that sell products in CategoryID 8.
select companyname, supplierid from suppliers where supplierid in (select supplierid from products where categoryid = 8);
```
CompanyName|SupplierID
Tokyo Traders|4
Mayumi's|6
Pavlova, Ltd.|7
Nord-Ost-Fisch Handelsgesellschaft mbH|13
Svensk Sjöföda AB|17
New England Seafood Cannery|19
Lyngbysild|21
Escargots Nouveaux|27
```

7. Create a report in two parts that shows the date of the last sale made by each employee, and the date
of the first sale made by each employee.
select o1.employeeid, o1.orderdate from orders o1 where o1.orderdate = (select max(o2.orderdate) from orders o2 where o2.employeeid = o1.employeeid) order by o1.employeeid;
```
EmployeeID|OrderDate
1|1998-05-06
2|1998-05-05
2|1998-05-05
3|1998-04-30
4|1998-05-06
5|1998-04-22
6|1998-04-23
7|1998-05-06
8|1998-05-06
9|1998-04-29
```

select o1.employeeid, o1.orderdate from orders o1 where o1.orderdate = (select min(o2.orderdate) from orders o2 where o2.employeeid = o1.employeeid) order by o1.employeeid;
```
EmployeeID|OrderDate
1|1996-07-17
2|1996-07-25
3|1996-07-08
4|1996-07-08
5|1996-07-04
6|1996-07-05
7|1996-08-26
8|1996-07-22
9|1996-07-12
```

8. What is the product number of our most expensive product? Create a report that shows the employee
id and order id of every order for that product.
select o.employeeid, o.orderid from orders o where exists (select od.orderid from order_details od where od.productid = 38 and o.orderid = od.orderid);
```
EmployeeID|OrderID
4|10329
1|10351
7|10353
4|10360
5|10372
4|10417
7|10424
3|10479
4|10518
3|10540
2|10541
1|10616
9|10672
4|10783
2|10805
4|10816
3|10817
9|10828
3|10831
2|10865
9|10889
3|10964
1|10981
2|11032
```

9. Create a report showing the date of the last sale for every product, ordered by product id.

10. Create a report that shows all companies by name that sell products in the Seafood category.
select s.supplierid, s.companyname from suppliers s where s.supplierid in (select p.supplierid from products p where p.categoryid in (select c.categoryid from categories c where categoryid = 8));
```
SupplierID|CompanyName
4|Tokyo Traders
6|Mayumi's
7|Pavlova, Ltd.
13|Nord-Ost-Fisch Handelsgesellschaft mbH
17|Svensk Sjöföda AB
19|New England Seafood Cannery
21|Lyngbysild
27|Escargots Nouveaux
```

11. Create a report that lists the ten most expensive products.
select o1.productid, o1.productname, o1.unitprice from products o1 where exists (select max(o2.unitprice) from products o2) order by unitprice desc limit 10;
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

12. Create a report that shows the date of the last order by all employees.
select o1.employeeid, o1.orderdate from orders o1 where o1.orderdate = (select max(o2.orderdate) from orders o2 where o2.employeeid = o1.employeeid) order by o1.employeeid;
```
EmployeeID|OrderDate
1|1998-05-06
2|1998-05-05
2|1998-05-05
3|1998-04-30
4|1998-05-06
5|1998-04-22
6|1998-04-23
7|1998-05-06
8|1998-05-06
9|1998-04-29
```

13. Create a line item report that contains a line for each product in the order with the following columns:
the order id, the product id, the unit price, the quantity sold, the line item price, and the percent of
that line item constitutes of the total amount of the order.
