Sure, Dylan! Here’s another full-length mock exam for Database Management Systems (DBMS) covering different areas. This mock exam will include multiple-choice, true/false, short answer, and essay questions, along with a detailed marking scheme and explanations for each question.

### Mock Exam: Database Management Systems

#### Section A: Multiple Choice Questions (20 marks)

**1. Which of the following is not a type of database model? (1 mark)**
   - a) Hierarchical
   - b) Network
   - c) Relational
   - d) Linear
?
   **Answer:** d) Linear

**2. In SQL, which command is used to remove a table from a database? (1 mark)**
   - a) DELETE
   - b) REMOVE
   - c) DROP
   - d) TRUNCATE
?
   **Answer:** c) DROP

**3. What is a primary key in a database? (1 mark)**
   - a) A field that uniquely identifies a record in a table
   - b) A field that contains duplicate values
   - c) A field that is used for indexing
   - d) A field that cannot have null values
?
   **Answer:** a) A field that uniquely identifies a record in a table

**4. Which SQL statement is used to extract data from a database? (1 mark)**
   - a) SELECT
   - b) GET
   - c) EXTRACT
   - d) FETCH
?
   **Answer:** a) SELECT


**5. What does ACID stand for in the context of database transactions? (1 mark)**
   - a) Atomicity, Consistency, Isolation, Durability
   - b) Atomicity, Correctness, Isolation, Durability
   - c) Atomicity, Consistency, Integrity, Durability
   - d) Atomicity, Correctness, Integrity, Durability
?
   **Answer:** a) Atomicity, Consistency, Isolation, Durability


**6. Which of the following is a valid SQL constraint? (1 mark)**
   - a) PRIMARY KEY
   - b) FOREIGN CONSTRAINT
   - c) UNIQUE CONSTRAINT
   - d) DEFAULT CONSTRAINT
?
   **Answer:** a) PRIMARY KEY


**7. What is the purpose of normalization in databases? (1 mark)**
   - a) To reduce data redundancy
   - b) To increase data redundancy
   - c) To speed up database queries
   - d) To create backup copies of the database
?
   **Answer:** a) To reduce data redundancy


**8. In a relational database, what is a foreign key? (1 mark)**
   - a) A field that uniquely identifies each record within its table
   - b) A field that links to the primary key of another table
   - c) A field that is used for indexing
   - d) A field that contains foreign data
?
   **Answer:** b) A field that links to the primary key of another table


**9. Which of the following is used to establish a relationship between tables? (1 mark)**
   - a) Index
   - b) Primary Key
   - c) Foreign Key
   - d) View
?
   **Answer:** c) Foreign Key


**10. Which of the following statements is true about a clustered index? (1 mark)**
    - a) A table can have multiple clustered indexes
    - b) Clustered indexes store data in a non-sequential order
    - c) Clustered indexes are slower to read than non-clustered indexes
    - d) A table can have only one clustered index

    **Answer:** d) A table can have only one clustered index

#### Section B: True/False Questions (10 marks)


**1. In a relational database, a table can have more than one primary key. (1 mark)**
?
   **Answer:** False


**2. SQL stands for Structured Query Language. (1 mark)**
?
   **Answer:** True


**3. A view in SQL is a virtual table based on the result set of an SQL query. (1 mark)**
?
   **Answer:** True


**4. The JOIN clause is used to combine rows from two or more tables based on a related column. (1 mark)**
?
   **Answer:** True


**5. The UPDATE command in SQL is used to delete records from a table. (1 mark)**
?
   **Answer:** False


**6. A transaction in a database must be atomic, which means it must be completed in its entirety or not at all. (1 mark)**
?
   **Answer:** True


**7. SQL functions such as COUNT(), AVG(), and SUM() are aggregate functions. (1 mark)**
?
   **Answer:** True


**8. The GROUP BY clause is used to filter the result set of an SQL query. (1 mark)**
?
   **Answer:** False


