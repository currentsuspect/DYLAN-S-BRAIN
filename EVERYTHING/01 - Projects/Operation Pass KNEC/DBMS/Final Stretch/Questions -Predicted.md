### Chapter 1: Database Design and ER Modeling

#### Section A: Short Answer Questions
1. **Define a database schema.** 
   - A database schema is the blueprint or structure of a database, defining how data is organized and how relationships among data are associated. It includes definitions of tables, columns, data types, and constraints.

![[Pasted image 20240718101524.png]]

2. **What is an entity? Provide an example.**
   - An entity is a real-world object or concept that can be distinctly identified in a database. Example: A Customer in a sales database.

3. **Explain the difference between a primary key and a foreign key.**
   - A primary key is a unique identifier for a record within a table, ensuring each record is unique. A foreign key is a field in one table that links to the primary key of another table, establishing a relationship between the two tables.

4. **What is a composite key?**
   - A composite key is a primary key that consists of two or more columns used together to uniquely identify a record in a table.

5. **List three types of relationships in an ER diagram.**
   - One-to-One (1:1), One-to-Many (1:M), Many-to-Many (M:M)

6. **Define an attribute and provide an example.**
   - An attribute is a property or characteristic of an entity. Example: The attribute "Name" for the entity "Customer."

7. **What is the purpose of normalization in database design?**
   - Normalization organizes data to reduce redundancy and improve data integrity by dividing large tables into smaller, related tables.

8. **Explain what a weak entity is and provide an example.**
   - A weak entity is an entity that cannot be uniquely identified by its attributes alone and relies on a foreign key relationship with another entity. Example: An "OrderItem" that depends on "Order."

9. **Describe the term "cardinality" in the context of ER diagrams.**
   - Cardinality defines the number of instances of one entity that can be associated with instances of another entity. Examples include one-to-one, one-to-many, and many-to-many relationships.

10. **What is a relationship set?**
    - A relationship set is a set of associations between entities. It represents the connections between entity instances in an ER diagram.

#### Section B: Essay Questions
1. **Design an ER diagram for a university database that includes entities for Students, Courses, and Instructors.**
   - Draw an ER diagram with entities: Student (StudentID, Name, Major), Course (CourseID, Title, Credits), and Instructor (InstructorID, Name, Department). Include relationships such as Student-Course (enrollment), Instructor-Course (teaching).

2. **Discuss the steps involved in transforming an ER diagram into a relational schema.**
   - Steps include:
     1. Identify entities and convert them to tables.
     2. Define primary keys for each table.
     3. Identify relationships and add foreign keys to establish connections.
     4. Normalize tables to reduce redundancy.
     5. Review and refine the schema for optimization.

#### Section C: Practical Questions
1. **Given the following entities and their attributes, draw an ER diagram:**
   - **Customers:** CustomerID, Name, Address, Phone
   - **Orders:** OrderID, OrderDate, CustomerID
   - **Products:** ProductID, ProductName, Price
   - **OrderDetails:** OrderID, ProductID, Quantity
   - **Answer:** Draw an ER diagram with relationships: Customers to Orders (one-to-many), Orders to OrderDetails (one-to-many), Products to OrderDetails (one-to-many).

2. **Normalize the given relation to 3NF:**
   - **Orders(OrderID, OrderDate, CustomerID, CustomerName, ProductID, ProductName, Quantity, Price)**
   - **Answer:** 
     1. First Normal Form (1NF): Eliminate repeating groups.
     2. Second Normal Form (2NF): Remove partial dependencies.
     3. Third Normal Form (3NF): Remove transitive dependencies.
     - Resulting tables:
       - Orders(OrderID, OrderDate, CustomerID)
       - Customers(CustomerID, CustomerName)
       - OrderDetails(OrderID, ProductID, Quantity, Price)
       - Products(ProductID, ProductName, Price)

### Chapter 2: SQL Queries

#### Section A: Short Answer Questions
1. **What is a SQL query?**
   - A SQL query is a statement used to perform tasks such as retrieving data, updating records, or managing database objects in a relational database.

2. **Explain the difference between a SELECT and an UPDATE statement.**
   - SELECT retrieves data from one or more tables. UPDATE modifies existing records in a table.

3. **What is a JOIN operation in SQL?**
   - A JOIN operation combines rows from two or more tables based on a related column between them.

