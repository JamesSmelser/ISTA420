// Name: TSQL Exercise05
// Author: James Smelser
// Date: July 30, 2019

# TSQL Exercise 05
-------------------------------------------------------------------------------

```
use tsqlv4;

drop table if exists dbo.presidents;
create table dbo.presidents
(ID varchar(100),LastName varchar(100),FirstName varchar(100),MiddleName varchar(100),OrderofPresidency varchar(100),DateofBirth varchar(100),DateofDeath varchar(100),TownorCountyofBirth varchar(100),StateofBirth varchar(100),HomeState varchar(100),PartyAffiliation varchar(100),DateTookOffice varchar(100),
DateLeftOffice varchar(100),AssassinationAttempt varchar(100),Assassinated varchar(100),ReligiousAffiliation varchar(100),ImagePath varchar(100));

bulk insert dbo.presidents from 'C:\Users\smels\OneDrive\Desktop\president.csv'
with
(
fieldterminator = ',',
rowterminator = '\n'
);

delete top(1) from dbo.presidents
output deleted.*;

alter table dbo.presidents drop column ImagePath;

alter table dbo.presidents add Seq int identity Primary Key;

DECLARE @id varchar(100)
UPDATE dbo.presidents
SET @id = DateLeftOffice = '1/20/2017'
WHERE ID = 44;

insert into dbo.presidents output inserted.*
values('45', 'Trump', 'Donald', 'John', '45', '6/14/1946', NULL, 'Queens', 'New York', 'New York', 'Republican', '1/20/2017', NULL, 'false', 'false', 'Christian');

GO
ALTER TABLE dbo.presidents
ALTER COLUMN DateTookOffice DATE
ALTER TABLE dbo.presidents
ALTER COLUMN DateofBirth DATE
ALTER TABLE dbo.presidents
ALTER COLUMN DateofDeath DATE NULL
ALTER TABLE dbo.presidents
ALTER COLUMN DateLeftOffice DATE NULL;

SELECT OrderofPresidency, LastName, FirstName, DATEDIFF(DAY, DateTookOffice, DateLeftOffice) as TimeinOffice from dbo.presidents;

SELECT OrderofPresidency, LastName, FirstName, DATEDIFF(Year, DateofBirth, DateTookOffice) as AgeofPrez from dbo.presidents;

select HomeState, PartyAffiliation, count(*) as Tot
from dbo.presidents
group by HomeState, PartyAffiliation
order by Tot desc;

select PartyAffiliation, ReligiousAffiliation, count(*) as Tot
from dbo.presidents
group by PartyAffiliation, ReligiousAffiliation
order by Tot desc;

Select * from dbo.presidents;
```
