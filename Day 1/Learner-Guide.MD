# **Day 1 Learner Guide: Fundamentals and Relational Design**

---

### **Overview of Day 1:**

Welcome to Day 1 of the **Database Design Crash Course**! Today, we’ll focus on the following core topics:

1. Understanding **databases** and the **relational model**.
2. Learning how to **model data** using **Entity-Relationship (ER) diagrams**.
3. **Normalizing data** to reduce redundancy and improve data integrity.
4. Translating an ER diagram into a **relational schema** and implementing it with **SQL**.

By the end of today, you'll be able to:

* Define key database concepts and how relational databases work.
* Create Entity-Relationship diagrams to visually represent a database.
* Normalize a database to 3NF to avoid data anomalies.
* Write SQL to implement a relational schema from an ER diagram.

---

### **Session 1: Introduction to Databases**

#### **Key Concepts:**

* **What is a Database?**

  * A **database** is an organized collection of data, stored and accessed electronically.
  * **DBMS (Database Management System)**: Software that helps in creating, managing, and interacting with databases (e.g., MySQL, PostgreSQL, MongoDB).

* **Relational Databases**:

  * In relational databases, data is stored in **tables** with rows and columns.
  * A **primary key** uniquely identifies each row in a table.
  * A **foreign key** is a column that links to the primary key in another table, establishing a relationship between tables.

#### **Key Takeaways:**

* Tables store **data** in **rows** (records) and **columns** (fields).
* **Primary Key**: Ensures each record is unique.
* **Foreign Key**: Links tables together.

---

### **Session 2: Data Modeling & ER Diagrams**

#### **Key Concepts:**

* **Data Modeling**: The process of designing the structure of a database by defining its entities, attributes, and relationships.

* **Entity-Relationship Diagram (ERD)**:

  * **Entity**: Represents an object or concept (e.g., `Customer`, `Product`).
  * **Attribute**: Defines properties of an entity (e.g., `Customer Name`, `Product Price`).
  * **Relationship**: Describes how entities are connected (e.g., `Customer` **buys** `Product`).

* **Cardinality**:

  * **One-to-One (1:1)**: A record in one table is related to a record in another table.
  * **One-to-Many (1:M)**: A record in one table is related to multiple records in another.
  * **Many-to-Many (M:N)**: Multiple records in one table are related to multiple records in another table (handled by a **junction table**).

#### **Practice:**

* Draw an ER diagram for a **Library System** (Entities: Books, Authors; Relationship: "Writes").

#### **Key Takeaways:**

* Use ER diagrams to visually represent your data and relationships.
* Recognize **cardinality** to design how entities interact with each other.

---

### **Session 3: Database Normalization**

#### **Key Concepts:**

* **Normalization**: The process of organizing data to eliminate redundancy and avoid anomalies (insertion, update, deletion).

* **First Normal Form (1NF)**:

  * Eliminate repeating groups or duplicate columns.
  * Ensure each column contains **atomic** (indivisible) values.

* **Second Normal Form (2NF)**:

  * Eliminate **partial dependencies**: non-key attributes must depend on the **entire** primary key (for composite keys).

* **Third Normal Form (3NF)**:

  * Eliminate **transitive dependencies**: non-key attributes should not depend on other non-key attributes.

#### **Practice:**

* Normalize a non-normalized table for an **Orders** system through 1NF, 2NF, and 3NF.
* Example: Convert a customer order table with redundant data into a normalized form.

#### **Key Takeaways:**

* **1NF**: Remove repeating groups.
* **2NF**: Remove partial dependencies.
* **3NF**: Remove transitive dependencies.

---

### **Session 4: Translating ERD to Relational Schema**

#### **Key Concepts:**

* **Relational Schema**: The blueprint of a relational database, defined by tables, attributes, and relationships.

* **Translating ERD to Tables**:

  * Each **entity** becomes a **table**.
  * Each **attribute** becomes a **column**.
  * Each **relationship** between entities is represented by **foreign keys**.

* **SQL Syntax for Table Creation**:

  * **CREATE TABLE**: Defines the structure of the table.
  * Define **Primary Keys** and **Foreign Keys**.
  * Example:

    ```sql
    CREATE TABLE Customers (
        CustomerID INT PRIMARY KEY,
        CustomerName VARCHAR(100),
        ContactName VARCHAR(100)
    );
    ```

#### **Practice:**

* Translate the **Library System ER Diagram** into an SQL **CREATE TABLE** statement for the `Books` and `Authors` tables.

#### **Key Takeaways:**

* ERDs are converted into **tables** and **foreign keys** in the relational schema.
* Use **SQL CREATE TABLE** statements to define database tables and relationships.

---

### **Session 5: Database Design Best Practices**

#### **Key Concepts:**

* **Integrity Constraints**: Ensure the accuracy and reliability of data.

  * **Primary Key**: Uniquely identifies each record in a table.
  * **Foreign Key**: Enforces referential integrity between tables.
  * **Not Null**, **Unique**, **Check Constraints**: Ensure data validity.
* **Indexing**: A method to optimize query performance, especially for frequently queried columns.

  * Index **primary keys** and columns frequently used in **JOINs** or **WHERE** clauses.

#### **Practice:**

* Implement **Primary Key**, **Foreign Key**, and **Not Null** constraints in your SQL table definitions.
* Write an **Index** statement for a column that is queried frequently.

#### **Key Takeaways:**

* **Integrity Constraints** ensure that the database maintains consistency.
* **Indexes** improve query performance.

---

### **Homework & Practice (Optional)**

1. **Create an ER Diagram**: Design an ER diagram for a **student registration system** (Entities: Student, Course, Instructor, Enrollment).
2. **Normalize the Schema**: Normalize the student registration system to **3NF**.
3. **Write SQL Code**: Implement the relational schema in SQL by creating tables for the student registration system.

---

### **Summary of Day 1:**

Today, we covered:

* **Introduction to databases**: Understanding tables, primary keys, and foreign keys.
* **Data modeling**: How to visualize database structure using ER diagrams.
* **Normalization**: Techniques to organize data into 1NF, 2NF, and 3NF.
* **Translating ER diagrams to relational schemas**: Writing SQL to implement your designs.
* **Best practices**: Ensuring data integrity and optimizing performance with indexing.

---

### **Next Steps:**

* **Review your work**: Go over your ER diagrams, SQL statements, and normalized tables.
* **Prepare for Day 2**: Tomorrow, we'll dive into advanced normalization, NoSQL design principles, and optimization techniques.

---

### **Resources for Further Study:**

* **Books**:

  * *Database Design for Mere Mortals* by Michael J. Hernandez.
  * *Database System Concepts* by Silberschatz, Korth, and Sudarshan.
* **Online Resources**:

  * W3Schools SQL Tutorial: [https://www.w3schools.com/sql/](https://www.w3schools.com/sql/)
  * dbdiagram.io: [https://dbdiagram.io/](https://dbdiagram.io/) for ER diagram creation.
