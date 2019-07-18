// Name: TSQL lab03
// Author: James Smelser
// Date: July 15, 2019

-----------------------------------------------------------
# TSQL Lab 03
-- 1. What is the order number and the date of each order sold by each employee?
select o.orderid, o.orderdate, e.lastname || ', ' || e.firstname as employeename from orders o join employees e on o.employeeid = e.employeeid order by o.orderid;
```
OrderID|OrderDate|employeename
10248|1996-07-04|Buchanan, Steven
10249|1996-07-05|Suyama, Michael
10250|1996-07-08|Peacock, Margaret
10251|1996-07-08|Leverling, Janet
10252|1996-07-09|Peacock, Margaret
10253|1996-07-10|Leverling, Janet
10254|1996-07-11|Buchanan, Steven
10255|1996-07-12|Dodsworth, Anne
10256|1996-07-15|Leverling, Janet
10257|1996-07-16|Peacock, Margaret
10258|1996-07-17|Davolio, Nancy
10259|1996-07-18|Peacock, Margaret
10260|1996-07-19|Peacock, Margaret
10261|1996-07-19|Peacock, Margaret
10262|1996-07-22|Callahan, Laura
10263|1996-07-23|Dodsworth, Anne
10264|1996-07-24|Suyama, Michael
10265|1996-07-25|Fuller, Andrew
10266|1996-07-26|Leverling, Janet
10267|1996-07-29|Peacock, Margaret
10268|1996-07-30|Callahan, Laura
10269|1996-07-31|Buchanan, Steven
10270|1996-08-01|Davolio, Nancy
10271|1996-08-01|Suyama, Michael
10272|1996-08-02|Suyama, Michael
10273|1996-08-05|Leverling, Janet
10274|1996-08-06|Suyama, Michael
10275|1996-08-07|Davolio, Nancy
10276|1996-08-08|Callahan, Laura
10277|1996-08-09|Fuller, Andrew
10278|1996-08-12|Callahan, Laura
10279|1996-08-13|Callahan, Laura
10280|1996-08-14|Fuller, Andrew
10281|1996-08-14|Peacock, Margaret
10282|1996-08-15|Peacock, Margaret
10283|1996-08-16|Leverling, Janet
10284|1996-08-19|Peacock, Margaret
10285|1996-08-20|Davolio, Nancy
10286|1996-08-21|Callahan, Laura
10287|1996-08-22|Callahan, Laura
10288|1996-08-23|Peacock, Margaret
10289|1996-08-26|King, Robert
10290|1996-08-27|Callahan, Laura
10291|1996-08-27|Suyama, Michael
10292|1996-08-28|Davolio, Nancy
10293|1996-08-29|Davolio, Nancy
10294|1996-08-30|Peacock, Margaret
10295|1996-09-02|Fuller, Andrew
10296|1996-09-03|Suyama, Michael
10297|1996-09-04|Buchanan, Steven
10298|1996-09-05|Suyama, Michael
10299|1996-09-06|Peacock, Margaret
10300|1996-09-09|Fuller, Andrew
10301|1996-09-09|Callahan, Laura
10302|1996-09-10|Peacock, Margaret
10303|1996-09-11|King, Robert
10304|1996-09-12|Davolio, Nancy
10305|1996-09-13|Callahan, Laura
10306|1996-09-16|Davolio, Nancy
10307|1996-09-17|Fuller, Andrew
10308|1996-09-18|King, Robert
10309|1996-09-19|Leverling, Janet
10310|1996-09-20|Callahan, Laura
10311|1996-09-20|Davolio, Nancy
10312|1996-09-23|Fuller, Andrew
10313|1996-09-24|Fuller, Andrew
10314|1996-09-25|Davolio, Nancy
10315|1996-09-26|Peacock, Margaret
10316|1996-09-27|Davolio, Nancy
10317|1996-09-30|Suyama, Michael
10318|1996-10-01|Callahan, Laura
10319|1996-10-02|King, Robert
10320|1996-10-03|Buchanan, Steven
10321|1996-10-03|Leverling, Janet
10322|1996-10-04|King, Robert
10323|1996-10-07|Peacock, Margaret
10324|1996-10-08|Dodsworth, Anne
10325|1996-10-09|Davolio, Nancy
10326|1996-10-10|Peacock, Margaret
10327|1996-10-11|Fuller, Andrew
10328|1996-10-14|Peacock, Margaret
10329|1996-10-15|Peacock, Margaret
10330|1996-10-16|Leverling, Janet
10331|1996-10-16|Dodsworth, Anne
10332|1996-10-17|Leverling, Janet
10333|1996-10-18|Buchanan, Steven
10334|1996-10-21|Callahan, Laura
10335|1996-10-22|King, Robert
10336|1996-10-23|King, Robert
10337|1996-10-24|Peacock, Margaret
10338|1996-10-25|Peacock, Margaret
10339|1996-10-28|Fuller, Andrew
10340|1996-10-29|Davolio, Nancy
10341|1996-10-29|King, Robert
10342|1996-10-30|Peacock, Margaret
10343|1996-10-31|Peacock, Margaret
10344|1996-11-01|Peacock, Margaret
10345|1996-11-04|Fuller, Andrew
10346|1996-11-05|Leverling, Janet
10347|1996-11-06|Peacock, Margaret
10348|1996-11-07|Peacock, Margaret
10349|1996-11-08|King, Robert
10350|1996-11-11|Suyama, Michael
10351|1996-11-11|Davolio, Nancy
10352|1996-11-12|Leverling, Janet
10353|1996-11-13|King, Robert
10354|1996-11-14|Callahan, Laura
10355|1996-11-15|Suyama, Michael
10356|1996-11-18|Suyama, Michael
10357|1996-11-19|Davolio, Nancy
10358|1996-11-20|Buchanan, Steven
10359|1996-11-21|Buchanan, Steven
10360|1996-11-22|Peacock, Margaret
10361|1996-11-22|Davolio, Nancy
10362|1996-11-25|Leverling, Janet
10363|1996-11-26|Peacock, Margaret
10364|1996-11-26|Davolio, Nancy
10365|1996-11-27|Leverling, Janet
10366|1996-11-28|Callahan, Laura
10367|1996-11-28|King, Robert
10368|1996-11-29|Fuller, Andrew
10369|1996-12-02|Callahan, Laura
10370|1996-12-03|Suyama, Michael
10371|1996-12-03|Davolio, Nancy
10372|1996-12-04|Buchanan, Steven
10373|1996-12-05|Peacock, Margaret
10374|1996-12-05|Davolio, Nancy
10375|1996-12-06|Leverling, Janet
10376|1996-12-09|Davolio, Nancy
10377|1996-12-09|Davolio, Nancy
10378|1996-12-10|Buchanan, Steven
10379|1996-12-11|Fuller, Andrew
10380|1996-12-12|Callahan, Laura
10381|1996-12-12|Leverling, Janet
10382|1996-12-13|Peacock, Margaret
10383|1996-12-16|Callahan, Laura
10384|1996-12-16|Leverling, Janet
10385|1996-12-17|Davolio, Nancy
10386|1996-12-18|Dodsworth, Anne
10387|1996-12-18|Davolio, Nancy
10388|1996-12-19|Fuller, Andrew
10389|1996-12-20|Peacock, Margaret
10390|1996-12-23|Suyama, Michael
10391|1996-12-23|Leverling, Janet
10392|1996-12-24|Fuller, Andrew
10393|1996-12-25|Davolio, Nancy
10394|1996-12-25|Davolio, Nancy
10395|1996-12-26|Suyama, Michael
10396|1996-12-27|Davolio, Nancy
10397|1996-12-27|Buchanan, Steven
10398|1996-12-30|Fuller, Andrew
10399|1996-12-31|Callahan, Laura
10400|1997-01-01|Davolio, Nancy
10401|1997-01-01|Davolio, Nancy
10402|1997-01-02|Callahan, Laura
10403|1997-01-03|Peacock, Margaret
10404|1997-01-03|Fuller, Andrew
10405|1997-01-06|Davolio, Nancy
10406|1997-01-07|King, Robert
10407|1997-01-07|Fuller, Andrew
10408|1997-01-08|Callahan, Laura
10409|1997-01-09|Leverling, Janet
10410|1997-01-10|Leverling, Janet
10411|1997-01-10|Dodsworth, Anne
10412|1997-01-13|Callahan, Laura
10413|1997-01-14|Leverling, Janet
10414|1997-01-14|Fuller, Andrew
10415|1997-01-15|Leverling, Janet
10416|1997-01-16|Callahan, Laura
10417|1997-01-16|Peacock, Margaret
10418|1997-01-17|Peacock, Margaret
10419|1997-01-20|Peacock, Margaret
10420|1997-01-21|Leverling, Janet
10421|1997-01-21|Callahan, Laura
10422|1997-01-22|Fuller, Andrew
10423|1997-01-23|Suyama, Michael
10424|1997-01-23|King, Robert
10425|1997-01-24|Suyama, Michael
10426|1997-01-27|Peacock, Margaret
10427|1997-01-27|Peacock, Margaret
10428|1997-01-28|King, Robert
10429|1997-01-29|Leverling, Janet
10430|1997-01-30|Peacock, Margaret
10431|1997-01-30|Peacock, Margaret
10432|1997-01-31|Leverling, Janet
10433|1997-02-03|Leverling, Janet
10434|1997-02-03|Leverling, Janet
10435|1997-02-04|Callahan, Laura
10436|1997-02-05|Leverling, Janet
10437|1997-02-05|Callahan, Laura
10438|1997-02-06|Leverling, Janet
10439|1997-02-07|Suyama, Michael
10440|1997-02-10|Peacock, Margaret
10441|1997-02-10|Leverling, Janet
10442|1997-02-11|Leverling, Janet
10443|1997-02-12|Callahan, Laura
10444|1997-02-12|Leverling, Janet
10445|1997-02-13|Leverling, Janet
10446|1997-02-14|Suyama, Michael
10447|1997-02-14|Peacock, Margaret
10448|1997-02-17|Peacock, Margaret
10449|1997-02-18|Leverling, Janet
10450|1997-02-19|Callahan, Laura
10451|1997-02-19|Peacock, Margaret
10452|1997-02-20|Callahan, Laura
10453|1997-02-21|Davolio, Nancy
10454|1997-02-21|Peacock, Margaret
10455|1997-02-24|Callahan, Laura
10456|1997-02-25|Callahan, Laura
10457|1997-02-25|Fuller, Andrew
10458|1997-02-26|King, Robert
10459|1997-02-27|Peacock, Margaret
10460|1997-02-28|Callahan, Laura
10461|1997-02-28|Davolio, Nancy
10462|1997-03-03|Fuller, Andrew
10463|1997-03-04|Buchanan, Steven
10464|1997-03-04|Peacock, Margaret
10465|1997-03-05|Davolio, Nancy
10466|1997-03-06|Peacock, Margaret
10467|1997-03-06|Callahan, Laura
10468|1997-03-07|Leverling, Janet
10469|1997-03-10|Davolio, Nancy
10470|1997-03-11|Peacock, Margaret
10471|1997-03-11|Fuller, Andrew
10472|1997-03-12|Callahan, Laura
10473|1997-03-13|Davolio, Nancy
10474|1997-03-13|Buchanan, Steven
10475|1997-03-14|Dodsworth, Anne
10476|1997-03-17|Callahan, Laura
10477|1997-03-17|Buchanan, Steven
10478|1997-03-18|Fuller, Andrew
10479|1997-03-19|Leverling, Janet
10480|1997-03-20|Suyama, Michael
10481|1997-03-20|Callahan, Laura
10482|1997-03-21|Davolio, Nancy
10483|1997-03-24|King, Robert
10484|1997-03-24|Leverling, Janet
10485|1997-03-25|Peacock, Margaret
10486|1997-03-26|Davolio, Nancy
10487|1997-03-26|Fuller, Andrew
10488|1997-03-27|Callahan, Laura
10489|1997-03-28|Suyama, Michael
10490|1997-03-31|King, Robert
10491|1997-03-31|Callahan, Laura
10492|1997-04-01|Leverling, Janet
10493|1997-04-02|Peacock, Margaret
10494|1997-04-02|Peacock, Margaret
10495|1997-04-03|Leverling, Janet
10496|1997-04-04|King, Robert
10497|1997-04-04|King, Robert
10498|1997-04-07|Callahan, Laura
10499|1997-04-08|Peacock, Margaret
10500|1997-04-09|Suyama, Michael
10501|1997-04-09|Dodsworth, Anne
10502|1997-04-10|Fuller, Andrew
10503|1997-04-11|Suyama, Michael
10504|1997-04-11|Peacock, Margaret
10505|1997-04-14|Leverling, Janet
10506|1997-04-15|Dodsworth, Anne
10507|1997-04-15|King, Robert
10508|1997-04-16|Davolio, Nancy
10509|1997-04-17|Peacock, Margaret
10510|1997-04-18|Suyama, Michael
10511|1997-04-18|Peacock, Margaret
10512|1997-04-21|King, Robert
10513|1997-04-22|King, Robert
10514|1997-04-22|Leverling, Janet
10515|1997-04-23|Fuller, Andrew
10516|1997-04-24|Fuller, Andrew
10517|1997-04-24|Leverling, Janet
10518|1997-04-25|Peacock, Margaret
10519|1997-04-28|Suyama, Michael
10520|1997-04-29|King, Robert
10521|1997-04-29|Callahan, Laura
10522|1997-04-30|Peacock, Margaret
10523|1997-05-01|King, Robert
10524|1997-05-01|Davolio, Nancy
10525|1997-05-02|Davolio, Nancy
10526|1997-05-05|Peacock, Margaret
10527|1997-05-05|King, Robert
10528|1997-05-06|Suyama, Michael
10529|1997-05-07|Buchanan, Steven
10530|1997-05-08|Leverling, Janet
10531|1997-05-08|King, Robert
10532|1997-05-09|King, Robert
10533|1997-05-12|Callahan, Laura
10534|1997-05-12|Callahan, Laura
10535|1997-05-13|Peacock, Margaret
10536|1997-05-14|Leverling, Janet
10537|1997-05-14|Davolio, Nancy
10538|1997-05-15|Dodsworth, Anne
10539|1997-05-16|Suyama, Michael
10540|1997-05-19|Leverling, Janet
10541|1997-05-19|Fuller, Andrew
10542|1997-05-20|Davolio, Nancy
10543|1997-05-21|Callahan, Laura
10544|1997-05-21|Peacock, Margaret
10545|1997-05-22|Callahan, Laura
10546|1997-05-23|Davolio, Nancy
10547|1997-05-23|Leverling, Janet
10548|1997-05-26|Leverling, Janet
10549|1997-05-27|Buchanan, Steven
10550|1997-05-28|King, Robert
10551|1997-05-28|Peacock, Margaret
10552|1997-05-29|Fuller, Andrew
10553|1997-05-30|Fuller, Andrew
10554|1997-05-30|Peacock, Margaret
10555|1997-06-02|Suyama, Michael
10556|1997-06-03|Fuller, Andrew
10557|1997-06-03|Dodsworth, Anne
10558|1997-06-04|Davolio, Nancy
10559|1997-06-05|Suyama, Michael
10560|1997-06-06|Callahan, Laura
10561|1997-06-06|Fuller, Andrew
10562|1997-06-09|Davolio, Nancy
10563|1997-06-10|Fuller, Andrew
10564|1997-06-10|Peacock, Margaret
10565|1997-06-11|Callahan, Laura
10566|1997-06-12|Dodsworth, Anne
10567|1997-06-12|Davolio, Nancy
10568|1997-06-13|Leverling, Janet
10569|1997-06-16|Buchanan, Steven
10570|1997-06-17|Leverling, Janet
10571|1997-06-17|Callahan, Laura
10572|1997-06-18|Leverling, Janet
10573|1997-06-19|King, Robert
10574|1997-06-19|Peacock, Margaret
10575|1997-06-20|Buchanan, Steven
10576|1997-06-23|Leverling, Janet
10577|1997-06-23|Dodsworth, Anne
10578|1997-06-24|Peacock, Margaret
10579|1997-06-25|Davolio, Nancy
10580|1997-06-26|Peacock, Margaret
10581|1997-06-26|Leverling, Janet
10582|1997-06-27|Leverling, Janet
10583|1997-06-30|Fuller, Andrew
10584|1997-06-30|Peacock, Margaret
10585|1997-07-01|King, Robert
10586|1997-07-02|Dodsworth, Anne
10587|1997-07-02|Davolio, Nancy
10588|1997-07-03|Fuller, Andrew
10589|1997-07-04|Callahan, Laura
10590|1997-07-07|Peacock, Margaret
10591|1997-07-07|Davolio, Nancy
10592|1997-07-08|Leverling, Janet
10593|1997-07-09|King, Robert
10594|1997-07-09|Leverling, Janet
10595|1997-07-10|Fuller, Andrew
10596|1997-07-11|Callahan, Laura
10597|1997-07-11|King, Robert
10598|1997-07-14|Davolio, Nancy
10599|1997-07-15|Suyama, Michael
10600|1997-07-16|Peacock, Margaret
10601|1997-07-16|King, Robert
10602|1997-07-17|Callahan, Laura
10603|1997-07-18|Callahan, Laura
10604|1997-07-18|Davolio, Nancy
10605|1997-07-21|Davolio, Nancy
10606|1997-07-22|Peacock, Margaret
10607|1997-07-22|Buchanan, Steven
10608|1997-07-23|Peacock, Margaret
10609|1997-07-24|King, Robert
10610|1997-07-25|Callahan, Laura
10611|1997-07-25|Suyama, Michael
10612|1997-07-28|Davolio, Nancy
10613|1997-07-29|Peacock, Margaret
10614|1997-07-29|Callahan, Laura
10615|1997-07-30|Fuller, Andrew
10616|1997-07-31|Davolio, Nancy
10617|1997-07-31|Peacock, Margaret
10618|1997-08-01|Davolio, Nancy
10619|1997-08-04|Leverling, Janet
10620|1997-08-05|Fuller, Andrew
10621|1997-08-05|Peacock, Margaret
10622|1997-08-06|Peacock, Margaret
10623|1997-08-07|Callahan, Laura
10624|1997-08-07|Peacock, Margaret
10625|1997-08-08|Leverling, Janet
10626|1997-08-11|Davolio, Nancy
10627|1997-08-11|Callahan, Laura
10628|1997-08-12|Peacock, Margaret
10629|1997-08-12|Peacock, Margaret
10630|1997-08-13|Davolio, Nancy
10631|1997-08-14|Callahan, Laura
10632|1997-08-14|Callahan, Laura
10633|1997-08-15|King, Robert
10634|1997-08-15|Peacock, Margaret
10635|1997-08-18|Callahan, Laura
10636|1997-08-19|Peacock, Margaret
10637|1997-08-19|Suyama, Michael
10638|1997-08-20|Leverling, Janet
10639|1997-08-20|King, Robert
10640|1997-08-21|Peacock, Margaret
10641|1997-08-22|Peacock, Margaret
10642|1997-08-22|King, Robert
10643|1997-08-25|Suyama, Michael
10644|1997-08-25|Leverling, Janet
10645|1997-08-26|Peacock, Margaret
10646|1997-08-27|Dodsworth, Anne
10647|1997-08-27|Peacock, Margaret
10648|1997-08-28|Buchanan, Steven
10649|1997-08-28|Buchanan, Steven
10650|1997-08-29|Buchanan, Steven
10651|1997-09-01|Callahan, Laura
10652|1997-09-01|Peacock, Margaret
10653|1997-09-02|Davolio, Nancy
10654|1997-09-02|Buchanan, Steven
10655|1997-09-03|Davolio, Nancy
10656|1997-09-04|Suyama, Michael
10657|1997-09-04|Fuller, Andrew
10658|1997-09-05|Peacock, Margaret
10659|1997-09-05|King, Robert
10660|1997-09-08|Callahan, Laura
10661|1997-09-09|King, Robert
10662|1997-09-09|Leverling, Janet
10663|1997-09-10|Fuller, Andrew
10664|1997-09-10|Davolio, Nancy
10665|1997-09-11|Davolio, Nancy
10666|1997-09-12|King, Robert
10667|1997-09-12|King, Robert
10668|1997-09-15|Davolio, Nancy
10669|1997-09-15|Fuller, Andrew
10670|1997-09-16|Peacock, Margaret
10671|1997-09-17|Davolio, Nancy
10672|1997-09-17|Dodsworth, Anne
10673|1997-09-18|Fuller, Andrew
10674|1997-09-18|Peacock, Margaret
10675|1997-09-19|Buchanan, Steven
10676|1997-09-22|Fuller, Andrew
10677|1997-09-22|Davolio, Nancy
10678|1997-09-23|King, Robert
10679|1997-09-23|Callahan, Laura
10680|1997-09-24|Davolio, Nancy
10681|1997-09-25|Leverling, Janet
10682|1997-09-25|Leverling, Janet
10683|1997-09-26|Fuller, Andrew
10684|1997-09-26|Leverling, Janet
10685|1997-09-29|Peacock, Margaret
10686|1997-09-30|Fuller, Andrew
10687|1997-09-30|Dodsworth, Anne
10688|1997-10-01|Peacock, Margaret
10689|1997-10-01|Davolio, Nancy
10690|1997-10-02|Davolio, Nancy
10691|1997-10-03|Fuller, Andrew
10692|1997-10-03|Peacock, Margaret
10693|1997-10-06|Leverling, Janet
10694|1997-10-06|Callahan, Laura
10695|1997-10-07|King, Robert
10696|1997-10-08|Callahan, Laura
10697|1997-10-08|Leverling, Janet
10698|1997-10-09|Peacock, Margaret
10699|1997-10-09|Leverling, Janet
10700|1997-10-10|Leverling, Janet
10701|1997-10-13|Suyama, Michael
10702|1997-10-13|Peacock, Margaret
10703|1997-10-14|Suyama, Michael
10704|1997-10-14|Suyama, Michael
10705|1997-10-15|Dodsworth, Anne
10706|1997-10-16|Callahan, Laura
10707|1997-10-16|Peacock, Margaret
10708|1997-10-17|Suyama, Michael
10709|1997-10-17|Davolio, Nancy
10710|1997-10-20|Davolio, Nancy
10711|1997-10-21|Buchanan, Steven
10712|1997-10-21|Leverling, Janet
10713|1997-10-22|Davolio, Nancy
10714|1997-10-22|Buchanan, Steven
10715|1997-10-23|Leverling, Janet
10716|1997-10-24|Peacock, Margaret
10717|1997-10-24|Davolio, Nancy
10718|1997-10-27|Davolio, Nancy
10719|1997-10-27|Callahan, Laura
10720|1997-10-28|Callahan, Laura
10721|1997-10-29|Buchanan, Steven
10722|1997-10-29|Callahan, Laura
10723|1997-10-30|Leverling, Janet
10724|1997-10-30|Callahan, Laura
10725|1997-10-31|Peacock, Margaret
10726|1997-11-03|Peacock, Margaret
10727|1997-11-03|Fuller, Andrew
10728|1997-11-04|Peacock, Margaret
10729|1997-11-04|Callahan, Laura
10730|1997-11-05|Buchanan, Steven
10731|1997-11-06|King, Robert
10732|1997-11-06|Leverling, Janet
10733|1997-11-07|Davolio, Nancy
10734|1997-11-07|Fuller, Andrew
10735|1997-11-10|Suyama, Michael
10736|1997-11-11|Dodsworth, Anne
10737|1997-11-11|Fuller, Andrew
10738|1997-11-12|Fuller, Andrew
10739|1997-11-12|Leverling, Janet
10740|1997-11-13|Peacock, Margaret
10741|1997-11-14|Peacock, Margaret
10742|1997-11-14|Leverling, Janet
10743|1997-11-17|Davolio, Nancy
10744|1997-11-17|Suyama, Michael
10745|1997-11-18|Dodsworth, Anne
10746|1997-11-19|Davolio, Nancy
10747|1997-11-19|Suyama, Michael
10748|1997-11-20|Leverling, Janet
10749|1997-11-20|Peacock, Margaret
10750|1997-11-21|Dodsworth, Anne
10751|1997-11-24|Leverling, Janet
10752|1997-11-24|Fuller, Andrew
10753|1997-11-25|Leverling, Janet
10754|1997-11-25|Suyama, Michael
10755|1997-11-26|Peacock, Margaret
10756|1997-11-27|Callahan, Laura
10757|1997-11-27|Suyama, Michael
10758|1997-11-28|Leverling, Janet
10759|1997-11-28|Leverling, Janet
10760|1997-12-01|Peacock, Margaret
10761|1997-12-02|Buchanan, Steven
10762|1997-12-02|Leverling, Janet
10763|1997-12-03|Leverling, Janet
10764|1997-12-03|Suyama, Michael
10765|1997-12-04|Leverling, Janet
10766|1997-12-05|Peacock, Margaret
10767|1997-12-05|Peacock, Margaret
10768|1997-12-08|Leverling, Janet
10769|1997-12-08|Leverling, Janet
10770|1997-12-09|Callahan, Laura
10771|1997-12-10|Dodsworth, Anne
10772|1997-12-10|Leverling, Janet
10773|1997-12-11|Davolio, Nancy
10774|1997-12-11|Peacock, Margaret
10775|1997-12-12|King, Robert
10776|1997-12-15|Davolio, Nancy
10777|1997-12-15|King, Robert
10778|1997-12-16|Leverling, Janet
10779|1997-12-16|Leverling, Janet
10780|1997-12-16|Fuller, Andrew
10781|1997-12-17|Fuller, Andrew
10782|1997-12-17|Dodsworth, Anne
10783|1997-12-18|Peacock, Margaret
10784|1997-12-18|Peacock, Margaret
10785|1997-12-18|Davolio, Nancy
10786|1997-12-19|Callahan, Laura
10787|1997-12-19|Fuller, Andrew
10788|1997-12-22|Davolio, Nancy
10789|1997-12-22|Davolio, Nancy
10790|1997-12-22|Suyama, Michael
10791|1997-12-23|Suyama, Michael
10792|1997-12-23|Davolio, Nancy
10793|1997-12-24|Leverling, Janet
10794|1997-12-24|Suyama, Michael
10795|1997-12-24|Callahan, Laura
10796|1997-12-25|Leverling, Janet
10797|1997-12-25|King, Robert
10798|1997-12-26|Fuller, Andrew
10799|1997-12-26|Dodsworth, Anne
10800|1997-12-26|Davolio, Nancy
10801|1997-12-29|Peacock, Margaret
10802|1997-12-29|Peacock, Margaret
10803|1997-12-30|Peacock, Margaret
10804|1997-12-30|Suyama, Michael
10805|1997-12-30|Fuller, Andrew
10806|1997-12-31|Leverling, Janet
10807|1997-12-31|Peacock, Margaret
10808|1998-01-01|Fuller, Andrew
10809|1998-01-01|King, Robert
10810|1998-01-01|Fuller, Andrew
10811|1998-01-02|Callahan, Laura
10812|1998-01-02|Buchanan, Steven
10813|1998-01-05|Davolio, Nancy
10814|1998-01-05|Leverling, Janet
10815|1998-01-05|Fuller, Andrew
10816|1998-01-06|Peacock, Margaret
10817|1998-01-06|Leverling, Janet
10818|1998-01-07|King, Robert
10819|1998-01-07|Fuller, Andrew
10820|1998-01-07|Leverling, Janet
10821|1998-01-08|Davolio, Nancy
10822|1998-01-08|Suyama, Michael
10823|1998-01-09|Buchanan, Steven
10824|1998-01-09|Callahan, Laura
10825|1998-01-09|Davolio, Nancy
10826|1998-01-12|Suyama, Michael
10827|1998-01-12|Davolio, Nancy
10828|1998-01-13|Dodsworth, Anne
10829|1998-01-13|Dodsworth, Anne
10830|1998-01-13|Peacock, Margaret
10831|1998-01-14|Leverling, Janet
10832|1998-01-14|Fuller, Andrew
10833|1998-01-15|Suyama, Michael
10834|1998-01-15|Davolio, Nancy
10835|1998-01-15|Davolio, Nancy
10836|1998-01-16|King, Robert
10837|1998-01-16|Dodsworth, Anne
10838|1998-01-19|Leverling, Janet
10839|1998-01-19|Leverling, Janet
10840|1998-01-19|Peacock, Margaret
10841|1998-01-20|Buchanan, Steven
10842|1998-01-20|Davolio, Nancy
10843|1998-01-21|Peacock, Margaret
10844|1998-01-21|Callahan, Laura
10845|1998-01-21|Callahan, Laura
10846|1998-01-22|Fuller, Andrew
10847|1998-01-22|Peacock, Margaret
10848|1998-01-23|King, Robert
10849|1998-01-23|Dodsworth, Anne
10850|1998-01-23|Davolio, Nancy
10851|1998-01-26|Buchanan, Steven
10852|1998-01-26|Callahan, Laura
10853|1998-01-27|Dodsworth, Anne
10854|1998-01-27|Leverling, Janet
10855|1998-01-27|Leverling, Janet
10856|1998-01-28|Leverling, Janet
10857|1998-01-28|Callahan, Laura
10858|1998-01-29|Fuller, Andrew
10859|1998-01-29|Davolio, Nancy
10860|1998-01-29|Leverling, Janet
10861|1998-01-30|Peacock, Margaret
10862|1998-01-30|Callahan, Laura
10863|1998-02-02|Peacock, Margaret
10864|1998-02-02|Peacock, Margaret
10865|1998-02-02|Fuller, Andrew
10866|1998-02-03|Buchanan, Steven
10867|1998-02-03|Suyama, Michael
10868|1998-02-04|King, Robert
10869|1998-02-04|Buchanan, Steven
10870|1998-02-04|Buchanan, Steven
10871|1998-02-05|Dodsworth, Anne
10872|1998-02-05|Buchanan, Steven
10873|1998-02-06|Peacock, Margaret
10874|1998-02-06|Buchanan, Steven
10875|1998-02-06|Peacock, Margaret
10876|1998-02-09|King, Robert
10877|1998-02-09|Davolio, Nancy
10878|1998-02-10|Peacock, Margaret
10879|1998-02-10|Leverling, Janet
10880|1998-02-10|King, Robert
10881|1998-02-11|Peacock, Margaret
10882|1998-02-11|Peacock, Margaret
10883|1998-02-12|Callahan, Laura
10884|1998-02-12|Peacock, Margaret
10885|1998-02-12|Suyama, Michael
10886|1998-02-13|Davolio, Nancy
10887|1998-02-13|Callahan, Laura
10888|1998-02-16|Davolio, Nancy
10889|1998-02-16|Dodsworth, Anne
10890|1998-02-16|King, Robert
10891|1998-02-17|King, Robert
10892|1998-02-17|Peacock, Margaret
10893|1998-02-18|Dodsworth, Anne
10894|1998-02-18|Davolio, Nancy
10895|1998-02-18|Leverling, Janet
10896|1998-02-19|King, Robert
10897|1998-02-19|Leverling, Janet
10898|1998-02-20|Peacock, Margaret
10899|1998-02-20|Buchanan, Steven
10900|1998-02-20|Davolio, Nancy
10901|1998-02-23|Peacock, Margaret
10902|1998-02-23|Davolio, Nancy
10903|1998-02-24|Leverling, Janet
10904|1998-02-24|Leverling, Janet
10905|1998-02-24|Dodsworth, Anne
10906|1998-02-25|Peacock, Margaret
10907|1998-02-25|Suyama, Michael
10908|1998-02-26|Peacock, Margaret
10909|1998-02-26|Davolio, Nancy
10910|1998-02-26|Davolio, Nancy
10911|1998-02-26|Leverling, Janet
10912|1998-02-26|Fuller, Andrew
10913|1998-02-26|Peacock, Margaret
10914|1998-02-27|Suyama, Michael
10915|1998-02-27|Fuller, Andrew
10916|1998-02-27|Davolio, Nancy
10917|1998-03-02|Peacock, Margaret
10918|1998-03-02|Leverling, Janet
10919|1998-03-02|Fuller, Andrew
10920|1998-03-03|Peacock, Margaret
10921|1998-03-03|Davolio, Nancy
10922|1998-03-03|Buchanan, Steven
10923|1998-03-03|King, Robert
10924|1998-03-04|Leverling, Janet
10925|1998-03-04|Leverling, Janet
10926|1998-03-04|Peacock, Margaret
10927|1998-03-05|Peacock, Margaret
10928|1998-03-05|Davolio, Nancy
10929|1998-03-05|Suyama, Michael
10930|1998-03-06|Peacock, Margaret
10931|1998-03-06|Peacock, Margaret
10932|1998-03-06|Callahan, Laura
10933|1998-03-06|Suyama, Michael
10934|1998-03-09|Leverling, Janet
10935|1998-03-09|Peacock, Margaret
10936|1998-03-09|Leverling, Janet
10937|1998-03-10|King, Robert
10938|1998-03-10|Leverling, Janet
10939|1998-03-10|Fuller, Andrew
10940|1998-03-11|Callahan, Laura
10941|1998-03-11|King, Robert
10942|1998-03-11|Dodsworth, Anne
10943|1998-03-11|Peacock, Margaret
10944|1998-03-12|Suyama, Michael
10945|1998-03-12|Peacock, Margaret
10946|1998-03-12|Davolio, Nancy
10947|1998-03-13|Leverling, Janet
10948|1998-03-13|Leverling, Janet
10949|1998-03-13|Fuller, Andrew
10950|1998-03-16|Davolio, Nancy
10951|1998-03-16|Dodsworth, Anne
10952|1998-03-16|Davolio, Nancy
10953|1998-03-16|Dodsworth, Anne
10954|1998-03-17|Buchanan, Steven
10955|1998-03-17|Callahan, Laura
10956|1998-03-17|Suyama, Michael
10957|1998-03-18|Callahan, Laura
10958|1998-03-18|King, Robert
10959|1998-03-18|Suyama, Michael
10960|1998-03-19|Leverling, Janet
10961|1998-03-19|Callahan, Laura
10962|1998-03-19|Callahan, Laura
10963|1998-03-19|Dodsworth, Anne
10964|1998-03-20|Leverling, Janet
10965|1998-03-20|Suyama, Michael
10966|1998-03-20|Peacock, Margaret
10967|1998-03-23|Fuller, Andrew
10968|1998-03-23|Davolio, Nancy
10969|1998-03-23|Davolio, Nancy
10970|1998-03-24|Dodsworth, Anne
10971|1998-03-24|Fuller, Andrew
10972|1998-03-24|Peacock, Margaret
10973|1998-03-24|Suyama, Michael
10974|1998-03-25|Leverling, Janet
10975|1998-03-25|Davolio, Nancy
10976|1998-03-25|Davolio, Nancy
10977|1998-03-26|Callahan, Laura
10978|1998-03-26|Dodsworth, Anne
10979|1998-03-26|Callahan, Laura
10980|1998-03-27|Peacock, Margaret
10981|1998-03-27|Davolio, Nancy
10982|1998-03-27|Fuller, Andrew
10983|1998-03-27|Fuller, Andrew
10984|1998-03-30|Davolio, Nancy
10985|1998-03-30|Fuller, Andrew
10986|1998-03-30|Callahan, Laura
10987|1998-03-31|Callahan, Laura
10988|1998-03-31|Leverling, Janet
10989|1998-03-31|Fuller, Andrew
10990|1998-04-01|Fuller, Andrew
10991|1998-04-01|Davolio, Nancy
10992|1998-04-01|Davolio, Nancy
10993|1998-04-01|King, Robert
10994|1998-04-02|Fuller, Andrew
10995|1998-04-02|Davolio, Nancy
10996|1998-04-02|Peacock, Margaret
10997|1998-04-03|Callahan, Laura
10998|1998-04-03|Callahan, Laura
10999|1998-04-03|Suyama, Michael
11000|1998-04-06|Fuller, Andrew
11001|1998-04-06|Fuller, Andrew
11002|1998-04-06|Peacock, Margaret
11003|1998-04-06|Leverling, Janet
11004|1998-04-07|Leverling, Janet
11005|1998-04-07|Fuller, Andrew
11006|1998-04-07|Leverling, Janet
11007|1998-04-08|Callahan, Laura
11008|1998-04-08|King, Robert
11009|1998-04-08|Fuller, Andrew
11010|1998-04-09|Fuller, Andrew
11011|1998-04-09|Leverling, Janet
11012|1998-04-09|Davolio, Nancy
11013|1998-04-09|Fuller, Andrew
11014|1998-04-10|Fuller, Andrew
11015|1998-04-10|Fuller, Andrew
11016|1998-04-10|Dodsworth, Anne
11017|1998-04-13|Dodsworth, Anne
11018|1998-04-13|Peacock, Margaret
11019|1998-04-13|Suyama, Michael
11020|1998-04-14|Fuller, Andrew
11021|1998-04-14|Leverling, Janet
11022|1998-04-14|Dodsworth, Anne
11023|1998-04-14|Davolio, Nancy
11024|1998-04-15|Peacock, Margaret
11025|1998-04-15|Suyama, Michael
11026|1998-04-15|Peacock, Margaret
11027|1998-04-16|Davolio, Nancy
11028|1998-04-16|Fuller, Andrew
11029|1998-04-16|Peacock, Margaret
11030|1998-04-17|King, Robert
11031|1998-04-17|Suyama, Michael
11032|1998-04-17|Fuller, Andrew
11033|1998-04-17|King, Robert
11034|1998-04-20|Callahan, Laura
11035|1998-04-20|Fuller, Andrew
11036|1998-04-20|Callahan, Laura
11037|1998-04-21|King, Robert
11038|1998-04-21|Davolio, Nancy
11039|1998-04-21|Davolio, Nancy
11040|1998-04-22|Peacock, Margaret
11041|1998-04-22|Leverling, Janet
11042|1998-04-22|Fuller, Andrew
11043|1998-04-22|Buchanan, Steven
11044|1998-04-23|Peacock, Margaret
11045|1998-04-23|Suyama, Michael
11046|1998-04-23|Callahan, Laura
11047|1998-04-24|King, Robert
11048|1998-04-24|King, Robert
11049|1998-04-24|Leverling, Janet
11050|1998-04-27|Callahan, Laura
11051|1998-04-27|King, Robert
11052|1998-04-27|Leverling, Janet
11053|1998-04-27|Fuller, Andrew
11054|1998-04-28|Callahan, Laura
11055|1998-04-28|King, Robert
11056|1998-04-28|Callahan, Laura
11057|1998-04-29|Leverling, Janet
11058|1998-04-29|Dodsworth, Anne
11059|1998-04-29|Fuller, Andrew
11060|1998-04-30|Fuller, Andrew
11061|1998-04-30|Peacock, Margaret
11062|1998-04-30|Peacock, Margaret
11063|1998-04-30|Leverling, Janet
11064|1998-05-01|Davolio, Nancy
11065|1998-05-01|Callahan, Laura
11066|1998-05-01|King, Robert
11067|1998-05-04|Davolio, Nancy
11068|1998-05-04|Callahan, Laura
11069|1998-05-04|Davolio, Nancy
11070|1998-05-05|Fuller, Andrew
11071|1998-05-05|Davolio, Nancy
11072|1998-05-05|Peacock, Margaret
11073|1998-05-05|Fuller, Andrew
11074|1998-05-06|King, Robert
11075|1998-05-06|Callahan, Laura
11076|1998-05-06|Peacock, Margaret
11077|1998-05-06|Davolio, Nancy
```

