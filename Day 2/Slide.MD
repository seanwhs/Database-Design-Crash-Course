## **Day 2: Advanced Database Design & Optimization**

---

### **Slide 1: Title Slide**

* **Title**: Day 2: Advanced Database Design and Optimization
* **Subtitle**: Exploring Advanced Normalization, Query Optimization, and Best Practices
* **Your Name**
* **Course Date**

---

### **Slide 2: Learning Outcomes for Day 2**

* By the end of today, you will:

  * Master **Advanced Normalization** (BCNF, 4NF, and 5NF)
  * Understand **Indexing** and **Query Optimization**
  * Learn about **ACID Transactions** and their importance in databases
  * Explore the world of **NoSQL Databases**
  * Follow **Database Design Best Practices** for scalability and performance

---

### **Slide 3: Session Overview**

* **1. Advanced Normalization (2 hours)**
* **2. Indexing & Query Optimization (2 hours)**
* **3. Transactions and ACID Properties (1.5 hours)**
* **4. NoSQL Databases (1.5 hours)**
* **5. Database Design Best Practices (1 hour)**

---

## **Session 1: Advanced Normalization (BCNF, 4NF, 5NF)**

---

### **Slide 4: Why Do We Normalize?**

* Eliminate redundancy
* Ensure data consistency
* Improve query performance
* Prevent update anomalies

---

### **Slide 5: Boyce-Codd Normal Form (BCNF)**

* **Definition**: Every determinant must be a candidate key.
* **Why BCNF?**: Eliminate anomalies that can exist in 3NF.
* **Example**:

  * If a table contains non-prime attributes that depend on part of a composite key, it's not in BCNF.
* **Solution**: Split the table into two smaller ones to ensure that each determinant is a candidate key.

---

### **Slide 6: Fourth Normal Form (4NF)**

* **Definition**: Eliminate multi-valued dependencies.
* **Example**:

  * A table that contains multiple independent sets of attributes for the same entity violates 4NF.
  * Solution: Separate the attributes into different tables to remove multi-valued dependencies.

---

### **Slide 7: Fifth Normal Form (5NF)**

* **Definition**: Eliminate join dependencies and ensure no loss of information.
* **Example**:

  * A table containing information that can be reconstructed from several smaller tables should be split.
* **Solution**: Split the table so that data can be safely reconstructed using joins.

---

### **Slide 8: Advanced Normalization Summary**

* **1NF**: Eliminate repeating groups.
* **2NF**: Remove partial dependencies.
* **3NF**: Eliminate transitive dependencies.
* **BCNF**: Every determinant is a candidate key.
* **4NF**: Eliminate multi-valued dependencies.
* **5NF**: Eliminate join dependencies.

---

## **Session 2: Indexing & Query Optimization**

---

### **Slide 9: Introduction to Indexing**

* **What is an Index?**

  * A data structure that improves query speed.
* **Why Use Indexes?**

  * Speeds up search queries by allowing quick lookups.
  * Improves **SELECT** query performance, but can slow down **INSERT**, **UPDATE**, and **DELETE** operations.

---

### **Slide 10: Types of Indexes**

* **Primary Index**: Unique index on the primary key.
* **Unique Index**: Ensures all values are unique in a column.
* **Composite Index**: An index on multiple columns.
* **Full-Text Index**: Used for text searching.
* **Clustered vs Non-Clustered Index**:

  * Clustered: Data is stored in order of the index.
  * Non-clustered: Data is stored separately from the index.

---

### **Slide 11: Query Optimization**

* **Query Execution Plans**: Visual representation of how the database executes queries.
* **Optimizing Queries**:

  * Use **EXPLAIN** to analyze query execution.
  * Ensure proper use of indexes.
  * Avoid **SELECT *** (select only necessary columns).
  * Optimize **JOINs** and **WHERE** clauses.

---

### **Slide 12: Trade-offs of Indexing**

