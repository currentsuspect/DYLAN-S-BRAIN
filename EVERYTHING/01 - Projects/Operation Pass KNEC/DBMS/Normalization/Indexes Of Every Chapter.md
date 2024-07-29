### Chapter 1: Introduction to Database Systems

- **Database**: A collection of organized data that can be easily accessed, managed, and updated.
- **Database Management System (DBMS)**: Software that uses a database to store, retrieve, and manage data efficiently. Examples include MySQL, Oracle, and Microsoft SQL Server.
- **Data**: Raw facts and figures without context, such as numbers or text.
- **Information**: Data processed in a meaningful way to be useful.
- **Data Processing**: The collection and manipulation of data to produce meaningful information.
- **File System**: A method of storing and organizing files on a disk.
- **Database System**: An integrated system combining the database, the DBMS, and the associated applications.
- **Database Applications**: Software applications that interact with the database to perform tasks like querying, updating, and reporting.
- **Database Users**: Individuals who interact with the database, including end-users, application programmers, and database administrators.
- **Database Administrator (DBA)**: A person responsible for the installation, configuration, upgrading, administration, monitoring, and maintenance of databases.
- **DBMS Architecture**: The framework for managing data, typically divided into three levels: internal, conceptual, and external.
- **Three-Level Architecture (ANSI-SPARC)**: A DBMS architecture with three levels: internal (physical storage), conceptual (logical structure), and external (user views).
- **Data Independence**: The ability to change the schema at one level without affecting the schema at the next higher level.

### Chapter 2: Data Models

- **Data Model**: A conceptual framework for organizing and defining data elements and their relationships.
- **Conceptual Model**: An abstract model defining what data the system contains and how it is related.
- **Logical Model**: A detailed version of the conceptual model, often used in the design of the database.
- **Physical Model**: Defines how the data will be stored in the database.
- **Entity-Relationship (ER) Model**: A conceptual model that defines the structure of data in terms of entities, attributes, and relationships.
- **Entity**: A distinct object in the database, such as a person, place, or thing.
- **Attribute**: A property or characteristic of an entity.
- **Relationship**: An association among entities.
- **ER Diagram**: A graphical representation of an ER model.
- **Relational Model**: Represents data as tables (relations) with rows and columns.
- **Hierarchical Model**: Data is organized in a tree-like structure.
- **Network Model**: Data is organized in a graph, allowing more complex relationships.
- **Object-Oriented Model**: Data is represented as objects, similar to object-oriented programming.
- **Object-Relational Model**: Combines features of the relational model and the object-oriented model.

### Chapter 3: Database Design

- **Database Design**: The process of creating a detailed data model of a database.
- **Schema**: The structure of the database, defined in a formal language.
- **Schema Mapping**: The process of matching the elements of one schema with the elements of another.
- **Conceptual Design**: The high-level design of the database, focusing on what data will be stored.
- **Logical Design**: The detailed design of the database, focusing on how data will be stored.
- **Physical Design**: The implementation of the logical design in a specific DBMS.
- **Normalization**: The process of organizing data to minimize redundancy.
- **Normal Forms**: Guidelines for organizing data into tables (1NF, 2NF, 3NF, BCNF, 4NF, 5NF).
- **Functional Dependency**: A relationship between two attributes, typically between the primary key and other attributes.
- **Primary Key**: A unique identifier for a record in a table.
- **Foreign Key**: An attribute in one table that refers to the primary key of another table.
- **Composite Key**: A primary key composed of multiple attributes.
- **Surrogate Key**: An artificial key used as a primary key.
- **Candidate Key**: An attribute, or a set of attributes, that uniquely identifies a tuple in a relation.
- **Referential Integrity**: Ensures that relationships between tables remain consistent.
- **Entity Integrity**: Ensures that each table has a unique primary key.

### Chapter 4: SQL - Structured Query Language

