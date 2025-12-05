### **Slide Deck: Day 1 - Database Design Crash Course**

---

### **Slide 1: Title Slide**

* **Title:** Day 1: Fundamentals and Relational Design
* **Subtitle:** Database Design Crash Course
* **Instructor Name/Logo**
* **Date**

---

### **Slide 2: Agenda**

* **Session 1:** Introduction to Databases
* **Session 2:** Data Modeling & ER Diagrams
* **Session 3:** Database Normalization
* **Session 4:** Translating ERD to Relational Schema
* **Session 5:** Database Design Best Practices

---

### **Session 1: Introduction to Databases**

#### **Slide 3: What is a Database?**

* A **Database** is a collection of structured data stored electronically.
* **Purpose:** To store, retrieve, and manage data efficiently.
* **DBMS (Database Management System)**: Software that allows for the creation, management, and manipulation of databases.
* **Types of Databases**:

  * **Relational** (e.g., MySQL, PostgreSQL)
  * **NoSQL** (e.g., MongoDB, Cassandra)

#### **Slide 4: Relational Databases**

* **Relational Database**: Data is stored in **tables**.

  * Tables consist of **rows** (records) and **columns** (fields).
* **Key Concepts:**

  * **Primary Key**: A unique identifier for each row.
  * **Foreign Key**: A field that establishes a relationship between tables.
  * **Referential Integrity**: Ensures foreign keys point to valid records in the referenced table.

---

### **Session 2: Data Modeling & ER Diagrams**

#### **Slide 5: What is Data Modeling?**

* **Data Modeling**: The process of defining the structure, relationships, and constraints of data.
* **Entities**: Objects that hold data (e.g., Customer, Product).
* **Attributes**: Properties or details about entities (e.g., Name, Price).
* **Relationships**: How entities are related (e.g., Customer **buys** Product).

#### **Slide 6: ER Diagram Basics**

* **ER Diagram**: A visual representation of data models.

  * **Entities** (represented as rectangles)
  * **Attributes** (represented as ovals)
  * **Relationships** (represented as diamonds)
  * **Cardinality**: Defines the type of relationship (one-to-one, one-to-many, many-to-many)

#### **Slide 7: Cardinality of Relationships**

* **One-to-One (1:1)**: A single entity in one table relates to a single entity in another table.
* **One-to-Many (1:M)**: A single entity in one table can relate to multiple entities in another table.
* **Many-to-Many (M:N)**: Multiple entities in one table relate to multiple entities in another table (requires a junction table).

---

### **Session 3: Database Normalization**

#### **Slide 8: What is Normalization?**

* **Normalization**: The process of organizing data to reduce redundancy and dependency.

  * **Goal**: To ensure consistency and eliminate data anomalies.

#### **Slide 9: First Normal Form (1NF)**

* **1NF**: Eliminate duplicate rows and ensure each column contains atomic values (no multiple values in one column).

  * Example: A column for multiple phone numbers violates 1NF. Split it into individual phone number columns or rows.

#### **Slide 10: Second Normal Form (2NF)**

* **2NF**: Remove partial dependencies; ensure all non-key attributes are fully dependent on the primary key.

  * Example: In a table storing orders, removing fields like **Product Name** from the order table (which depends on the product ID) would bring it to 2NF.

#### **Slide 11: Third Normal Form (3NF)**

* **3NF**: Remove transitive dependencies. Non-key attributes should not depend on other non-key attributes.

  * Example: **Product Price** shouldn’t depend on **Product Category** if **Category** is not part of the primary key.

---

### **Session 4: Translating ERD to Relational Schema**

#### **Slide 12: From ER Diagram to Tables**

* **Step 1**: Convert **entities** into **tables**.
* **Step 2**: Convert **attributes** into **columns**.
* **Step 3**: Convert **relationships** into **foreign keys**.

#### **Slide 13: Writing SQL for Relational Schema**

* **CREATE TABLE**: Syntax for creating tables.

  * Example:

    ```sql
    CREATE TABLE Customers (
        CustomerID INT PRIMARY KEY,
        CustomerName VARCHAR(255),
        ContactName VARCHAR(255),
        Country VARCHAR(100)
    );
    ```

#### **Slide 14: Example: Translating ERD to Schema**

* ERD Example: Library System with Books and Authors.

  * Convert the **Books** entity to a table.
  * Convert the **Authors** entity to a table.
  * Define a **Foreign Key** relationship between Books and Authors.

---

### **Session 5: Database Design Best Practices**

#### **Slide 15: Integrity Constraints**

* **Primary Key**: Ensures each row is unique.
* **Foreign Key**: Maintains referential integrity between tables.
* **Not Null**: Ensures a field cannot have a NULL value.
* **Unique**: Ensures all values in a column are distinct.

#### **Slide 16: Indexing for Performance**

* **Indexing**: A method for optimizing the retrieval of data.

  * Index fields that are frequently used in **WHERE**, **JOIN**, or **ORDER BY** clauses.
  * Example: Indexing a **ProductID** column can speed up product searches in an e-commerce app.

---

### **Slide 17: Recap of Key Concepts**

* **Data Modeling**: Entities, attributes, relationships.
* **ER Diagrams**: Visual representation of data relationships.
* **Normalization**: Eliminate redundancy and ensure data integrity.
* **Translating ERDs**: From ER diagram to relational schema.
* **Design Best Practices**: Integrity constraints, indexing.

---

### **Slide 18: What’s Coming Next (Day 2)**

* **Session 1:** Advanced Normalization (4NF, 5NF)
* **Session 2:** NoSQL Design Principles
* **Session 3:** SQL Query Optimization
* **Final Project:** Real-world database design and implementation

---

### **Slide 19: Questions?**

* **Q&A**: Open the floor for any questions or clarifications.
* **Contact Information**: Provide instructor email or support info if needed.

---

### **Slide 20: Thank You!**

* **Reminder:** Review course materials, practice SQL queries, and prepare for Day 2.

---
