// Name: TSQL Lab01
// Author: James Smelser
// Date: July 1, 2019

--------------------------------
# TSQL Lab 01
```
drop table if exists family;

create table family(
id integer,
name text,
sex integer,
role text,
location text
);

insert into family values (1, "James", 1, "parent", "Columbus");
insert into family values (2, "Christina", 0, "parent", "Columbus");
insert into family values (3, "Alyssa", 0, "child", "Columbus");
insert into family values (4, "Sophia", 0, "child", "Columbus");
insert into family values (5, "Jax", 1, "child", "Columbus");
```
```
select * from family;
id|name|sex|role|location
1|James|1|parent|Columbus
2|Christina|0|parent|Columbus
3|Alyssa|0|child|Columbus
4|Sophia|0|child|Columbus
5|Jax|1|child|Columbus
select * from family where sex = 0;
id|name|sex|role|location
2|Christina|0|parent|Columbus
3|Alyssa|0|child|Columbus
4|Sophia|0|child|Columbus
select * from family where sex = 1;
id|name|sex|role|location
1|James|1|parent|Columbus
5|Jax|1|child|Columbus
```
