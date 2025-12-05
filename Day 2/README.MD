# **Day 2 Readme: Advanced Database Design and Optimization**

---

### **Course Overview:**

Welcome to **Day 2** of the **Database Design Crash Course**! Today, we will build upon the foundational concepts learned in Day 1. We will delve into more advanced topics such as:

* **Advanced Normalization (BCNF, 4NF, and 5NF)**
* **Indexing** and **Query Optimization**
* **Database Transactions** and **ACID Properties**
* **NoSQL Databases** and the differences from relational databases
* **Database Design Best Practices**

By the end of Day 2, you’ll have a deeper understanding of database design principles and be equipped with the knowledge to optimize databases for performance and scalability.

---

### **Day 2 Learning Outcomes:**

After completing Day 2, you should be able to:

1. **Normalize a database** to **Boyce-Codd Normal Form (BCNF)**, **4NF**, and **5NF**.
2. **Design efficient indexes** to optimize database queries and improve performance.
3. Understand and apply the concepts of **ACID Transactions** in relational databases.
4. Recognize the differences between **SQL** and **NoSQL** databases and when to use each.
5. Follow **database design best practices** for scalability, maintainability, and performance.

---

### **Day 2 Schedule and Key Topics:**

---

#### **Session 1: Advanced Normalization (2 hours)**

**Key Topics:**

* **Boyce-Codd Normal Form (BCNF)**:

  * Definition and how it differs from 3NF.
  * Eliminate functional dependencies that violate BCNF.
* **Fourth Normal Form (4NF)**:

  * Eliminate multi-valued dependencies.
  * Example and applications of 4NF.
* **Fifth Normal Form (5NF)**:

  * Eliminate join dependencies and ensure that no data is lost during joins.
  * Practical applications of 5NF.

**Learning Goals:**

* Understand how to apply BCNF, 4NF, and 5NF to design more efficient and scalable databases.
* Work with more complex normalization problems to ensure minimal redundancy and data anomalies.

---

#### **Session 2: Indexing & Query Optimization (2 hours)**

**Key Topics:**

* **Indexes**:

  * Types of indexes (Primary, Unique, Composite, Full-Text, etc.).
  * **How indexing improves query performance**.
  * **Trade-offs** of indexing and when not to use indexes.
* **Query Optimization**:

  * Understanding query execution plans.
  * Analyzing and optimizing SQL queries using indexing, joins, and subqueries.

**Learning Goals:**

* Learn how to create and manage indexes to optimize read-heavy queries.
* Understand query optimization strategies for faster data retrieval.

---

#### **Session 3: Transactions and ACID Properties (1.5 hours)**

**Key Topics:**

* **Database Transactions**:

  * What is a transaction? A sequence of operations performed as a single unit.
  * **ACID Properties**: Atomicity, Consistency, Isolation, Durability.
  * Handling transactions in SQL (COMMIT, ROLLBACK, SAVEPOINT).
* **Concurrency Control**:

  * Ensuring data consistency when multiple transactions are executed concurrently.

**Learning Goals:**

* Understand the importance of ACID properties to maintain data integrity.
* Learn how to use **transactions** in SQL to ensure that your operations are reliable and consistent.

---

#### **Session 4: NoSQL Databases (1.5 hours)**

**Key Topics:**

* **What is NoSQL?**:

  * Introduction to NoSQL databases and types (Document-based, Key-Value stores, Column-family stores, and Graph databases).
* **SQL vs. NoSQL**:

  * Differences in schema design, data storage, and scalability.
  * Pros and cons of NoSQL and when to use it.
* **Examples of NoSQL Databases**:

  * MongoDB (Document store), Redis (Key-Value store), Cassandra (Column-family store), and Neo4j (Graph database).

**Learning Goals:**

* Understand the key differences between relational (SQL) and non-relational (NoSQL) databases.
* Learn when to use NoSQL databases and how they are designed for scalability and flexibility.

---

#### **Session 5: Database Design Best Practices (1 hour)**

**Key Topics:**

* **Design Principles**:

  * Focus on **scalability**, **maintainability**, and **performance**.
  * **Modularization**: Organizing database schemas into logical modules.
* **Data Integrity**:

  * Enforcing consistency through constraints (e.g., primary and foreign keys).
* **Optimizing for Read and Write Performance**:

  * Balancing normalization and denormalization for performance.
  * Using **partitioning** and **sharding** to scale large databases.

**Learning Goals:**

* Learn how to follow best practices to design databases that are efficient, scalable, and easy to maintain.

---

### **Lab: Advanced Database Design & Optimization (2 hours)**

**Objective:**

* Apply the concepts learned in Day 2 to a hands-on project. Students will:

  * Normalize a complex schema to BCNF, 4NF, and 5NF.
  * Create indexes and optimize queries for a sample database.
  * Design a transaction handling system using ACID properties.
  * Compare and contrast a relational database schema with a NoSQL schema for a similar use case.

**Deliverables:**

* Submission of normalized tables for a complex schema.
* SQL code for creating indexes and optimizing queries.
* A demonstration of transaction handling with ACID principles.
* A comparison document outlining the advantages of using SQL vs. NoSQL for a specific use case.

---

### **Conclusion & Final Assessment (1 hour)**

**Objective**:

* **Review**: Recap the key concepts from Day 1 and Day 2, focusing on advanced normalization, query optimization, and database design best practices.
* **Q&A Session**: Open the floor for any final questions, clarifications, and review of the lab results.
* **Final Quiz**: To assess students' understanding of the advanced topics covered throughout the course.

---

### **Resources:**

* **Books**:

  * *Database Design for Mere Mortals* by Michael J. Hernandez (for in-depth design principles).
  * *SQL Performance Explained* by Markus Winand (for query optimization).
* **Websites**:

  * *Database Design* resources at [w3schools](https://www.w3schools.com/sql/).
  * MongoDB documentation: [https://www.mongodb.com/docs/](https://www.mongodb.com/docs/)
  * PostgreSQL documentation: [https://www.postgresql.org/docs/](https://www.postgresql.org/docs/)

---

### **Key Takeaways for Day 2:**

* **Advanced Normalization**: You will be able to normalize databases to higher normal forms (BCNF, 4NF, 5NF) to eliminate redundancy and maintain data integrity.
* **Query Optimization**: Learn to optimize queries using indexing and query planning tools.
* **Transactions and ACID**: Understand how to ensure data consistency and reliability in databases using transactions.
* **NoSQL**: Learn the strengths and weaknesses of NoSQL databases and when to use them in place of SQL databases.
* **Best Practices**: You’ll leave with a set of best practices for designing scalable, maintainable, and optimized databases.

---

### **Looking Forward to Day 2!**

Get ready to dive deeper into more advanced topics and reinforce your learning through hands-on activities. Be sure to bring your questions, as we'll be tackling more complex design challenges and optimizations!
