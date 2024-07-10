### Mock Exam: Database Management Systems

#### Section A: Multiple Choice Questions (20 marks)

**Q: Which of the following is not a type of database management system? (1 mark)**
   - a) Hierarchical DBMS
   - b) Network DBMS
   - c) Relational DBMS
   - d) Distributed DBMS
   - e) Spreadsheet DBMS
   ?
   **Answer:** e) Spreadsheet DBMS


**Q: The primary key in a database table: (1 mark)**
   - a) Uniquely identifies each record in the table
   - b) Can be NULL
   - c) Can contain duplicate values
   - d) Is used to establish relationships between tables
   ?
   **Answer:** a) Uniquely identifies each record in the table


**Q: Which SQL statement is used to extract data from a database? (1 mark)**
   - a) GET
   - b) EXTRACT
   - c) SELECT
   - d) RETRIEVE
?
   **Answer:** c) SELECT


**Q: In SQL, which keyword is used to specify a condition while retrieving data? (1 mark)**
   - a) WHERE
   - b) IF
   - c) WHEN
   - d) THEN
   ?
   **Answer:** a) WHERE


**Q: What does the acronym ACID stand for in database systems? (1 mark)**
   - a) Atomicity, Consistency, Isolation, Durability
   - b) Accuracy, Consistency, Integrity, Durability
   - c) Atomicity, Concurrency, Isolation, Durability
   - d) Accuracy, Concurrency, Integrity, Durability
   ?
   **Answer:** a) Atomicity, Consistency, Isolation, Durability


**Q: Which normal form ensures that there are no partial dependencies of any attribute on the primary key? (1 mark)**
   - a) 1NF
   - b) 2NF
   - c) 3NF
   - d) BCNF
?
   **Answer:** b) 2NF

**Q: A foreign key is: (1 mark)**
   - a) A unique key in a table
   - b) A key used to uniquely identify a row in another table
   - c) A key that cannot be null
   - d) A key that references a primary key in the same table

   **Answer:** b) A key used to uniquely identify a row in another table

**Q: Which of the following is a Data Definition Language (DDL) command? (1 mark)**
   - a) SELECT
   - b) INSERT
   - c) UPDATE
   - d) CREATE
?
   **Answer:** d) CREATE


**Q: The process of organizing data to minimize redundancy is called: (1 mark)**
   - a) Normalization
   - b) Indexing
   - c) Partitioning
   - d) Replication
?
   **Answer:** a) Normalization


**Q: In an ER diagram, an oval represents: (1 mark)**
    - a) Entity
    - b) Attribute
    - c) Relationship
    - d) Primary key
?
	**Answer:** b) Attribute

#### Section B: True/False Questions (10 marks)

**Q: A database is a collection of interrelated data. (1 mark)**
   - True
?
   **Answer:** True

**2. SQL is a procedural language. (1 mark)**
?
   **Answer:** False

**3. A surrogate key is a natural key used to uniquely identify a record in a table. (1 mark)**
?
   **Answer:** False

**4. The SQL command to delete all rows from a table is TRUNCATE. (1 mark)**
?
   **Answer:** True

**5. A view in SQL is a virtual table based on the result-set of an SQL statement. (1 mark)**
?
   **Answer:** True

**6. In a relational database, a row is also known as a tuple. (1 mark)**
?
   **Answer:** True

**7. The GROUP BY clause in SQL is used to filter records. (1 mark)**
?
   **Answer:** False

**8. Referential integrity ensures that foreign key values in a table always point to existing records in another table. (1 mark)**
?
   **Answer:** True

**9. A clustered index rearranges the way records in the table are physically stored. (1 mark)**
?
   **Answer:** True

**10. Data integrity constraints are used to ensure accuracy and consistency of data in a database. (1 mark)**
    - True
?
**Answer:** True

#### Section C: Short Answer Questions (30 marks)


**1. Explain the difference between a primary key and a unique key. (5 marks)**
?
**Answer:**
- **Primary Key:**
  - Uniquely identifies each record in a table.
  - Cannot be NULL.
  - Only one primary key is allowed per table.
  - Ensures entity integrity.
- **Unique Key:**
  - Ensures that all values in a column are unique.
  - Can contain NULL values (though each NULL is considered unique).
  - Multiple unique keys can be defined in a table.
  - Used to enforce unique constraints on a column.

**2. What are the different types of JOIN operations in SQL? Explain each with an example. (10 marks)**
?
**Answer:**
- **INNER JOIN:**
  - Returns records that have matching values in both tables.
  - Example:
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    INNER JOIN departments ON employees.department_id = departments.id;
    ```
- **LEFT JOIN (or LEFT OUTER JOIN):**
  - Returns all records from the left table, and the matched records from the right table. If no match, NULLs are returned.
  - Example:
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    LEFT JOIN departments ON employees.department_id = departments.id;
    ```
