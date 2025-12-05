## **2-Day Database Design Crash Course Syllabus**

### **Day 1: Fundamentals and Relational Design**

#### **Session 1: Introduction to Databases (1 hour)**

* **Overview of Databases**

  * What is a database? (Purpose and importance)
  * Key concepts: Tables, Records, Fields
  * Types of databases: Relational vs. NoSQL
  * Example DBMS: MySQL, PostgreSQL, MongoDB
* **Relational Database Basics**

  * Structure of a relational database: Tables, Rows, Columns
  * Primary Keys, Foreign Keys, and Referential Integrity

#### **Session 2: Data Modeling and ER Diagrams (2 hours)**

* **Data Modeling Concepts**

  * Entities, attributes, relationships
  * Primary Key vs. Foreign Key
  * Cardinality: One-to-one, One-to-many, Many-to-many
* **Entity-Relationship (ER) Diagrams**

  * How to draw an ER diagram
  * Identifying entities, attributes, and relationships
  * Mapping cardinalities: 1:1, 1:N, M:N

#### **Session 3: Database Normalization (2 hours)**

* **Why Normalize?**

  * Importance of normalization in avoiding data anomalies
  * First Normal Form (1NF): Eliminating duplicate rows
  * Second Normal Form (2NF): Removing partial dependencies
  * Third Normal Form (3NF): Removing transitive dependencies
  * Quick exercise: Normalize a sample schema

* **When to Denormalize**

  * Trade-offs: Performance vs. data integrity

#### **Session 4: Translating ERD to Relational Schema (2 hours)**

* **From ERD to Tables**

  * Mapping entities to tables
  * Converting relationships to foreign keys
  * Creating a schema from an ERD (Practical exercise)
* **Hands-on Practice**

  * Convert a simple ER diagram to relational schema using SQL

#### **Session 5: Database Design Best Practices (1 hour)**

* **Integrity Constraints**

  * Primary Key, Foreign Key, Unique, Not Null, Check constraints
  * Ensuring referential integrity and security in design
* **Basic Indexing**

  * Introduction to indexing and its performance impact
  * When to use indexes (on primary keys, foreign keys, etc.)

---

### **Day 2: Advanced Topics, SQL, and Practical Design**

#### **Session 1: Advanced Database Design Concepts (2 hours)**

* **Advanced Normalization (4NF and 5NF)**

  * Multi-valued and join dependencies
  * Quick overview of Boyce-Codd Normal Form (BCNF) and its use cases
* **Designing for Performance**

  * Trade-offs between normalization and denormalization
  * Query optimization strategies
  * Indexing best practices

#### **Session 2: NoSQL Design Overview (1 hour)**

* **When to Use NoSQL**

  * Key-value stores, Document stores, Column-family, and Graph databases
  * Differences between relational and NoSQL databases
  * How to design schemas for MongoDB, Cassandra, and other NoSQL systems
* **NoSQL Design Principles**

  * Data modeling for performance, scalability, and availability

#### **Session 3: Practical SQL Implementation (2 hours)**

* **Basic SQL Commands**

  * Create, Alter, Drop tables
  * Write SQL queries: SELECT, INSERT, UPDATE, DELETE
* **Querying for Data Retrieval**

  * Joins (Inner Join, Left Join, Right Join)
  * Aggregations (GROUP BY, COUNT, SUM)
* **Exercise**

  * Hands-on SQL session: Design a database schema for a simple e-commerce application and run queries

#### **Session 4: Final Project and Hands-on Design (2 hours)**

* **Final Design Challenge**

  * Create an ER diagram and corresponding relational schema for a given scenario (e.g., library system, e-commerce site, etc.)
  * Implement the schema in SQL (CREATE statements)
* **Group Discussion and Q&A**

  * Review of the final project designs
  * Open discussion and feedback
  * Troubleshoot common design issues

#### **Session 5: Review and Wrap-Up (1 hour)**

* **Quick Recap of Key Concepts**

  * ER modeling, normalization, and relational design
  * Best practices for database integrity and performance
  * Design considerations for NoSQL and relational databases
* **Final Q&A**

  * Address any remaining questions or challenges from the course
  * Provide additional resources for further learning

---

### **Course Materials:**

* **Textbook:**

  * *Database Design for Mere Mortals* by Michael J. Hernandez
  * *Database System Concepts* by Silberschatz, Korth, and Sudarshan

* **Tools:**

  * SQL Database (e.g., MySQL or SQLite)
  * ER Diagram Tool (e.g., dbdiagram.io or Lucidchart)

* **Project Files:**

  * Sample SQL scripts, ER diagram templates, and example databases

---

### **Course Outcomes:**

By the end of the 2-day crash course, you will:

* Have a strong grasp of relational database design concepts.
* Be able to translate real-world requirements into normalized database schemas.
* Understand how to optimize for performance, integrity, and scalability.
* Be familiar with both SQL and NoSQL design principles.
* Complete a hands-on project that demonstrates your ability to design and implement a relational database.

