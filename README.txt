Step 1: Set Up the MySQL Database
1. Install MySQL (if not already installed):
Download and install MySQL if not already downloaded.
2. Create the Database:
Open MySQL Shell
Log in to MySQL:
Enter your root password when prompted.

Create the HomeDepotDB database:

CREATE DATABASE HomeDepotDB;
3. Create Tables:
Use the “SQL Script” file to create tables.:
This will create the tables and the necessary relationships based on the relational schema.
Step 2: Populate the Database with Test Data
1. Insert Sample Data from “Data Population” file:

Execute this script to populate the database with basic data.

Step 3: Implement the Application User Interface (CLI)
1. Download Python and Install MySQL Connector if not already installed:

Install the MySQL Connector library to interact with the database:

pip install mysql-connector-python

2. Save the Python Script (CLI):
Save the Python code for the Command-Line Interface (CLI) in a file named home_depot_cli.py.
3. Run the Application:
Open a terminal and navigate to the folder containing the script.
Run the application:
python home_depot_cli.py

Step 4: Execute Test Queries
1. Test Query 1: List All Products
This query will show all products in the Products table:

SELECT * FROM Products;

2. Test Query 2: View Store Sales
This query will show the total sales per store:

SELECT s.Location, SUM(o.TotalAmount) AS TotalSales
FROM Stores s
JOIN Orders o ON s.StoreID = o.StoreID
GROUP BY s.StoreID;

3. Test Query 3: View All Employees
This query will show all employees and their assigned store:

SELECT e.Name, e.Role, s.Location
FROM Employees e
JOIN Stores s ON e.StoreID = s.StoreID;

4. Test Query 4: View Orders for a Specific Customer
This query will show all orders for a particular customer (e.g., customer with CustomerID 1):

SELECT o.OrderID, o.OrderDate, o.TotalAmount
FROM Orders o
WHERE o.CustomerID = 1;

5. Test Query 5: View Products Supplied by a Supplier
This query will show the products supplied by a specific supplier:

SELECT p.Name, p.Category
FROM Products p
JOIN ProductSupplier ps ON p.ProductID = ps.ProductID
WHERE ps.SupplierID = 1;
Conclusion
You now have the Home Depot database, the Command-Line Interface (CLI) application, and a set of test queries. You can interact with the database using the CLI and verify the system's functionality with the provided test queries.
