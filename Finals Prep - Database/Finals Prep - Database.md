---
Created time: 2024-04-28T15:39:00
tags:
  - Academics
---
# Database Design Process
- **Requirements Collection and Analysis**
	- Get requirements
	- Now the users needs
	- Define functional and non functional requirements
- **Conceptual Design** - ER
	- Chose Data model
	- Translate to conceptual schema
	- Identify Entities, Attributes and Relationships
	- Create ER diagram
	- Gam Notes
	  - Choose a data model, translate the requirements into a conceptual schema of the database, by applying the concepts of the chosen data model.
	  - E-R (Entity-Relationship) model is typically used to represent the conceptual design.
- **Logical Design**
  - Map the high-level conceptual schema onto the implementation data model of the database system that will be used.
  - Relational data model.
- **Physical Design**
	- Define physical structure
	- Layout, storage, access paths
---
## Entity-Relationship Model `Relation Schema`
Good one does not have redundant attributes
### **Entity Set**
collection of entities that share common characteristics
  - **Strong entity set**
	  - Exists on its own and has its own existence.
	  - Customers, Orders, products
  - **Weak entity set**
	  - Depends on another entitiy set to exist.
	  - order items (dependent on orders), addresses (dependent on customers).
### **Attributes**
Characteristics of an entity
Simple - Cmplex Derived
  - **Simple attribute**
	  - Single value that describes an entity
	  - Examples: customer name, order date.
  - **Complex attribute**
	  - Made up of multiple simple attributes
	  - Address, Phone Number
  - **Composite**
	  - made of multiple
	  - Fullname
  - Multi-valued
	  - Multiple values
  - **Derived**
	  - Gotten from others
	  - Total cost = Units * unit price*
- **Relationship Set**
	- Relationships between sets
---
## Structural Constraints
- **Mapping Cardinalities**
  - **One-to-one**
	  - Related to only one instance of another entity
	  - Customer - Address
  - **One-to-many**
	  - Related to multiple instances of another entity
	  - Customer - Orders
  - **Many-to-one**
	  - Many instances are related to one instance of another
	  - Orders - Customer
  - **Many-to-many**
	  - Multiple instances of one entity are related to multiple instances of another entity
- **Participation Constraint**
	- This is the minimum number of instances of one entity that must be related to another
  - **Total**
	  - Each instance must be related to at least one instance of another entity
	  - Customer -> Order
  - **Partial**
	  - Not every instance needs to be related to another entity
---
## Logical Design
Converting E-R model to Relational
Make schema, keys, weak to strong, Combine
1. **Make** a **schema** for each entity set and relationship set
2. Pick primary and foreign **keys**
3. **Link** weak sets to string sets
4. **Combine** the schemas
- E-R model -> Relational model
  - For each entity set and for each relationship set, there is a unique schema to which we assign the name of the corresponding entity set or relationship set.
  - Specify primary key and foreign key (if there are any) for each relation.
  - Relationship set between weak entity set and its identifying entity set.
  - Combination of schemas.

---
## Normalization
Organizing data to reduce redundance
- **Decomposition**
	- Statements are made dynamically during runtime
- Functional Dependencies
- 1NF, 2NF, 3NF, BCNF, …
---
## Accessing SQL from a Programming Language
### Two approaches to accessing SQL from a general-purpose programming language: `Embedded Dynamite`
  - **Dynamic SQL:**
	  - Made and run dynamically during runtime
	  - Built as string and executed
  - **Embedded SQL**
	  - Compiled alongside language code
	  - Embedded into the programming language
### Database connectivity:
  - **JDBC** `Java Database Connectiviy`
	  - API for accessing relational databases
	  - Gives interface for accessing DBMS
  - **ODBC** `Open Database Connection`
	  - C based to access DBMS
	  - Allows to connect to database, execute SQL
- **General usage**
  - `Import Connect Execute Results Close`
  - **Import** necessary libraries
  - Establish **connection**
  - **Execute** SQL statements
  - Get **results**
  - **Close** connection
  - Steps involved – no programming required.

---
## Security
Authorize - Access - Views - Backup - Integrity - Encrypt
- Counter Measures:
  - Authorization
  - Access controls
  - Views
  - Backup and recovery
  - Integrity
  - Encryption
  - **RAID technology** `Redundant Array of Independent Disks`