-- 2. List each territory by region.
select r.regionid, r.regiondescription, t.regionid, t.territorydescription from region r join territories t on r.regionid = t.regionid order by r.regionid;
```
RegionID|RegionDescription|RegionID|TerritoryDescription
1|Eastern                                           |1|Westboro
1|Eastern                                           |1|Bedford
1|Eastern                                           |1|Georgetow
1|Eastern                                           |1|Boston
1|Eastern                                           |1|Cambridge
1|Eastern                                           |1|Braintree
1|Eastern                                           |1|Providence
1|Eastern                                           |1|Wilton
1|Eastern                                           |1|Morristown
1|Eastern                                           |1|Edison
1|Eastern                                           |1|NewYork
1|Eastern                                           |1|NewYork
1|Eastern                                           |1|Mellvile
1|Eastern                                           |1|Fairport
1|Eastern                                           |1|Neward
1|Eastern                                           |1|Rockville
1|Eastern                                           |1|Greensboro
1|Eastern                                           |1|Cary
1|Eastern                                           |1|Louisville
2|Western                                           |2|HoffmanEstates
2|Western                                           |2|Chicago
2|Western                                           |2|Denver
2|Western                                           |2|ColoradoSprings
2|Western                                           |2|Phoenix
2|Western                                           |2|Scottsdale
2|Western                                           |2|SantaMonica
2|Western                                           |2|MenloPark
2|Western                                           |2|SanFrancisco
2|Western                                           |2|Campbell
2|Western                                           |2|SantaClara
2|Western                                           |2|SantaCruz
2|Western                                           |2|Bellevue
2|Western                                           |2|Redmond
2|Western                                           |2|Seattle
3|Northern                                          |3|Hollis
3|Northern                                          |3|Portsmouth
3|Northern                                          |3|Philadelphia
3|Northern                                          |3|Beachwood
3|Northern                                          |3|Findlay
3|Northern                                          |3|Southfield
3|Northern                                          |3|Troy
3|Northern                                          |3|BloomfieldHills
3|Northern                                          |3|Racine
3|Northern                                          |3|Roseville
3|Northern                                          |3|Minneapolis
4|Southern|4|Columbia
4|Southern|4|Atlanta
4|Southern|4|Savannah
4|Southern|4|Orlando
4|Southern|4|Tampa
4|Southern|4|Bentonville
4|Southern|4|Dallas
4|Southern|4|Austin
```

