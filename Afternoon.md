DROP TABLE IF EXISTS Person;
DROP TABLE IF EXISTS Orders;

CREATE TABLE  Person (
  ID INTEGER PRIMARY KEY AUTOINCREMENT,
  Name TEXT,
  Age INTEGER,
  Height INTEGER,
  City TEXT,
  FavoriteColor TEXT
  );
  
CREATE TABLE Orders (
  PersonID INTEGER,
  ProductName TEXT,
  ProductPrice INTEGER,
  Quantity INTEGER
  );
  
  INSERT INTO Person ( Name, Age, Height, City, FavoriteColor ) 
  VALUES ( 'Drew McIntire', 22, 178, 'Phoenix', 'Blue' ),
  		 ( 'Devin McIntire', 21, 183, 'Alton', 'Green' ),
         ( 'Dylon Tribble', 8, 137, 'Godfrey', 'Green' ),
         ( 'Harmony Tribble', 40, 157, 'Godfrey', 'Purple' ),
         ( 'Paul', 40, 186, 'Godfrey', 'Red' );
    
SELECT * FROM Person
ORDER BY Height DESC;

SELECT * FROM Person
ORDER BY Height ASC;

SELECT * FROM Person
ORDER BY Age DESC;
  
SELECT * FROM Person
WHERE Age > 20;

SELECT * FROM Person
WHERE Age = 18;

SELECT * FROM Person
WHERE AGE < 20 AND Age > 30;

SELECT * FROM Person
WHERE Age != 27;

SELECT * FROM Person
WHERE FavoriteColor != 'Red';

SELECT * FROM Person
WHERE FavoriteColor != 'Red' AND FavoriteColor != 'Blue';

SELECT * FROM Person
WHERE FavoriteColor = 'Orange' OR FavoriteColor = 'Green';

SELECT * FROM Person
WHERE FavoriteColor IN ('Orange', 'Green', 'Blue');

SELECT * FROM Person
WHERE FavoriteColor IN ('Yellow', 'Purple');

INSERT INTO Orders ( PersonID, ProductName, ProductPrice, Quantity )
VALUES ( 1, 'Bike', 200, 1 ),
	   ( 2, 'Mattress', 600, 2 ),
       ( 1, 'Pillow', 15, 4 ),
       ( 5, 'Cooler', 50, 1 ),
       ( 4, 'Puppy', 300, 2 );
       
SELECT SUM(Quantity) FROM Orders;

SELECT SUM(ProductPrice) FROM Orders
WHERE PersonID = 1;

INSERT INTO Artist (Name) 
VALUES ( 'John White Abbott' ),
	   ( 'Aagot' ),
       ( 'Robert Adam' );
       
SELECT * FROM Artist
ORDER BY Name DESC LIMIT 10;

SELECT * FROM Artist
ORDER BY Name ASC LIMIT 5;

SELECT * FROM Artist
WHERE Name LIKE 'Black%';

SELECT * FROM Artist
WHERE Name LIKE '%Black%';

SELECT FirstName, LastName FROM Employee
WHERE City = 'Calgary';

SELECT FirstName, LastName, MAX(BirthDate) FROM Employee;

SELECT FirstName, LastName, MIN(BirthDate) FROM Employee;

SELECT FirstName, EmployeeId FROM Employee
WHERE FirstName = 'Nancy';

SELECT * FROM Employee 
WHERE ReportsTo = 2;

SELECT count(*) FROM Employee
WHERE City = 'Lethbridge';

SELECT count(*) FROM Invoice
WHERE BillingCountry = 'USA';

SELECT MAX(Total) FROM Invoice;

SELECT MIN(Total) FROM Invoice;

SELECT * FROM Invoice
WHERE Total > 5;

SELECT count(*) FROM Invoice
WHERE Total < 5;

SELECT count(*) FROM Invoice
WHERE BillingState IN( 'CA', 'TX', 'AZ' );

SELECT AVG(Total) FROM Invoice;

SELECT SUM(Total) FROM Invoice;

