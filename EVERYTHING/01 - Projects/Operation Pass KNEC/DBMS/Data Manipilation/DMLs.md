### Comprehensive Guide to Database Manipulation in MySQL

Manipulating databases involves creating, modifying, and deleting tables and fields. Below is a full rundown of these operations in MySQL.

### 1. Creating a Database and Table

**Create Database**:
```sql
CREATE DATABASE School;
```
This command creates a new database named `School`.

**Use Database**:
```sql
USE School;
```
This command selects the `School` database to work within it.

**Create Table**:
```sql
CREATE TABLE Students (
    StudentID INT AUTO_INCREMENT PRIMARY KEY,
    FullName VARCHAR(100),
    Age INT,
    Major VARCHAR(50)
);
```
This command creates a `Students` table with fields `StudentID`, `FullName`, `Age`, and `Major`.

### 2. Adding a Field to a Table

To add a new field to an existing table, use the `ALTER TABLE` statement with the `ADD` clause.

**Example**:
```sql
ALTER TABLE Students
ADD Email VARCHAR(255);
```
This command adds a new field called `Email` to the `Students` table.

### 3. Renaming a Field in a Table

To rename an existing field, use the `ALTER TABLE` statement with the `CHANGE COLUMN` clause.

**Example**:
```sql
ALTER TABLE Students
CHANGE COLUMN FullName Name VARCHAR(100);
```
This command renames the `FullName` field to `Name` in the `Students` table.

### 4. Changing the Data Type of a Field

To change the data type of an existing field, use the `MODIFY COLUMN` clause.

**Example**:
```sql
ALTER TABLE Students
MODIFY COLUMN Age TINYINT;
```
This command changes the data type of the `Age` field to `TINYINT`.

### 5. Removing a Field from a Table

To remove an existing field, use the `ALTER TABLE` statement with the `DROP COLUMN` clause.

**Example**:
```sql
ALTER TABLE Students
DROP COLUMN Age;
```
This command removes the `Age` field from the `Students` table.

### 6. Renaming a Table

To rename an existing table, use the `RENAME TABLE` statement.

**Example**:
```sql
RENAME TABLE Students TO Learners;
```
This command renames the `Students` table to `Learners`.

### 7. Removing a Table

To remove (drop) an entire table, use the `DROP TABLE` statement.

**Example**:
```sql
DROP TABLE Learners;
```
This command removes the `Learners` table from the database.

### 8. Adding and Removing Data

**Insert Data**:
```sql
INSERT INTO Students (FullName, Age, Major, Email)
VALUES ('Alice Smith', 20, 'Computer Science', 'alice@example.com');
```
This command inserts a new record into the `Students` table.

**Update Data**:
```sql
UPDATE Students
SET Major = 'Physics'
WHERE StudentID = 1;
```
This command updates the `Major` field of the student with `StudentID` 1.

**Delete Data**:
```sql
DELETE FROM Students
WHERE StudentID = 1;
```
This command deletes the record of the student with `StudentID` 1.

### 9. Queries and Data Retrieval

**Select Data**:
```sql
SELECT * FROM Students;
```
This command retrieves all records from the `Students` table.

**Conditional Select**:
```sql
SELECT FullName, Email
FROM Students
WHERE Major = 'Computer Science';
```
This command retrieves the `FullName` and `Email` of students who are majoring in Computer Science.

### Summary

#### Commands Recap

1. **Creating Database and Table**:
    ```sql
    CREATE DATABASE School;
    USE School;
    CREATE TABLE Students (StudentID INT AUTO_INCREMENT PRIMARY KEY, FullName VARCHAR(100), Age INT, Major VARCHAR(50));
    ```

2. **Adding a Field**:
    ```sql
    ALTER TABLE Students ADD Email VARCHAR(255);
    ```

3. **Renaming a Field**:
    ```sql
    ALTER TABLE Students CHANGE COLUMN FullName Name VARCHAR(100);
    ```

4. **Changing Data Type**:
    ```sql
    ALTER TABLE Students MODIFY COLUMN Age TINYINT;
    ```

5. **Removing a Field**:
    ```sql
    ALTER TABLE Students DROP COLUMN Age;
    ```

6. **Renaming a Table**:
    ```sql
    RENAME TABLE Students TO Learners;
    ```

7. **Removing a Table**:
    ```sql
    DROP TABLE Learners;
    ```

8. **Adding, Updating, Deleting Data**:
    ```sql
    INSERT INTO Students (FullName, Age, Major, Email) VALUES ('Alice Smith', 20, 'Computer Science', 'alice@example.com');
    UPDATE Students SET Major = 'Physics' WHERE StudentID = 1;
    DELETE FROM Students WHERE StudentID = 1;
    ```

9. **Retrieving Data**:
    ```sql
    SELECT * FROM Students;
    SELECT FullName, Email FROM Students WHERE Major = 'Computer Science';
    ```

### COUNT Function in DBMS

In Database Management Systems (DBMS), the `COUNT` function is used to return the number of rows that match a specified condition within a table or a result set. Here's a comprehensive explanation of the `COUNT` function:

### Key Points:

1. **Syntax**:
   ```sql
   COUNT(expression)
   ```
   - `expression` can be `*` (to count all rows), a column name, or an expression.

2. **Functionality**:
   - **Counting Rows**: `COUNT(*)` counts all rows in a table, including those with NULL values.
   - **Counting Non-NULL Values**: `COUNT(column_name)` counts the number of non-NULL values in the specified column.
   - **Counting Distinct Values**: `COUNT(DISTINCT column_name)` counts the number of distinct (unique) non-NULL values in the specified column.

3. **Usage**:
   - Typically used in `SELECT` statements to retrieve and display the count of rows that meet certain criteria.

4. **Example Queries**:

   - **Counting All Rows**:
     ```sql
     SELECT COUNT(*) FROM Employees;
     ```
     This query returns the total number of rows in the `Employees` table.

   - **Counting Non-NULL Values**:
     ```sql
     SELECT COUNT(EmployeeID) FROM Employees;
     ```
     This query counts the number of non-NULL `EmployeeID` values in the `Employees` table.

   - **Counting Distinct Values**:
     ```sql
     SELECT COUNT(DISTINCT Department) FROM Employees;
     ```
     This query counts the number of distinct department names in the `Employees` table.

5. **Behavior**:
   - `COUNT` always returns a numeric value.
   - If there are no rows that match the condition, `COUNT` returns 0.
   - `COUNT` can be combined with other functions and clauses, such as `GROUP BY`, `HAVING`, and `WHERE`, to perform complex data analysis.

### Example Scenario:

Consider a table `Orders` where you want to analyze the number of orders placed by each customer:

```sql
CREATE TABLE Orders (
    OrderID INT AUTO_INCREMENT PRIMARY KEY,
    CustomerID INT,
    OrderDate DATE,
    TotalAmount DECIMAL(10, 2)
);

INSERT INTO Orders (CustomerID, OrderDate, TotalAmount)
VALUES (1, '2024-07-12', 100.50),
       (2, '2024-07-12', 75.25),
       (1, '2024-07-11', 150.00),
       (3, '2024-07-10', 200.75);
```

To count the total number of orders in the `Orders` table:

```sql
SELECT COUNT(*) AS TotalOrders FROM Orders;
```

This query returns:
```
TotalOrders
-----------
4
```


The `COUNT` function in DBMS is a powerful tool for retrieving and analyzing numerical data related to rows in a table or result set. It provides flexibility in counting all rows, specific columns, or distinct values, making it essential for various data analysis tasks in database applications. Understanding `COUNT` helps in efficiently managing and querying data to derive meaningful insights from large datasets.