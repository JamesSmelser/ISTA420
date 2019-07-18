// Name: TSQL exercise01
// Author: James Smelser
// Date: July 2, 2019

-----------------------------------
# TSQL Exercise 01
```
drop table if exists guns;

create table guns(
id integer,
year,
make text,
model integer,
rounds fired integer
);

insert into guns values (1, 2012, "SIG", 357, 452);
insert into guns values (2, 2014, "Glock", 19, 846);
insert into guns values (3, 2008, "Ruger", 22, 1003);
insert into guns values (4, 2017, "Winchester", 3030, 255);
insert into guns values (5, 2001, "Remington", 870, 647);
insert into guns values (6, 2019, "Colt", 1911, 754);
insert into guns values (7, 2011, "CZ", 380, 255);
insert into guns values (8, 2007, "HK", 40, 490);
insert into guns values (9, 2010, "FN", 308, 105);
insert into guns values (10, 2002, "Remington", 338, 602);
```
```
select * from guns;
id|year|make|model|rounds
1|2012|SIG|357|452
2|2014|Glock|19|846
3|2008|Ruger|22|1003
4|2017|Winchester|3030|255
5|2001|Remington|870|647
6|2019|Colt|1911|754
7|2011|CZ|380|255
8|2007|HK|40|490
9|2010|FN|308|105
10|2002|Remington|338|602
```
```
select * from guns order by make;
id|year|make|model|rounds
7|2011|CZ|380|255
6|2019|Colt|1911|754
9|2010|FN|308|105
2|2014|Glock|19|846
8|2007|HK|40|490
5|2001|Remington|870|647
10|2002|Remington|338|602
3|2008|Ruger|22|1003
1|2012|SIG|357|452
4|2017|Winchester|3030|255
```
```
select * from guns where make = "Remington";
id|year|make|model|rounds
5|2001|Remington|870|647
10|2002|Remington|338|602
```
```
select * from guns where rounds > 400;
id|year|make|model|rounds
1|2012|SIG|357|452
2|2014|Glock|19|846
3|2008|Ruger|22|1003
5|2001|Remington|870|647
6|2019|Colt|1911|754
8|2007|HK|40|490
10|2002|Remington|338|602
```
