### **Day 1 Lesson Plan: Fundamentals and Relational Design**

---

#### **Objective for Day 1:**

By the end of Day 1, students will:

* Understand the basic concepts of databases and relational databases.
* Be able to create Entity-Relationship (ER) diagrams.
* Know how to normalize data and apply normalization techniques (1NF, 2NF, 3NF).
* Be able to translate ER diagrams into relational schemas and implement them in SQL.

---

### **Session 1: Introduction to Databases (1 hour)**

**Objective:**
Introduce basic database concepts, focusing on relational databases and key terminologies such as tables, rows, columns, primary keys, and foreign keys.

#### **Agenda:**

* **What is a Database? (15 min)**

  * Discuss the purpose of a database.
  * Introduction to types of databases (Relational vs. NoSQL).
* **Relational Databases (30 min)**

  * Definition of relational databases and key concepts: **tables**, **rows** (records), **columns** (fields).
  * **Primary Key**: Uniquely identifies each row.
  * **Foreign Key**: Links tables together by referencing a primary key in another table.
  * **Referential Integrity**: Ensures consistency between related tables.
* **Practical Activity:**

  * Quick poll/questionnaire on what students understand about databases.
  * Hands-on exercise: Identify primary and foreign keys in a simple database schema (e.g., Students and Courses).

#### **Materials Needed:**

* Presentation slides with database definitions and examples.
* Whiteboard or flipchart for quick visual explanations.

---

### **Session 2: Data Modeling & ER Diagrams (2 hours)**

**Objective:**
Teach students how to visualize a database structure through **Entity-Relationship (ER) Diagrams**.

#### **Agenda:**

* **Introduction to Data Modeling (30 min)**

  * **Entities**: Represent real-world objects like `Customer`, `Product`.
  * **Attributes**: Properties of entities like `Customer Name`, `Product Price`.
  * **Relationships**: How entities are related (e.g., Customer **buys** Product).

* **Cardinality of Relationships (15 min)**

  * **One-to-One (1:1)**
  * **One-to-Many (1:M)**
  * **Many-to-Many (M:N)** and how to handle them with junction tables.

* **Drawing ER Diagrams (45 min)**

  * Demonstrate how to draw ER diagrams: use of rectangles for entities, ovals for attributes, and diamonds for relationships.
  * Walkthrough of creating an ER diagram for a simple example (e.g., Library System with Books and Authors).

* **Practical Activity (30 min)**

  * Students will create their own ER diagrams for a **library system** or **e-commerce website**.
  * Discuss as a group and provide feedback on their diagrams.

#### **Materials Needed:**

* ER Diagramming tool (e.g., dbdiagram.io, Lucidchart) or paper and markers for sketching.
* Sample problem statements (e.g., design an ER diagram for a library system).

---

### **Session 3: Database Normalization (2 hours)**

**Objective:**
Introduce students to **Normalization** and how it helps in reducing redundancy and improving database efficiency.

#### **Agenda:**

* **Introduction to Normalization (15 min)**

  * Discuss the need for normalization to reduce data redundancy.
  * Introduction to the first three normal forms (1NF, 2NF, and 3NF).

* **First Normal Form (1NF) (15 min)**

  * Definition: Each column must contain atomic (indivisible) values.
  * Practical example: Convert a non-normalized table into 1NF.

* **Second Normal Form (2NF) (30 min)**

  * Definition: Remove partial dependencies (non-key attributes must depend on the entire primary key).
  * Practical example: Normalize a 1NF table to 2NF.

* **Third Normal Form (3NF) (30 min)**

  * Definition: Remove transitive dependencies (non-key attributes should not depend on other non-key attributes).
  * Practical example: Normalize a 2NF table to 3NF.

* **Practical Activity (30 min)**

  * Students will be given a sample unnormalized table and asked to bring it through 1NF, 2NF, and 3NF.

#### **Materials Needed:**

* Sample non-normalized tables.
* Step-by-step handouts for 1NF, 2NF, and 3NF.
* Whiteboard or PowerPoint for showing normalization examples.

---

### **Session 4: Translating ERD to Relational Schema (2 hours)**

**Objective:**
Teach students how to convert an ER diagram into a **relational schema** (tables) and implement it using SQL.

#### **Agenda:**

* **Converting ERD to Tables (30 min)**

  * How to convert entities into tables.
  * How to convert attributes into columns.
  * Convert relationships into foreign keys.

* **SQL for Relational Schema (30 min)**

  * Introduction to SQL **CREATE TABLE** statements.
  * How to define primary and foreign keys in SQL.
  * Writing SQL queries to create tables.

* **Hands-on Exercise:**

  * Students will take the ER diagram they created earlier and write SQL `CREATE TABLE` statements.
  * Example: Writing SQL for the **Books** and **Authors** tables from the library system.

* **Discussion and Review (30 min)**:

  * Review students’ SQL code and ERD translations.
  * Discuss challenges and common mistakes.

#### **Materials Needed:**

* SQL examples for **CREATE TABLE** statements.
* A sample relational schema for practice.

---

### **Session 5: Database Design Best Practices (1 hour)**

**Objective:**
Discuss best practices in database design to ensure data integrity and performance.

#### **Agenda:**

* **Integrity Constraints (30 min)**

  * Definition of **Primary Key**, **Foreign Key**, **Not Null**, and **Unique** constraints.
  * Why integrity constraints are important.
  * How to implement these constraints in SQL.

* **Indexing for Performance (30 min)**

  * Introduction to **indexing** and its importance in optimizing query performance.
  * When to index columns in your database schema.
  * Example of creating an index in SQL.

#### **Materials Needed:**

* SQL examples with constraints and indexing.
* Discussion prompts to engage students.

---

### **Closing (15 min)**

* **Recap of Key Concepts (5 min)**

  * Quickly review the major points of the day: ERD, normalization, SQL table creation.

* **Q&A Session (10 min)**

  * Open the floor for any remaining questions or clarifications.

---

### **Homework (Optional)**:

* **Practice Exercise**: Ask students to design an ER diagram for a **student registration system** and normalize the resulting database to 3NF.
* **SQL Challenge**: Write SQL code to create tables for a small business (e.g., inventory system).

---

### **Materials Needed for the Entire Day:**

* Laptop/computer with SQL database installed (MySQL, PostgreSQL, or SQLite).
* Whiteboard, markers, or presentation software.
* ER Diagram tool (optional) for practical exercises.

---

### **End of Day 1**

This lesson plan is structured to provide a balance of **lecture**, **practical activities**, and **group discussion**, ensuring that students have a strong grasp of database design principles by the end of Day 1. The goal is to keep sessions interactive, providing hands-on practice as much as possible.