-- 3. What is the supplier name for each product alphabetically by supplier?
select s.companyname, p.productname from suppliers s left join products p on s.supplierid = p.supplierid order by s.companyname;
```
CompanyName|ProductName
Aux joyeux ecclésiastiques|Chartreuse verte
Aux joyeux ecclésiastiques|Côte de Blaye
Bigfoot Breweries|Laughing Lumberjack Lager
Bigfoot Breweries|Sasquatch Ale
Bigfoot Breweries|Steeleye Stout
Cooperativa de Quesos 'Las Cabras'|Queso Cabrales
Cooperativa de Quesos 'Las Cabras'|Queso Manchego La Pastora
Escargots Nouveaux|Escargots de Bourgogne
Exotic Liquids|Aniseed Syrup
Exotic Liquids|Chai
Exotic Liquids|Chang
Formaggi Fortini s.r.l.|Gorgonzola Telino
Formaggi Fortini s.r.l.|Mascarpone Fabioli
Formaggi Fortini s.r.l.|Mozzarella di Giovanni
Forêts d'érables|Sirop d'érable
Forêts d'érables|Tarte au sucre
G'day, Mate|Filo Mix
G'day, Mate|Manjimup Dried Apples
G'day, Mate|Perth Pasties
Gai pâturage|Camembert Pierrot
Gai pâturage|Raclette Courdavault
Grandma Kelly's Homestead|Grandma's Boysenberry Spread
Grandma Kelly's Homestead|Northwoods Cranberry Sauce
Grandma Kelly's Homestead|Uncle Bob's Organic Dried Pears
Heli Süßwaren GmbH & Co. KG|Gumbär Gummibärchen
Heli Süßwaren GmbH & Co. KG|NuNuCa Nuß-Nougat-Creme
Heli Süßwaren GmbH & Co. KG|Schoggi Schokolade
Karkki Oy|Lakkalikööri
Karkki Oy|Maxilaku
Karkki Oy|Valkoinen suklaa
Leka Trading|Gula Malacca
Leka Trading|Ipoh Coffee
Leka Trading|Singaporean Hokkien Fried Mee
Lyngbysild|Rogede sild
Lyngbysild|Spegesild
Ma Maison|Pâté chinois
Ma Maison|Tourtière
Mayumi's|Genen Shouyu
Mayumi's|Konbu
Mayumi's|Tofu
New England Seafood Cannery|Boston Crab Meat
New England Seafood Cannery|Jack's New England Clam Chowder
New Orleans Cajun Delights|Chef Anton's Cajun Seasoning
New Orleans Cajun Delights|Chef Anton's Gumbo Mix
New Orleans Cajun Delights|Louisiana Fiery Hot Pepper Sauce
New Orleans Cajun Delights|Louisiana Hot Spiced Okra
Nord-Ost-Fisch Handelsgesellschaft mbH|Nord-Ost Matjeshering
Norske Meierier|Flotemysost
Norske Meierier|Geitost
Norske Meierier|Gudbrandsdalsost
PB Knäckebröd AB|Gustaf's Knäckebröd
PB Knäckebröd AB|Tunnbröd
Pasta Buttini s.r.l.|Gnocchi di nonna Alice
Pasta Buttini s.r.l.|Ravioli Angelo
Pavlova, Ltd.|Alice Mutton
Pavlova, Ltd.|Carnarvon Tigers
Pavlova, Ltd.|Outback Lager
Pavlova, Ltd.|Pavlova
Pavlova, Ltd.|Vegie-spread
Plutzer Lebensmittelgroßmärkte AG|Original Frankfurter grüne Soße
Plutzer Lebensmittelgroßmärkte AG|Rhönbräu Klosterbier
Plutzer Lebensmittelgroßmärkte AG|Rössle Sauerkraut
Plutzer Lebensmittelgroßmärkte AG|Thüringer Rostbratwurst
Plutzer Lebensmittelgroßmärkte AG|Wimmers gute Semmelknödel
Refrescos Americanas LTDA|Guaraná Fantástica
Specialty Biscuits, Ltd.|Scottish Longbreads
Specialty Biscuits, Ltd.|Sir Rodney's Marmalade
Specialty Biscuits, Ltd.|Sir Rodney's Scones
Specialty Biscuits, Ltd.|Teatime Chocolate Biscuits
Svensk Sjöföda AB|Gravad lax
Svensk Sjöföda AB|Inlagd Sill
Svensk Sjöföda AB|Röd Kaviar
Tokyo Traders|Ikura
Tokyo Traders|Longlife Tofu
Tokyo Traders|Mishi Kobe Niku
Zaanse Snoepfabriek|Chocolade
Zaanse Snoepfabriek|Zaanse koeken
 ```

