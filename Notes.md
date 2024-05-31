---
tags:
  - Academics
---
# Class 1



---

## Databases

- Its and organized collection of data stored and accessed electronically
- Small ones can be stored on a file system
- Large ones are hosted on computer clusters or cloud storage
- Query languages

  - SQL (Structured Query Language): SQL is the most widely used query language for managing and manipulating relational databases. It allows users to perform tasks such as retrieving data, updating records, and creating and modifying database structures.
  - T-SQL (Transact-SQL): T-SQL is an extension of SQL that is used specifically with Microsoft SQL Server. It includes additional features and capabilities beyond standard SQL.
  - PL/SQL (Procedural Language/Structured Query Language): PL/SQL is Oracle Corporation's procedural extension for SQL. It allows users to create stored procedures, functions, and triggers within the Oracle database.
  - NoSQL Query Languages: NoSQL databases, such as MongoDB and Cassandra, use query languages specific to their database systems. These languages may include JavaScript-like syntax for querying and manipulating data.
  - SPARQL: SPARQL is a query language used for querying data stored in Resource Description Framework (RDF) format, commonly used in semantic web applications and linked data.
- Security
- Distributed computing issues including supporting concurrent access and fault tolerance

## Database Management System

- This is the software that interacts with end users, applications, the database itself to capture and analyse data
- has all the main facilities to administer the database
- The admin for postgrasql is pgadmin 4
- **Database System**: Includes the total of the database, dbms and associated apps
- Database can also be used to refer to the database system or app associated with the database

## Classifications of Databases

SQl means Structured Query langauge

- **Relational**: They model data as rows and columns in a series of tables

  - They use SQL
- **Non-Relational**

  - Known as NoSQL
  - They use different query languages

  Examples of NoSQL databases include:

  - MongoDB: document-oriented database that stores data in flexible, JSON-like documents.
  - Cassandra: distributed database designed to handle large amounts of data across many commodity servers.
  - Redis: in-memory data structure store that can be used as a database, cache, and message broker.
  - Neo4j: graph database that stores data in nodes and relationships, allowing for efficient traversal and analysis of complex relationships.
  - CouchDB: A database that uses a document-oriented model and supports replication and offline access.

## Database Management Systems

- DBMS
  - Allows users to performCRUD
- Databases are usually drawn as cylinders
- Everything should go through the DBMS to interact with the database

## Architecture

- Hide low level stuff from users

### Data Abstraction

- Physical level
  - Describes how the data are actualy stored
- Logical Level
  - Describes the data stored and thier relationships
  - Describes entire database in terms of a number of relatively simple structures
  - Independent from the physical level
    - Changes to physical level should be possible but should not affect the logical level
  - View level
    - Describes what the user can see

## Data Models

- **Relational**
  - Uses collection of tables to represent both the data

## Relational Data Model

- Uses a collection of tables to represent the relationships.
- In the context of databases, the relational data model is a way of organizing and representing data using tables. Each table in the model is called a relation, and it consists of rows and columns.

**Tables (Relations):** Tables are used to represent entities or concepts in the real world. For example, if we have a database for a school, we might have tables for students, courses, and teachers. Each table contains related information about a specific entity.

- Tables are known as relations
- Each table has multiple columns
- Relational data model means there are connections between the tables

**Columns:** Each table is made up of multiple columns, also known as attributes or fields. Columns define the type of data that can be stored in them. For example, a student table might have columns for student ID, name, age, and grade.

- Each column has a name

**Rows:** Each row in a table represents a single instance or record of the entity being represented. For example, in the student table, each row would represent a specific student and contain their corresponding data

- Each row represents one piece of information
- Each row has a primary key

**Primary key** is a unique identifier for each row

- An example of a primary key is a student ID number or social security number

**Foreign key** is a column that references the primary key of another table

- For example, a student table might have a foreign key that references the primary key of a course table. This would allow us to link each student to the courses they are enrolled in.
- Or department table

## Database Language

Data-definition language (DDL) is used to define the database structure or schema.

- To specify the database schema like data types, constraints and the relationship between the tables.
- DDL statements create, modify, and remove database objects such as tables, indexes, and users.
- Common DDL statements include:
  - CREATE: Creates a new database object
  - ALTER: Modifies an existing database object
  - DROP: Deletes an entire database object
  - TRUNCATE: Deletes all records from a table, leaving the table structure intact

Data manipulation language (DML) is used to retrieve and modify data in a database.

- DML statements are used to add, update, and delete records from tables.
- TO express database queries and updates
- Common DML statements include:
  - SELECT: Retrieves records from one or more tables
  - INSERT: Adds one or more new records to a table
  - UPDATE: Modifies one or more records in a table
  - DELETE: Deletes one or more records from a table
  - TRUNCATE: Deletes all records from a table

SQL Language

- DDL and DML
- SQL is a standardized language used to create, retrieve, update, and delete data from a relational database. It is the most widely used database language, and is supported by most relational database management systems (RDBMSs).
- SQL is a declarative language, meaning that it is used to describe what data should be retrieved or modified, but does not specify how to perform the operation.
- The database management system (DBMS) determines the most efficient way to carry out the operation based on factors such as the size and structure of the database and available system resources.
- The commands can be embedded in general-purpose programming languages such as Java and Python, allowing SQL-based database applications to be written in any language that supports the database's API.
- SQL is not used for developing complete software applications; it's used for handling the data part of an application.
- Python, C, and C++ have control structures (like loops, conditional statements, functions, etc.), while SQL does not.

### DDL

- Specify the database schema
- Specify the storage structure and access methods used by the database system
  - Different users have different access rights and permissions
  - read, insert update, delete
  - Example
  - CREATE TABLE department (dept_name VARCHAR(20),
    building VARCHAR(15),
    budget NUMERIC(12,2),
    PRIMARY KEY (dept_name));

## DML
Enables users to access or manipulate data as organized by the appropriate data model
Types:
- Procedural
  - User specifies what data is needed and how to get it
  - Example: Find the names of all students who have a GPA greater than 3.6
  - Example: Increase the salary of all employees by 10%
- Non-Procedural
  - User specifies what data is needed without specifying how to get it
  - SQL is a non-procedural language and mostly used in relational databases