**9. Referential integrity ensures that foreign key values in a table match primary key values in another table. (1 mark)**
   - True

   **Answer:** True


**10. Indexes in a database can slow down data retrieval. (1 mark)**
?
**Answer:** False

#### Section C: Short Answer Questions (30 marks)


**1. What are the differences between a DELETE and a TRUNCATE command in SQL? (5 marks)**
?
**Answer:**
- **DELETE:**
  - Removes specific rows from a table based on a condition.
  - Can be rolled back if used within a transaction.
  - Slower compared to TRUNCATE because it logs individual row deletions.
- **TRUNCATE:**
  - Removes all rows from a table, leaving the table structure intact.
  - Cannot be rolled back if used outside a transaction.
  - Faster as it deallocates data pages instead of logging individual row deletions.


**2. Explain the concept of a relational database and its advantages. (5 marks)**
?
**Answer:**
- **Relational Database:**
  - A type of database that stores data in tables with rows and columns. Tables are related to each other through keys (primary and foreign keys).
- **Advantages:**
  - **Data Integrity:** Enforces rules to ensure data accuracy and consistency.
  - **Flexibility:** Easy to add new tables, columns, and relationships.
  - **Scalability:** Supports large amounts of data and concurrent users.
  - **Security:** Allows fine-grained access control.
  - **Querying:** Powerful SQL language for data retrieval and manipulation.


**3. Describe the different types of joins in SQL with examples. (5 marks)**
?
**Answer:**
- **Inner Join:**
  - Returns rows with matching values in both tables.
  - Example:
    ```sql
    SELECT a.name, b.salary 
    FROM employees a 
    INNER JOIN payroll b 
    ON a.id = b.employee_id;
    ```
- **Left Join (Left Outer Join):**
  - Returns all rows from the left table and matched rows from the right table. Unmatched rows show NULL.
  - Example:
    ```sql
    SELECT a.name, b.salary 
    FROM employees a 
    LEFT JOIN payroll b 
    ON a.id = b.employee_id;
    ```
- **Right Join (Right Outer Join):**
  - Returns all rows from the right table and matched rows from the left table. Unmatched rows show NULL.
  - Example:
    ```sql
    SELECT a.name, b.salary 
    FROM employees a 
    RIGHT JOIN payroll b 
    ON a.id = b.employee_id;
    ```
- **Full Join (Full Outer Join):**
  - Returns rows when there is a match in one of the tables. Unmatched rows from both tables show NULL.
  - Example:
    ```sql
    SELECT a.name, b.salary 
    FROM employees a 
    FULL OUTER JOIN payroll b 
    ON a.id = b.employee_id;
    ```


**4. What is a transaction in a database? Explain its properties. (5 marks)**
?
**Answer:**
- **Transaction:**
  - A sequence of one or more SQL operations executed as a single unit of work. Transactions ensure data integrity.
- **Properties (ACID):**
  - **Atomicity:** Ensures that all operations within a transaction are completed; otherwise, the transaction is aborted.
  - **Consistency:** Ensures that the database transitions from one valid state to another.
  - **Isolation:** Ensures that transactions are executed independently without interference.
  - **Durability:** Ensures that the results of a transaction are permanent and survive system failures.


**5. Explain the concept of indexing in databases and its types. (5 marks)**
?
**Answer:**
- **Indexing:**
  - A database optimization technique that improves the speed of data retrieval operations by creating a data structure that provides a quick lookup.
- **Types:**
  - **Primary Index:** Automatically created on the primary key. Ensures unique and quick access.
  - **Secondary Index:** Created on non-primary key columns. Improves performance on frequently searched columns.
  - **Clustered Index:** Orders the physical data in the table based on the indexed column. A table can have only one clustered index.
  - **Non-Clustered Index:** Creates a separate structure for the index, which points to the actual data. A table can have multiple non-clustered indexes.
  - **Composite Index:** An index on multiple columns. Useful for queries involving multiple conditions.

#### Section D: Essay Questions (40 marks)