-- 4. For every order on May 5, 1998, how many of each item was ordered, and what was the price of the
-- item?
select o.orderid, o.orderdate, p.productname, od.unitprice, od.quantity from orders o join order_details od on o.orderid = od.orderid join products p on od.productid = p.productid where o.orderdate >= "1998-05-01" and o.orderdate < "1998-05-05";
```
OrderID|OrderDate|ProductName|UnitPrice|Quantity
11064|1998-05-01|Alice Mutton|39.0|77
11064|1998-05-01|Jack's New England Clam Chowder|9.65|12
11064|1998-05-01|Perth Pasties|32.8|25
11064|1998-05-01|Pâté chinois|24.0|4
11064|1998-05-01|Scottish Longbreads|12.5|55
11065|1998-05-01|Nord-Ost Matjeshering|25.89|4
11065|1998-05-01|Tourtière|7.45|20
11066|1998-05-01|Pavlova|17.45|3
11066|1998-05-01|Teatime Chocolate Biscuits|9.2|42
11066|1998-05-01|Sasquatch Ale|14.0|35
11067|1998-05-04|Jack's New England Clam Chowder|9.65|9
11068|1998-05-04|Rössle Sauerkraut|45.6|8
11068|1998-05-04|Ipoh Coffee|46.0|36
11068|1998-05-04|Original Frankfurter grüne Soße|13.0|28
11069|1998-05-04|Chartreuse verte|18.0|20
```