4. **Define an aggregate function and give an example.**
   - An aggregate function performs a calculation on a set of values and returns a single value. Example: SUM() to calculate the total of a numeric column.

5. **What does the WHERE clause do in a SQL query?**
   - The WHERE clause filters records based on specified conditions.

6. **Explain the purpose of the GROUP BY clause.**
   - The GROUP BY clause groups rows that have the same values in specified columns into summary rows.

7. **What is a subquery in SQL?**
   - A subquery is a query nested inside another query.

8. **Describe the difference between INNER JOIN and OUTER JOIN.**
   - INNER JOIN returns rows that have matching values in both tables. OUTER JOIN returns all rows from one table and matched rows from the other, including unmatched rows as NULL.

9. **What is the purpose of the HAVING clause?**
   - The HAVING clause filters groups based on specified conditions, used with GROUP BY.

10. **Define a view in SQL.**
    - A view is a virtual table based on a SQL query that displays data from one or more tables.

#### Section B: Essay Questions
1. **Explain the process of writing and optimizing SQL queries. Include examples of different types of joins and subqueries.**
   - Writing and optimizing SQL queries involves:
     1. Understanding requirements and identifying necessary tables and columns.
     2. Using SELECT, FROM, WHERE, JOIN, GROUP BY, HAVING clauses as needed.
     3. Using indexes, avoiding unnecessary columns, and writing efficient subqueries.
     - Examples:
       - INNER JOIN: `SELECT * FROM Orders INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID`
       - Subquery: `SELECT * FROM Products WHERE Price > (SELECT AVG(Price) FROM Products)`

2. **Discuss the significance of data integrity in SQL and the role of constraints. Provide examples of different types of constraints.**
   - Data integrity ensures accuracy and consistency of data. Constraints enforce rules on data:
     - PRIMARY KEY: Ensures unique values in a column.
     - FOREIGN KEY: Ensures referential integrity between tables.
     - UNIQUE: Ensures all values in a column are unique.
     - CHECK: Ensures values in a column meet a specific condition.
     - NOT NULL: Ensures a column cannot have NULL values.

#### Section C: Practical Questions
1. **Write a SQL query to find the names of all customers who have placed orders worth more than $500.**
   ```sql
   SELECT Customers.Name
   FROM Customers
   JOIN Orders ON Customers.CustomerID = Orders.CustomerID
   WHERE Orders.TotalAmount > 500;
   ```

2. **Given the following tables, write SQL queries to:**
   - **List all products and their prices.**
     ```sql
     SELECT ProductName, Price FROM Products;
     ```
   - **Find all orders placed by a specific customer (by CustomerID).**
     ```sql
     SELECT * FROM Orders WHERE CustomerID = 'specificCustomerID';
     ```
   - **Calculate the total quantity of each product ordered.**
     ```sql
     SELECT ProductID, SUM(Quantity) AS TotalQuantity FROM OrderDetails GROUP BY ProductID;
     ```
   - **Update the price of a specific product (by ProductID).**
     ```sql
     UPDATE Products SET Price = newPrice WHERE ProductID = 'specificProductID';
     ```
   - **Delete all orders older than a specific date.**
     ```sql
     DELETE FROM Orders WHERE OrderDate < 'specificDate';
     ```

### Chapter 3: Normalization

#### Section A: Short Answer Questions
1. **What is the first normal form (1NF)?**
   - 1NF ensures that each column contains atomic (indivisible) values and each record is unique.

2. **Define partial dependency and give an example.**
   - Partial dependency occurs when a non-key attribute depends on part of a composite key. Example: In a table with (StudentID, CourseID, InstructorName), if InstructorName depends only on CourseID, it's a partial dependency.

3. **What is transitive dependency? Provide an example.**
   - Transitive dependency occurs when a non-key attribute depends on another non-key attribute. Example: In a table with (StudentID, AdvisorID, AdvisorName), if AdvisorName depends on AdvisorID, it's a transitive dependency.

4. **Explain the purpose of normalization.**
   - Normalization reduces redundancy and improves data integrity by organizing data into smaller, related tables.

5. **Describe the second normal form (2NF).**
   - 2NF eliminates partial dependencies by ensuring that non-key attributes depend on the whole primary key.
