`Let's cover **UNION, INTERSECT, and FULL JOIN** in SQL with examples using tables to illustrate each concept:

### 1. UNION

- **Description**: Combines the results of two or more `SELECT` statements into a single result set, removing duplicate rows by default.
- **Usage**: Useful when you want to combine rows from different tables or queries that have the same structure.

#### Example with Tables:

Consider two tables, `Employees` and `Customers`, with the following structure:

**Employees Table:**
```
| EmployeeID | Name       | DepartmentID |
|------------|------------|--------------|
| 1          | Alice      | 101          |
| 2          | Bob        | 102          |
| 3          | Charlie    | 101          |
| 4          | David      | 103          |
```

**Customers Table:**
```
| CustomerID | Name       | CustomerType |
|------------|------------|--------------|
| 1          | Eve        | Regular      |
| 2          | Frank      | VIP          |
| 3          | Alice      | Regular      |
| 4          | Grace      | VIP          |
```

#### SQL Query:
```sql
-- Selecting names from both tables
SELECT Name FROM Employees
UNION
SELECT Name FROM Customers;
```

#### Result:
```
| Name    |
|---------|
| Alice   |
| Bob     |
| Charlie |
| David   |
| Eve     |
| Frank   |
| Grace   |
```

### 2. INTERSECT

- **Description**: Returns the common rows between two or more `SELECT` statements, removing duplicate rows by default.
- **Usage**: Useful when you want to find common elements between datasets.

#### Example with Tables:

Using the same `Employees` and `Customers` tables:

#### SQL Query:
```sql
-- Finding common names in both tables
SELECT Name FROM Employees
INTERSECT
SELECT Name FROM Customers;
```

#### Result:
```
| Name  |
|-------|
| Alice |
```

### 3. FULL JOIN (or FULL OUTER JOIN)

- **Description**: Returns all rows when there is a match in either the left (first) or right (second) table. If there is no match, NULL values are included.
- **Usage**: Useful when you want to combine the results of both left and right joins.

#### Example with Tables:

Using the same `Employees` and `Customers` tables:

#### SQL Query:
```sql
-- Full join to get all names from both tables
SELECT Employees.Name AS EmployeeName, Customers.Name AS CustomerName
FROM Employees
FULL JOIN Customers ON Employees.Name = Customers.Name;
```

#### Result:
```
| EmployeeName | CustomerName |
|--------------|--------------|
| Alice        | Alice        |
| Bob          | NULL         |
| Charlie      | NULL         |
| David        | NULL         |
| NULL         | Eve          |
| NULL         | Frank        |
| NULL         | Grace        |
```

In this example:
- Rows with names present in both `Employees` and `Customers` are matched (`Alice`).
- Employees `Bob`, `Charlie`, and `David` are included with `NULL` values for `CustomerName` because they do not have corresponding entries in `Customers`.
- Customers `Eve`, `Frank`, and `Grace` are included with `NULL` values for `EmployeeName` because they do not have corresponding entries in `Employees`.

### Summary:

- **UNION**: Combines results of multiple `SELECT` statements, removing duplicates.
- **INTERSECT**: Returns common rows between `SELECT` statements, removing duplicates.
- **FULL JOIN**: Returns all rows when there is a match in either the left or right table, including unmatched rows with `NULL` values.

These examples with tables demonstrate how each SQL operation (`UNION`, `INTERSECT`, and `FULL JOIN`) works and how they can be applied to real-world scenarios to manipulate and retrieve data effectively from relational databases.