-- 5. For every order on May 5, 1998, how many of each item was ordered giving the name of the item, and
-- what was the price of the item?
select o.orderid, o.orderdate, s.companyname from orders o join customers c on o.customerid = c.customerid join shippers s on o.shipperid = s.shipperid where o.orderdate like "1998-05-%";
```
OrderID|OrderDate|CompanyName
11064|1998-05-01|Speedy Express
11065|1998-05-01|Speedy Express
11066|1998-05-01|United Package
11067|1998-05-04|United Package
11068|1998-05-04|United Package
11069|1998-05-04|United Package
11070|1998-05-05|Speedy Express
11071|1998-05-05|Speedy Express
11072|1998-05-05|United Package
11073|1998-05-05|United Package
11074|1998-05-06|United Package
11075|1998-05-06|United Package
11076|1998-05-06|United Package
11077|1998-05-06|United Package
```

-- 6. For every order in May, 1998, what was the customer's name and the shipper's name?
select o.orderid, o.orderdate, s.companyname from orders o join customers c on o.customerid = c.customerid join shippers s on o.shipperid = s.shipperid where o.orderdate like "1998-05-%";
```
OrderID|OrderDate|CompanyName
11064|1998-05-01|Speedy Express
11065|1998-05-01|Speedy Express
11066|1998-05-01|United Package
11067|1998-05-04|United Package
11068|1998-05-04|United Package
11069|1998-05-04|United Package
11070|1998-05-05|Speedy Express
11071|1998-05-05|Speedy Express
11072|1998-05-05|United Package
11073|1998-05-05|United Package
11074|1998-05-06|United Package
11075|1998-05-06|United Package
11076|1998-05-06|United Package
11077|1998-05-06|United Package
```