- **SQL**: A standard language for managing and manipulating databases.
- **DDL (Data Definition Language)**: Part of SQL used to define database structures, such as tables.
  - **Examples**: CREATE, ALTER, DROP
- **DML (Data Manipulation Language)**: Part of SQL used for data manipulation.
  - **Examples**: SELECT, INSERT, UPDATE, DELETE
- **DCL (Data Control Language)**: Part of SQL used to control access to data.
  - **Examples**: GRANT, REVOKE
- **TCL (Transaction Control Language)**: Part of SQL used to manage transactions.
  - **Examples**: COMMIT, ROLLBACK, SAVEPOINT
- **SELECT Statement**: Retrieves data from a database.
- **INSERT Statement**: Adds new records to a table.
- **UPDATE Statement**: Modifies existing records in a table.
- **DELETE Statement**: Removes records from a table.
- **CREATE Statement**: Creates a new database object, such as a table.
- **ALTER Statement**: Modifies an existing database object.
- **DROP Statement**: Deletes a database object.
- **JOIN**: Combines rows from two or more tables based on a related column.
  - **Types**: Inner Join, Left Join, Right Join, Full Join
- **Subqueries**: Queries nested inside another query.
- **Indexes**: Data structures that improve the speed of data retrieval.
- **Views**: Virtual tables created by a query.
- **Stored Procedures**: Precompiled SQL statements that can be executed as needed.
- **Triggers**: SQL code that is automatically executed in response to certain events on a particular table or view.

### Chapter 5: Relational Algebra and Relational Calculus

- **Relational Algebra**: A procedural query language that uses operators to manipulate relations.
- **Selection (σ)**: Selects rows that satisfy a given predicate.
- **Projection (π)**: Selects specific columns from a relation.
- **Union (∪)**: Combines tuples from two relations, removing duplicates.
- **Set Difference (−)**: Returns tuples from one relation that are not in another.
- **Cartesian Product (×)**: Combines tuples from two relations in a pairwise fashion.
- **Rename (ρ)**: Renames the output relation.
- **Natural Join (⋈)**: Combines relations based on common attribute values.
- **Theta Join (⋈θ)**: Combines relations based on a given condition.
- **Division (÷)**: Returns tuples from one relation that match with every tuple in another relation.
- **Relational Calculus**: A non-procedural query language that uses mathematical predicates.
- **Tuple Relational Calculus (TRC)**: Uses tuple variables and predicates to describe queries.
- **Domain Relational Calculus (DRC)**: Uses domain variables and predicates to describe queries.

### Chapter 6: Database Security and Authorization

- **Database Security**: Protecting the database against unauthorized access, modification, or destruction.
- **Data Privacy**: Ensuring that sensitive data is not disclosed to unauthorized individuals.
- **Authentication**: Verifying the identity of users.
- **Authorization**: Granting or denying access to resources based on user identity.
- **Access Control**: Mechanisms to restrict access to data.
- **Encryption**: Transforming data into an unreadable format to protect it from unauthorized access.
- **SQL Injection**: A code injection technique that might destroy your database.
- **Role-Based Access Control (RBAC)**: Restricting system access to authorized users based on roles.
- **Discretionary Access Control (DAC)**: Access control based on the discretion of the data owner.
- **Mandatory Access Control (MAC)**: Access control based on fixed policies enforced by the system.
- **Audit Trails**: Records of database activities for security and monitoring purposes.
- **Security Policies**: Formal rules governing data access and handling.

### Chapter 7: Transaction Management

- **Transaction**: A sequence of operations performed as a single logical unit of work.
- **ACID Properties**: Set of properties that guarantee that database transactions are processed reliably.
  - **Atomicity**: Ensures that all operations within a transaction are completed; if not, the transaction is aborted.
  - **Consistency**: Ensures that a transaction brings the database from one valid state to another.
  - **Isolation**: Ensures that the operations of one transaction are isolated from others.
  - **Durability**: Ensures that the results of a completed transaction are permanent.