* **Advantages**:

  * Faster query performance (especially SELECT queries).
  * Efficient lookups.
* **Disadvantages**:

  * Slower write operations (INSERT, UPDATE, DELETE).
  * Increased storage space.

---

## **Session 3: Transactions and ACID Properties**

---

### **Slide 13: What is a Database Transaction?**

* A **transaction** is a sequence of one or more operations executed as a single unit.
* **ACID Properties** ensure that transactions are processed reliably.

---

### **Slide 14: ACID Properties**

* **Atomicity**: All or nothing – either the transaction is fully completed, or none of the changes are saved.
* **Consistency**: The database must remain in a valid state before and after the transaction.
* **Isolation**: Transactions must not interfere with each other.
* **Durability**: Once a transaction is committed, its effects are permanent, even if the system crashes.

---

### **Slide 15: SQL Transactions**

* **BEGIN TRANSACTION**: Starts a new transaction.
* **COMMIT**: Saves changes made during the transaction.
* **ROLLBACK**: Reverts changes made during the transaction.
* **SAVEPOINT**: Sets a point within a transaction to roll back to if needed.

---

## **Session 4: NoSQL Databases**

---

### **Slide 16: What is NoSQL?**

* **NoSQL** stands for “Not Only SQL” and refers to a broad category of databases that don’t use traditional relational models.
* Types of NoSQL Databases:

  * **Document-based**: MongoDB, CouchDB
  * **Key-Value Stores**: Redis, DynamoDB
  * **Column-family Stores**: Cassandra, HBase
  * **Graph Databases**: Neo4j, Amazon Neptune

---

### **Slide 17: SQL vs. NoSQL**

* **SQL**:

  * Structured schema.
  * Supports **ACID** transactions.
  * **Vertical scaling** (adding resources to a single server).
* **NoSQL**:

  * Schema-less or flexible schema.
  * Optimized for **horizontal scaling** (distributing load across many servers).
  * Often better for unstructured or semi-structured data.

---

### **Slide 18: When to Use NoSQL**

* High-velocity, large-scale data (e.g., real-time analytics).
* Flexible schema requirements.
* Applications with complex, evolving data structures (e.g., social networks, IoT data).

---

## **Session 5: Database Design Best Practices**

---

### **Slide 19: Design Principles**

* **Scalability**: Design databases that can handle increased data volume.
* **Maintainability**: Keep the design simple and modular.
* **Consistency**: Ensure data consistency through **constraints** and **validation** rules.
* **Performance**: Optimize queries and indexes for speed.

---

### **Slide 20: Data Integrity**

* Use **PRIMARY KEY**, **FOREIGN KEY**, and **UNIQUE** constraints to maintain data integrity.
* Avoid **NULL** values when possible.
* Ensure proper **normalization** and **denormalization** when appropriate.

---

### **Slide 21: Optimizing for Performance**

* **Denormalization**: Sometimes, a **denormalized** structure may improve read performance.
* **Partitioning**: Split large tables into smaller, more manageable pieces.
* **Sharding**: Distribute data across multiple servers.

---

### **Slide 22: Database Design Best Practices Summary**

* **Modular Design**: Split the database into logical modules for easier maintenance.
* **Performance vs. Data Integrity**: Balance between normalization and optimization.
* **Scalability**: Plan for future growth in terms of both data and traffic.

---

### **Slide 23: Lab and Final Assessment**

* **Lab Activity**: Apply advanced normalization and indexing techniques to a real-world scenario.
* **Final Assessment**: Review key concepts through a final quiz and Q&A.

---

### **Slide 24: Questions & Wrap-up**

* Open the floor for any final questions.
* Recap the main concepts covered in the course.
* **Thank You** and encourage students to continue practicing and learning about database design.

---

This **Day 2 Slide Outline** provides a structured approach to teaching advanced database design concepts, including normalization, indexing, transactions, and NoSQL databases. You can use this outline to create slides using tools like PowerPoint, Google Slides, or any other presentation software.

