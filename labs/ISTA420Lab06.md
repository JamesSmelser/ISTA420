// Name: TSQL lab06
// Author: James Smelser
// Date: July 25, 2019

-------------------------------------------------------
# Chapter 06 In-class Lab Assignment
## ISTA-420, T-SQL Fundamentals
### In-class Lab | Set operators
#### Using the Northwind database
#### Use set operators to execute the following queries. Note that it may be possible to use joins and sets to do the same thing.
1. Create a list of every country where we have either a customer or a supplier.
select country from customers union select country from suppliers;
```
Country
Argentina
Australia
Austria
Belgium
Brazil
Canada
Country
Denmark
Finland
France
Germany
Ireland
Italy
Japan
Mexico
Netherlands
Norway
Poland
Portugal
Singapore
Spain
Sweden
Switzerland
UK
USA
Venezuela
```

2. Create a list of every city and country where we have either a customer or a supplier.
select city, country from customers union select city, country from suppliers;
```
City|Country
Aachen|Germany
Albuquerque|USA
Anchorage|USA
Ann Arbor|USA
Annecy|France
Barcelona|Spain
Barquisimeto|Venezuela
Bend|USA
Bergamo|Italy
Berlin|Germany
Bern|Switzerland
Boise|USA
Boston|USA
Brandenburg|Germany
Bruxelles|Belgium
Bräcke|Sweden
Buenos Aires|Argentina
Butte|USA
Campinas|Brazil
Caracas|Venezuela
Charleroi|Belgium
City|Country
Cork|Ireland
Cowes|UK
Cunewalde|Germany
Cuxhaven|Germany
Elgin|USA
Eugene|USA
Frankfurt|Germany
Frankfurt a.M.|Germany
Genève|Switzerland
Graz|Austria
Göteborg|Sweden
Helsinki|Finland
I. de Margarita|Venezuela
Kirkland|USA
Kobenhavn|Denmark
Köln|Germany
Lander|USA
Lappeenranta|Finland
Leipzig|Germany
Lille|France
Lisboa|Portugal
London|UK
Luleå|Sweden
Lyngby|Denmark
Lyon|France
Madrid|Spain
Manchester|UK
Mannheim|Germany
Marseille|France
Melbourne|Australia
Montceau|France
Montréal|Canada
México D.F.|Mexico
München|Germany
Münster|Germany
Nantes|France
New Orleans|USA
Osaka|Japan
Oulu|Finland
Oviedo|Spain
Paris|France
Portland|USA
Ravenna|Italy
Reggio Emilia|Italy
Reims|France
Resende|Brazil
Rio de Janeiro|Brazil
Salerno|Italy
Salzburg|Austria
San Cristóbal|Venezuela
San Francisco|USA
Sandvika|Norway
Sao Paulo|Brazil
Seattle|USA
Sevilla|Spain
Singapore|Singapore
Stavern|Norway
Ste-Hyacinthe|Canada
Stockholm|Sweden
Strasbourg|France
Stuttgart|Germany
Sydney|Australia
Tokyo|Japan
Torino|Italy
Toulouse|France
Tsawassen|Canada
Vancouver|Canada
Versailles|France
Walla Walla|USA
Warszawa|Poland
Zaandam|Netherlands
Århus|Denmark
```

3. Create a list of every country where we have both a customer and a supplier.
select country from customers intersect select country from suppliers;
```
Country
Brazil
Canada
Denmark
Finland
France
Germany
Italy
Norway
Spain
Sweden
UK
USA
```

4. Create a list of every city and country where we have both a customer and a supplier.
select city, country from customers intersect select city, country from suppliers;
```
City|Country
Berlin|Germany
London|UK
Montréal|Canada
Paris|France
Sao Paulo|Brazil
```

5. Create a list of every country where we have customers but not suppliers.
select country from customers except select country from suppliers;
```
Country
Argentina
Austria
Belgium
Country
Ireland
Mexico
Poland
Portugal
Switzerland
Venezuela
```

6. Create a list of every country where we have suppliers but not customers.
select country from suppliers except select country from customers;
```
Country
Australia
Japan
Netherlands
Singapore
```

7. Create a list of every country where we have suppliers but not customers and where we have customers
but not suppliers. Do not include any country where we have both suppliers and customers.
select country from (select country from (select country from suppliers except select country from customers) union select country from (select country from customers except select country from suppliers)) except select country from (select country from customers intersect select country from suppliers);
```
country
Argentina
Australia
Austria
Belgium
Country
Ireland
Japan
Mexico
Netherlands
Poland
Portugal
Singapore
Switzerland
Venezuela
```