-- 7. What is the customer's name and the employee's name for every order shipped to France?
select o.orderid, o.shipcountry, c.companyname, e.firstname || ' ' || e.lastname as employeename from orders o join customers c on o.customerid = c.customerid join employees e on o.employeeid = e.employeeid where o.shipcountry like "france";
```
OrderID|ShipCountry|CompanyName|employeename
10248|France|Vins et alcools Chevalier|Steven Buchanan
10251|France|Victuailles en stock|Janet Leverling
10265|France|Blondesddsl père et fils|Andrew Fuller
10274|France|Vins et alcools Chevalier|Michael Suyama
10295|France|Vins et alcools Chevalier|Andrew Fuller
10297|France|Blondesddsl père et fils|Steven Buchanan
10311|France|Du monde entier|Nancy Davolio
10331|France|Bon app''|Anne Dodsworth
10334|France|Victuailles en stock|Laura Callahan
10340|France|Bon app''|Nancy Davolio
10350|France|La maison d''Asie|Michael Suyama
10358|France|La maison d''Asie|Steven Buchanan
10360|France|Blondesddsl père et fils|Margaret Peacock
10362|France|Bon app''|Janet Leverling
10371|France|La maison d''Asie|Nancy Davolio
10408|France|Folies gourmandes|Laura Callahan
10413|France|La maison d''Asie|Janet Leverling
10425|France|La maison d''Asie|Michael Suyama
10436|France|Blondesddsl père et fils|Janet Leverling
10449|France|Blondesddsl père et fils|Janet Leverling
10450|France|Victuailles en stock|Laura Callahan
10454|France|La maison d''Asie|Margaret Peacock
10459|France|Victuailles en stock|Margaret Peacock
10470|France|Bon app''|Margaret Peacock
10478|France|Victuailles en stock|Andrew Fuller
10480|France|Folies gourmandes|Michael Suyama
10493|France|La maison d''Asie|Margaret Peacock
10500|France|La maison d''Asie|Michael Suyama
10511|France|Bon app''|Margaret Peacock
10525|France|Bon app''|Nancy Davolio
10546|France|Victuailles en stock|Nancy Davolio
10559|France|Blondesddsl père et fils|Michael Suyama
10566|France|Blondesddsl père et fils|Anne Dodsworth
10584|France|Blondesddsl père et fils|Margaret Peacock
10609|France|Du monde entier|Robert King
10610|France|La maison d''Asie|Laura Callahan
10628|France|Blondesddsl père et fils|Margaret Peacock
10631|France|La maison d''Asie|Laura Callahan
10634|France|Folies gourmandes|Margaret Peacock
10663|France|Bon app''|Andrew Fuller
10671|France|France restauration|Nancy Davolio
10679|France|Blondesddsl père et fils|Laura Callahan
10683|France|Du monde entier|Andrew Fuller
10715|France|Bon app''|Janet Leverling
10730|France|Bon app''|Steven Buchanan
10732|France|Bon app''|Janet Leverling
10737|France|Vins et alcools Chevalier|Andrew Fuller
10738|France|Spécialités du monde|Andrew Fuller
10739|France|Vins et alcools Chevalier|Janet Leverling
10755|France|Bon app''|Margaret Peacock
10763|France|Folies gourmandes|Janet Leverling
10787|France|La maison d''Asie|Andrew Fuller
10789|France|Folies gourmandes|Nancy Davolio
10806|France|Victuailles en stock|Janet Leverling
10814|France|Victuailles en stock|Janet Leverling
10826|France|Blondesddsl père et fils|Michael Suyama
10827|France|Bon app''|Nancy Davolio
10832|France|La maison d''Asie|Andrew Fuller
10843|France|Victuailles en stock|Margaret Peacock
10850|France|Victuailles en stock|Nancy Davolio
10858|France|La corne d''abondance|Andrew Fuller
10860|France|France restauration|Janet Leverling
10871|France|Bon app''|Anne Dodsworth
10876|France|Bon app''|Robert King
10890|France|Du monde entier|Robert King
10907|France|Spécialités du monde|Michael Suyama
10923|France|La maison d''Asie|Robert King
10927|France|La corne d''abondance|Margaret Peacock
10932|France|Bon app''|Laura Callahan
10940|France|Bon app''|Laura Callahan
10964|France|Spécialités du monde|Janet Leverling
10971|France|France restauration|Andrew Fuller
10972|France|La corne d''abondance|Margaret Peacock
10973|France|La corne d''abondance|Michael Suyama
11043|France|Spécialités du monde|Steven Buchanan
11051|France|La maison d''Asie|Robert King
11076|France|Bon app''|Margaret Peacock
```

