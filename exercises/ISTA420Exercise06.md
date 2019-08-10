// Name: TSQL Exercise 06
// Author: James Smelser
// Date: August 10, 2019

-----------------------------------------------------
```
CREATE DATABASE SampleDatabase
GO

use SampleDatabase;

DROP TABLE IF EXISTS Products;
CREATE TABLE dbo.Products
(
ProductCode nchar(20) not null,
ProductName nvarchar(60) null,
ProductLine nchar(20) null,
ProductScale nchar(20) null,
ProductVendor nchar(30) null,
ProductDesc nvarchar(max) null,
QtyInStock int null,
BuyPrice float null,
MSRP float null,
CONSTRAINT PK_Products PRIMARY KEY CLUSTERED (ProductCode)
)

BULK INSERT dbo.Products FROM 'C:\Users\smels\OneDrive\Desktop\Products.csv'
WITH
(
FIELDTERMINATOR = ',',
ROWTERMINATOR = '\n'
)

DROP TABLE IF EXISTS Orders;
CREATE TABLE dbo.Orders
(
OrderNumber int not null,
OrderDate date null,
ReqDate date null,
ShipDate date null,
OrderStatus nchar(20) null,
Comments nvarchar(max) null,
CustNumber int not null,
CONSTRAINT PK_Orders PRIMARY KEY CLUSTERED (OrderNumber)
)

BULK INSERT dbo.Orders FROM 'C:\Users\smels\OneDrive\Desktop\Orders.csv'
WITH
(
FIELDTERMINATOR = ',',
ROWTERMINATOR = '\n'
)

DROP TABLE IF EXISTS Order_Details;
CREATE TABLE dbo.Order_Details
(
OrderNumber int not null,
ProductCode nchar(20) not null,
QtyOrdered int null,
PriceEach float null,
OrderLineNumber int null,
)

BULK INSERT dbo.Order_Details FROM 'C:\Users\smels\OneDrive\Desktop\Order_Details.csv'
WITH
(
FIELDTERMINATOR = ',',
ROWTERMINATOR = '\n'
)

DROP TABLE IF EXISTS Customers;
CREATE TABLE dbo.Customers
(
CustNumber int not null,
CustName nvarchar(50) null,
ContactLastName nchar(20) null,
ContactFirstName nchar(20) null,
Phone nvarchar(50) null,
AddressLine1 nvarchar(50) null,
AddressLine2 nvarchar(50) null,
City nchar(50) null,
State nchar(20) null,
PostalCode nvarchar(50) null,
Country nvarchar(50) null,
SalesRepEmpID int null,
CreditLimit float null,
CONSTRAINT PK_Customers PRIMARY KEY CLUSTERED (CustNumber)
)

BULK INSERT dbo.Customers FROM 'C:\Users\smels\OneDrive\Desktop\Customers.csv'
WITH
(
FIELDTERMINATOR = ',',
ROWTERMINATOR = '\n'
)

DROP TABLE IF EXISTS Payments;
CREATE TABLE dbo.Payments
(
CustNumber int not null,
CheckNumber nchar(20) not null,
PmtDue date null,
Amount float null,
CONSTRAINT PK_Payments PRIMARY KEY CLUSTERED (CheckNumber)
)

BULK INSERT dbo.Payments FROM 'C:\Users\smels\OneDrive\Desktop\Payments.csv'
WITH
(
FIELDTERMINATOR = ',',
ROWTERMINATOR = '\n'
)

DROP TABLE IF EXISTS Employees;
CREATE TABLE dbo.Employees
(
EmpNumber int not null,
LastName nchar(20) null,
FirstName nchar(20) null,
Extension nchar(10) null,
Email nvarchar(50) null,
OfficeCode int not null,
ReportsTo int null,
JobTitle nvarchar(30) null,
CONSTRAINT PK_Employees PRIMARY KEY CLUSTERED (EmpNumber)
)

BULK INSERT dbo.Employees FROM 'C:\Users\smels\OneDrive\Desktop\Employees.csv'
WITH
(
FIELDTERMINATOR = ',',
ROWTERMINATOR = '\n'
)

DROP TABLE IF EXISTS Offices;
CREATE TABLE dbo.Offices
(
OfficeCode int not null,
City nchar(30) null,
Phone nchar(20) null,
AddressLine1 nvarchar(50) null,
AddressLine2 nvarchar(50) null,
State nchar(20) not null,
Country nvarchar(50) null,
PostalCode nvarchar(50) null,
Territory nchar(10) null,
CONSTRAINT PK_Offices PRIMARY KEY CLUSTERED (OfficeCode)
)

BULK INSERT dbo.Offices FROM 'C:\Users\smels\OneDrive\Desktop\Offices.csv'
WITH
(
FIELDTERMINATOR = ',',
ROWTERMINATOR = '\n'
)

ALTER TABLE dbo.Orders
ADD CONSTRAINT FK_Orders_Customers
FOREIGN KEY(CustNumber)
REFERENCES Customers(CustNumber)
ON DELETE CASCADE
ON UPDATE CASCADE

ALTER TABLE dbo.Order_Details
ADD CONSTRAINT FK_Order_Details_Orders
FOREIGN KEY(OrderNumber)
REFERENCES Orders(OrderNumber)
ON DELETE CASCADE
ON UPDATE CASCADE

ALTER TABLE dbo.Order_Details
ADD CONSTRAINT FK_Order_Details_Products
FOREIGN KEY(ProductCode)
REFERENCES Products(ProductCode)
ON DELETE CASCADE
ON UPDATE CASCADE

ALTER TABLE dbo.Payments
ADD CONSTRAINT FK_Payments_Customers
FOREIGN KEY(CustNumber)
REFERENCES Customers(CustNumber)
ON DELETE CASCADE
ON UPDATE CASCADE

ALTER TABLE dbo.Employees
ADD CONSTRAINT FK_Employees_Offices
FOREIGN KEY(OfficeCode)
REFERENCES Offices(OfficeCode)
ON DELETE CASCADE
ON UPDATE CASCADE

select * from dbo.Products;
select * from dbo.Orders;
select * from dbo.Order_Details;
select * from dbo.Customers;
select * from dbo.Payments;
select * from dbo.Employees;
select * from dbo.Offices;
```