**1. Discuss the role of normalization in database design. Explain its different forms and their importance. (20 marks)**
?
**Answer:**
- **Normalization:**
  - The process of organizing data to reduce redundancy and improve data integrity.
- **Forms of Normalization:**
  - **First Normal Form (1NF):**
    - Ensures each table column contains atomic values and each record is unique.
    - Importance: Eliminates duplicate columns and ensures entries are scalar values.
  - **Second Normal Form (2NF):**
    - Achieved when the table is in 1NF and all non-key attributes are fully functional dependent on the primary key.
    - Importance: Removes partial dependency and ensures each non-key column is dependent on the whole primary key.
  - **Third Normal Form (3NF):**
    - Achieved when the table is in 2NF and all attributes are not transitively dependent on the primary key.
    - Importance: Eliminates transitive dependency, ensuring non-key attributes are independent of each other.
  - **Boyce-Codd Normal Form (BCNF):**
    - A stronger version of 3NF where every determinant is a candidate key.
    - Importance: Addresses anomalies that 3NF doesn’t cover, providing a higher level of data integrity.
  - **Fourth Normal Form (4NF):**
    - Achieved when the table is in BCNF and has no multi-valued dependencies.
    - Importance: Ensures a single record does not contain multiple values for a single attribute, reducing complexity.
  - **Fifth Normal Form (5NF):**
    - Achieved when the table is in 4NF and has no join dependency anomalies.
    - Importance: Ensures every join dependency is a candidate key, providing the most refined level of database design.
- **Importance of Normalization:**
  - **Data Integrity:** Ensures accuracy and consistency of data.
  - **Eliminates Redundancy:** Reduces data duplication, saving storage space.
  - **Improves Query Performance:** Optimizes complex queries and enhances data retrieval speed.
  - **Simplifies Database Maintenance:** Makes it easier to update, insert, or delete data without affecting other tables.



**2. Explain the process of database backup and recovery. Discuss the different types of backups and their advantages. (20 marks)**
?
**Answer:**
- **Database Backup:**
  - The process of creating a copy of the database data to protect against data loss.
- **Backup Process:**
  - **Planning:** Determine backup strategy, including frequency and types of backups.
  - **Execution:** Use database tools or scripts to perform the backup.
  - **Storage:** Store backups securely, preferably off-site or in the cloud.
  - **Testing:** Regularly test backups to ensure they can be restored when needed.
- **Types of Backups:**
  - **Full Backup:**
    - Creates a complete copy of the entire database.
    - **Advantages:** Simplifies recovery since all data is in one backup file.
    - **Disadvantages:** Time-consuming and requires significant storage space.
  - **Incremental Backup:**
    - Backs up only the data that has changed since the last backup.
    - **Advantages:** Faster and requires less storage space compared to full backups.
    - **Disadvantages:** Recovery can be slower as multiple backups may need to be restored.
  - **Differential Backup:**
    - Backs up all data that has changed since the last full backup.
    - **Advantages:** Faster than full backups and simpler recovery compared to incremental backups.
    - **Disadvantages:** Can grow larger and take longer to complete as more data changes.
  - **Transaction Log Backup:**
    - Backs up the transaction log, capturing all changes made to the database.
    - **Advantages:** Allows point-in-time recovery and minimizes data loss.
    - **Disadvantages:** Requires more complex management and storage planning.
- **Recovery Process:**
  - **Identify the Issue:** Determine the cause of data loss or corruption.
  - **Select Backup:** Choose the appropriate backup files for restoration.
  - **Restore Data:** Use database tools to restore from the selected backup.
  - **Validate Recovery:** Ensure the database is consistent and operational.
- **Importance of Backup and Recovery:**
  - **Data Protection:** Safeguards against data loss due to hardware failure, human error, or disasters.
  - **Business Continuity:** Ensures the availability of critical data and minimizes downtime.
  - **Compliance:** Meets regulatory requirements for data retention and protection.


#DBMS 
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