- 
---
## NoSQL – Document Databases
- Important characteristics of large-scale data management systems: **SCAF**
  - **Scalability**:
	  - Be able to handling increasing data and user trafiic without loss in performance
	  - Can grow with organizational needs
  - **Cost**
	  - Opensource and Cheap
  - **Flexibility**
	  - Be adaptable to changing business needs
	  - Doesn't need a fixed table structure
	  - Can add attributes without updating design
  - **Availability**
	  - Have high uptime availability
	  - Through backup servers
	  - NoSQL uses multiple servers or distributed systems
  - 
### CAP theorem:
  - **Consistency**
	  - consistent copies of data on different servers
	  - **Two Phase commit**
		  - Writes to the disk of primary server
		  - Writes to the backup server
  - **Availability**
	  - providing a response to any query
  - **Partition protection/tolerance**
	  - if a network that connects two or more database servers fails, the servers will still be available with consistent dataall at the same time
### ACID and BASE:
#### Isolated Strong Atom Twins
  - **Atomicity**
	  - All or nothing for transactions
	  - Treat all transactions as indivisible
  - **Consistency**
	  - Transactions dont leave data bases in a state of violated integrity
  - **Isolation**
	  - Transactions are not visible to others until they are complete
  - **Durability**
	  - Once completed, the transaction remain even in the event of a power loss
#### Base: Soft Consistent Available Base
  - **Basically Available**
	  - Available and respond to requests even during failures
	  - There can be a partial failure in some parts of the distributed system and the rest of the system continues to function
  - **Soft State**
	  - Allows temporary inconsistencies and eventual consistency
	  - data will expire if it is not refreshed
  - **Eventually Consistent**
	  - There may be times when the database is in an inconsistent state
#### Types of Eventual Consistency `Casual Monitonic Read & Write Session`
- **Casual Consistency** `Ordering food during date`
	- Preserves the order of updates
- **Read-your-writes consistency** `Only see newest`
	- Once updated all the reads of the record will retur updated the value the 
- **Session consistency**
	- Read and write consistency during session
- **Monotonic read consistency**
	- Never see earlier versions
- **Monotonic Write Consistency** 
	- Writes are done in order
#### Types of NoSQL databases
- **Key-value pair**
	- Store data as a collection of key-value pairs, where each item in the database is a simple key-value pair
- **Document**
	- Self-describing documents with their own attributes
- **Graph**
	- Store and query as nodes and relataionships
- **Column family**
	- Store data in columns instead of rows, making them
---
# Assignments
### **Assignment 3**
  1. Identify entity sets.
  2. Decide appropriate attributes for each entity set.
  3. Build relationship sets between entity sets.
  4. Remove redundant attributes.

### **Assignment 4**
  - Functional dependencies derived from the information about the system.
  - UNF -> 1NF: Remove repeating groups.
  - 1NF -> 2NF: Remove partial dependencies.
  - 2NF -> 3NF: Remove transitive dependencies. No decomposition needed in this step since there is no non-primary-key attributes transitively dependent on the primary key.
---
# Exam Details
- **Date**: Thursday, May 2nd
- **Time**: 11:30 AM – 1:30 PM
- **Tasks**:
  - Build an ER model for a given problem.
  - Derive relational schema from ER diagram.
  - Normalize given relations to 3NF relations.
  - Answer short questions.
---
# Practice
Here is a sample table database for you to practice normalization:

**Order Table**

| Order ID | Customer ID | Order Date | Product ID | Product Name | Quantity | Price |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 101 | 2022-01-01 | 1001 | Apple iPhone | 2 | 1000.00 |
| 1 | 101 | 2022-01-01 | 1002 | Samsung TV | 1 | 1500.00 |
| 2 | 102 | 2022-01-05 | 1003 | Sony Headphones | 3 | 50.00 |
| 2 | 102 | 2022-01-05 | 1004 | Canon Camera | 1 | 800.00 |
| 3 | 103 | 2022-01-10 | 1005 | HP Laptop | 2 | 1200.00 |

**Customer Table**

| Customer ID | Customer Name | Address | Phone |
| --- | --- | --- | --- |
| 101 | John Smith | 123 Main St | 555-1234 |
| 102 | Jane Doe | 456 Elm St | 555-5678 |
| 103 | Bob Johnson | 789 Oak St | 555-9012 |

Your task is to normalize this database to 3NF. You can start by identifying the functional dependencies and then applying the normalization steps:

1. UNF -> 1NF: Remove repeating groups.
2. 1NF -> 2NF: Remove partial dependencies.
3. 2NF -> 3NF: Remove transitive dependencies.
### 1NF
Order table

| Order ID |     |
| -------- | --- |
| 1        |     |
| 2        |     |