-- 8. List the products by name that were shipped to Germany.
select p.productid, p.productname, o.shipcountry from products p join order_details od on p.productid = od.productid join orders o on o.orderid = od.orderid where shipcountry like "germany" group by p.productid;
```
ProductID|ProductName|ShipCountry
1|Chai|Germany
2|Chang|Germany
3|Aniseed Syrup|Germany
4|Chef Anton's Cajun Seasoning|Germany
6|Grandma's Boysenberry Spread|Germany
7|Uncle Bob's Organic Dried Pears|Germany
8|Northwoods Cranberry Sauce|Germany
9|Mishi Kobe Niku|Germany
10|Ikura|Germany
11|Queso Cabrales|Germany
12|Queso Manchego La Pastora|Germany
13|Konbu|Germany
14|Tofu|Germany
15|Genen Shouyu|Germany
16|Pavlova|Germany
17|Alice Mutton|Germany
18|Carnarvon Tigers|Germany
19|Teatime Chocolate Biscuits|Germany
20|Sir Rodney's Marmalade|Germany
21|Sir Rodney's Scones|Germany
22|Gustaf's Knäckebröd|Germany
23|Tunnbröd|Germany
24|Guaraná Fantástica|Germany
25|NuNuCa Nuß-Nougat-Creme|Germany
26|Gumbär Gummibärchen|Germany
27|Schoggi Schokolade|Germany
28|Rössle Sauerkraut|Germany
29|Thüringer Rostbratwurst|Germany
30|Nord-Ost Matjeshering|Germany
31|Gorgonzola Telino|Germany
32|Mascarpone Fabioli|Germany
33|Geitost|Germany
34|Sasquatch Ale|Germany
35|Steeleye Stout|Germany
36|Inlagd Sill|Germany
37|Gravad lax|Germany
38|Côte de Blaye|Germany
39|Chartreuse verte|Germany
40|Boston Crab Meat|Germany
41|Jack's New England Clam Chowder|Germany
42|Singaporean Hokkien Fried Mee|Germany
43|Ipoh Coffee|Germany
44|Gula Malacca|Germany
45|Rogede sild|Germany
46|Spegesild|Germany
47|Zaanse koeken|Germany
49|Maxilaku|Germany
51|Manjimup Dried Apples|Germany
52|Filo Mix|Germany
53|Perth Pasties|Germany
54|Tourtière|Germany
55|Pâté chinois|Germany
56|Gnocchi di nonna Alice|Germany
57|Ravioli Angelo|Germany
58|Escargots de Bourgogne|Germany
59|Raclette Courdavault|Germany
60|Camembert Pierrot|Germany
61|Sirop d'érable|Germany
62|Tarte au sucre|Germany
63|Vegie-spread|Germany
64|Wimmers gute Semmelknödel|Germany
65|Louisiana Fiery Hot Pepper Sauce|Germany
67|Laughing Lumberjack Lager|Germany
68|Scottish Longbreads|Germany
69|Gudbrandsdalsost|Germany
70|Outback Lager|Germany
71|Flotemysost|Germany
72|Mozzarella di Giovanni|Germany
73|Röd Kaviar|Germany
74|Longlife Tofu|Germany
75|Rhönbräu Klosterbier|Germany
76|Lakkalikööri|Germany
77|Original Frankfurter grüne Soße|Germany
```