- **RIGHT JOIN (or RIGHT OUTER JOIN):**
  - Returns all records from the right table, and the matched records from the left table. If no match, NULLs are returned.
  - Example:
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    RIGHT JOIN departments ON employees.department_id = departments.id;
    ```
- **FULL JOIN (or FULL OUTER JOIN):**
  - Returns all records when there is a match in either left or right table. If no match, NULLs are returned.
  - Example:
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    FULL JOIN departments ON employees.department_id = departments.id;
    ```
- **CROSS JOIN:**
  - Returns the Cartesian product of the two tables, i.e., all combinations of rows.
  - Example:
    ```sql
    SELECT employees.name, departments.name
    FROM employees
    CROSS JOIN departments;
    ```

**3. Describe the concept of normalization and its benefits. (5 marks)**
?
**Answer:**
- **Normalization:** The process of organizing the fields and tables of a database to minimize redundancy and dependency. It involves dividing large tables into smaller ones and defining relationships between them.
- **Benefits:**
  - Reduces data redundancy.
  - Improves data integrity.
  - Enhances query performance.
  - Simplifies database maintenance.
  - Ensures consistent data through the elimination of anomalies.

**4. What are triggers in a database, and how are they used? Provide an example. (5 marks)**
?
**Answer:**
- **Triggers:** Special procedures that are automatically executed in response to certain events on a particular table or view in a database.
- **Usage:**
  - Enforcing business rules.
  - Validating data integrity.
  - Keeping audit trails.
  - Automating system tasks.
- **Example:**
  ```sql
  CREATE TRIGGER trg_after_insert
  AFTER INSERT ON employees
  FOR EACH ROW
  BEGIN
    INSERT INTO employee_audit (employee_id, action, action_time)
    VALUES (NEW.id, 'INSERT', NOW());
  END;
  ```

#### Section D: Essay Questions (40 marks)

**1. Discuss the role of a Database Management System (DBMS) in an organization's information system. Include its components and benefits. (20 marks)**
?
**Answer:**
- **Role of DBMS:**
  - A DBMS serves as the backbone of an organization's information system by providing efficient, reliable, and secure access to data. It supports data management tasks such as storage, retrieval, and manipulation of data.
- **Components:**
  - **Database Engine:** Core service for accessing and processing data.
  - **Database Schema:** Structure that defines the database’s logical design.
  - **Query Processor:** Translates and executes database queries.
  - **Transaction Manager:** Ensures ACID properties for transactions.
  - **Data Dictionary:** Metadata repository containing details about database objects.
  - **Backup and Recovery Systems:** Tools for data backup and restoration.
- **Benefits:**
  - **Data Consistency:** Ensures data remains accurate and consistent across the database.
  - **Data Security:** Provides mechanisms to protect data against unauthorized access.
  - **Data Sharing:** Allows multiple users to access data concurrently.
  - **Data Integrity:** Enforces rules to maintain data accuracy and reliability.
  - **Efficient Data Management:** Simplifies data retrieval and manipulation.
  - **Scalability:** Can handle increasing amounts of data and users.
  - **Improved Decision Making:** Provides accurate and timely data for better decision making.


**2. Explain the process of database design from requirements gathering to implementation. Include the stages and activities involved. (20 marks)**
?
**Answer:**
- **Requirements Gathering:**
  - **Activities:** Identifying user requirements, business rules, and data needs through interviews, surveys, and document analysis.
  - **Output:** Requirements specification document.
- **Conceptual Design:**
  - **Activities:** Creating an Entity-Relationship (ER) diagram to represent entities, attributes, and relationships.
  - **Output:** ER diagram.
- **Logical Design:**
  - **Activities:** Converting the ER diagram into a relational schema, defining tables, columns, primary keys, and foreign keys.
  - **Output:** Relational schema.
- **Normalization:**
  - **Activities:** Applying normalization rules to remove redundancy and improve data integrity.
  - **Output:** Normalized tables.
- **Physical Design:**
  - **Activities:** Defining the physical storage structure, indexing strategies, and partitioning.
  - **Output:** Physical schema.
- **Implementation:**
  - **Activities:** Creating database tables, writing SQL scripts, and setting up the DBMS.
  - **Output:** Functional database system.
- **Testing:**
  - **Activities:** Verifying the database design through test cases and validating against requirements.
  - **Output:** Test results and validation reports.
- **Deployment:**
  - **Activities:** Moving the database to the production environment and conducting user training.
  - **Output:** Deployed database system.
- **Maintenance:**
  - **Activities:** Monitoring performance, performing backups, and applying updates and patches.
  - **Output:** Continuous improvement and database maintenance plan.


### Marking Scheme

- **Multiple Choice Questions (20 marks):**
  - Each correct answer: 1 mark.

- **True/False Questions (10 marks):**
  - Each correct answer: 1 mark.

- **Short Answer Questions (30 marks):**
  - Detailed and accurate explanation: 5 marks per question.
  - Partial marks for incomplete but correct answers.

- **Essay Questions (40 marks):**
  - Comprehensive coverage of the topic: 10 marks.
  - Clear structure and organization: 5 marks.
  - Relevant examples and explanations: 5 marks.

By practicing this mock exam, you'll be better prepared for the types of questions you may encounter in your actual KNEC exam. Good luck with your studies, Dylan!

#DBMS 