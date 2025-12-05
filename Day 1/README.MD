## **Day 1: Fundamentals and Relational Design**

### **Course Overview:**

Welcome to Day 1 of the **Database Design Crash Course**! Today, we'll focus on the fundamentals of databases, data modeling, and relational design principles. You will learn how to design databases using **Entity-Relationship (ER) diagrams**, **normalize data** to reduce redundancy, and translate your designs into a relational schema.

### **Learning Objectives:**

By the end of Day 1, you will be able to:

1. Understand the core concepts of databases, including tables, rows, columns, primary keys, and foreign keys.
2. Create an **Entity-Relationship (ER)** diagram for a database system.
3. Normalize data to eliminate redundancy and ensure consistency.
4. Translate an ER diagram into a relational schema and implement it in SQL.

---

### **Session Breakdown:**

#### **Session 1: Introduction to Databases (1 hour)**

**Objective:** Understand what databases are and how relational databases work.

* **What is a Database?**

  * A structured collection of data that is stored electronically and can be accessed or managed via a Database Management System (DBMS).
  * Types of databases: Relational (SQL), NoSQL (Key-Value, Document, Column-Family, etc.)
* **Relational Databases (RDBMS):**

  * Data is stored in tables with rows (records) and columns (fields).
  * Key concepts:

    * **Primary Key**: A unique identifier for each record.
    * **Foreign Key**: A key that links one table to another.
    * **Referential Integrity**: Ensuring data consistency between related tables.

**Practical Activity:** Brief discussion of your course DBMS (e.g., MySQL, PostgreSQL) and how tables are structured.

---

#### **Session 2: Data Modeling and ER Diagrams (2 hours)**

**Objective:** Learn how to model data and visualize relationships between entities using **Entity-Relationship (ER) diagrams**.

* **Data Modeling Basics:**

  * **Entities**: Objects or concepts that have data stored about them (e.g., Customer, Product).
  * **Attributes**: Data fields of an entity (e.g., Customer Name, Product Price).
  * **Relationships**: How entities are related (e.g., Customer buys Product).

* **Cardinality of Relationships:**

  * **One-to-One (1:1)**: A single instance of one entity is related to a single instance of another entity.
  * **One-to-Many (1:M)**: A single instance of one entity can relate to many instances of another entity.
  * **Many-to-Many (M:N)**: Multiple instances of one entity can relate to multiple instances of another entity.

**Practical Activity:** Create an ER diagram for a simple application (e.g., a library system with Books and Authors).

---

#### **Session 3: Database Normalization (2 hours)**

**Objective:** Learn how to organize data efficiently by applying **Normalization** techniques.

* **Why Normalize?**

  * Reduces data redundancy and improves data integrity.
  * Eliminates anomalies (e.g., insertion, update, and deletion anomalies).

* **First Normal Form (1NF)**: Eliminate duplicate rows and ensure each field contains atomic values (i.e., no multiple values in one column).

* **Second Normal Form (2NF)**: Eliminate partial dependencies by ensuring all non-key attributes are fully dependent on the primary key.

* **Third Normal Form (3NF)**: Eliminate transitive dependencies by ensuring that non-key attributes do not depend on other non-key attributes.

**Practical Activity:** Normalize a sample schema (e.g., customer orders) to 3NF. Identify and remove redundant data.

---

#### **Session 4: Translating ERD to Relational Schema (2 hours)**

**Objective:** Learn how to convert an **Entity-Relationship Diagram (ERD)** into a **Relational Schema** and implement it in SQL.

* **From ERD to Tables**:

  * Convert entities to tables.
  * Convert attributes to columns.
  * Convert relationships to foreign keys.

* **Creating the Relational Schema:**

  * Write SQL **CREATE TABLE** statements.
  * Define **Primary Keys** and **Foreign Keys**.
  * Set **data types** for each column (e.g., `VARCHAR`, `INT`, `DATE`).

**Practical Activity:** Using your ER diagram from earlier, write SQL statements to create the corresponding tables and relationships. Run the SQL in your DBMS.

---

#### **Session 5: Database Design Best Practices (1 hour)**

**Objective:** Learn best practices for designing and maintaining a database system.

* **Integrity Constraints:**

  * **Primary Key**: Uniquely identifies each record.
  * **Foreign Key**: Ensures that relationships between tables are consistent.
  * **Not Null, Unique, and Check Constraints**: Ensure data validity and prevent invalid data entry.

* **Indexing for Performance:**

  * What are indexes? How do they improve query performance?
  * When should you use indexes (e.g., on primary/foreign keys, frequently queried fields)?

**Practical Activity:** Review your schema and ensure that **primary keys** and **foreign keys** are properly defined. Consider adding an index to improve query speed.

---

### **Additional Resources:**

* **Textbooks and References:**

  * *Database Design for Mere Mortals* by Michael J. Hernandez
  * *Database System Concepts* by Silberschatz, Korth, and Sudarshan

* **Tools:**

  * SQL Database: MySQL, PostgreSQL, SQLite
  * ER Diagram Tools: dbdiagram.io, Lucidchart, Draw.io

---

### **What to Expect Tomorrow (Day 2):**

On Day 2, we’ll dive into more advanced topics such as:

* Advanced Normalization (4NF, 5NF)
* NoSQL design principles and when to use NoSQL
* Hands-on SQL: Query optimization and performance strategies
* Final project design and hands-on practice

---

### **Important Tips for Day 1:**

* **Practice as you learn**: Take time to create ER diagrams and SQL queries for hands-on practice.
* **Ask Questions**: Don’t hesitate to ask for clarification during the sessions.
* **Focus on Concepts**: Ensure you understand **why** certain database design decisions are made (e.g., why normalize? why use foreign keys?).