- **Transaction States**: Various states a transaction goes through, including active, partially committed, committed, failed, and aborted.
- **Commit**: Makes all changes made by a transaction permanent.
- **Rollback**: Undoes all changes made by a transaction.
- **Concurrency Control**: Techniques to ensure that multiple transactions can execute concurrently without leading to inconsistencies.
- **Locking Mechanisms**: Techniques to control access to data items.
- **Deadlock**: A situation where two or more transactions are waiting for each other to release locks.
- **Deadlock Prevention**: Techniques to ensure that deadlocks do not occur.
- **Deadlock Detection**: Techniques to detect deadlocks.
- **Deadlock Resolution**: Techniques to break deadlocks.
- **Isolation Levels**: Degrees of isolation for transactions, such as read uncommitted, read committed, repeatable read, and serializable.
- **Serializability**: Ensures that the outcome of executing transactions concurrently is the same as if they were executed serially.

### Chapter 8: Database Recovery

- **Database Recovery**: Restoring the database to a correct state after a failure.
- **Backup**: A copy of the database at a specific point in time.
- **Restore**: The process of returning the database to a correct state using a backup.
- **Recovery Techniques**: Methods to restore the database, including log-based recovery and shadow paging.
- **Log-Based Recovery**: Uses a log of all changes made to the database to restore it.
- **Checkpoints**: Points in time at which the database state is saved to assist in recovery.
- **Shadow Paging**: Maintains two copies of the database, one current and one shadow.
- **Deferred Update**: Updates are not written to the database until after a transaction has committed.
- **Immediate Update**: Updates are written to the database as soon as they are made.
- **Recovery Time Objective (RTO)**: The maximum acceptable downtime after a failure.
- **Recovery Point Objective (RPO)**: The maximum acceptable amount of data loss after a failure.

### Chapter 9: Distributed Databases

- **Distributed Database**: A database that is spread across multiple physical locations.
- **Distributed Database Management System (DDBMS)**: Manages a distributed database and makes it appear as a single database to users.
- **Data Fragmentation**: Dividing a database into pieces that can be distributed across multiple locations.
- **Data Replication**: Storing copies of data on multiple servers to improve availability and reliability.
- **Data Allocation**: Deciding where to place data fragments in a distributed database.
- **Horizontal Fragmentation**: Dividing a table into rows.
- **Vertical Fragmentation**: Dividing a table into columns.
- **Two-Phase Commit Protocol**: A protocol to ensure all parts of a distributed transaction are committed.
- **Distributed Query Processing**: Techniques to process queries in a distributed database environment.
- **Distributed Transaction Management**: Managing transactions that span multiple locations in a distributed database.
- **CAP Theorem**: States that a distributed system can have at most two of three properties: consistency, availability, and partition tolerance.

### Chapter 10: Advanced Database Technologies

- **NoSQL Databases**: Non-relational databases designed to handle large volumes of unstructured data. Examples include MongoDB, Cassandra, and Redis.
- **Big Data**: Large and complex data sets that traditional data processing tools cannot handle.
- **Data Warehousing**: Storing and managing large amounts of data for analysis and reporting.
- **Data Mining**: Extracting useful information from large data sets.
- **OLAP (Online Analytical Processing)**: Tools for analyzing data stored in a data warehouse.
- **OLTP (Online Transaction Processing)**: Systems that manage transaction-oriented applications.
- **Cloud Databases**: Databases that run on cloud computing platforms.
- **In-Memory Databases**: Databases that store data in memory for faster access.
- **Graph Databases**: Databases that use graph structures to represent and store data. Examples include Neo4j and Amazon Neptune.
- **Time Series Databases**: Databases optimized for time-stamped data. Examples include InfluxDB and TimescaleDB.
- **Blockchain Databases**: Databases that use blockchain technology to provide a decentralized, secure ledger. Examples include BigchainDB and Chainlink.

This detailed explanation should help you understand each keyword and concept related to DBMS in ICT Module 2.