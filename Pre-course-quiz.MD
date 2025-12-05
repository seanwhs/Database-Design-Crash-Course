# **Pre-Course Quiz: Database Design Fundamentals**

---

### **Part 1: Multiple Choice Questions (MCQs)**

#### **1. What is a relational database?**

A. A database that stores data as files in a hierarchical structure.
B. A database that stores data in tables with relationships between them.
C. A database that stores data as key-value pairs.
D. A database that uses graphs to represent data.

**Answer**: B. A database that stores data in tables with relationships between them.

#### **2. What does "normalization" in database design aim to achieve?**

A. Reduce data redundancy and improve data integrity.
B. Increase the speed of data retrieval.
C. Ensure that data is stored in a denormalized form.
D. Minimize the number of indexes on a table.

**Answer**: A. Reduce data redundancy and improve data integrity.

#### **3. Which of the following SQL clauses is used to filter records in a query?**

A. `GROUP BY`
B. `ORDER BY`
C. `HAVING`
D. `WHERE`

**Answer**: D. `WHERE`

#### **4. What is a primary key in a relational database?**

A. A field that is used to uniquely identify each record in a table.
B. A field that ensures no two records in a table are the same.
C. A field that is used to establish relationships between tables.
D. A field that is indexed for faster query performance.

**Answer**: A. A field that is used to uniquely identify each record in a table.

#### **5. Which of the following is **not** a type of relationship in a relational database?**

A. One-to-one
B. One-to-many
C. Many-to-many
D. Key-to-value

**Answer**: D. Key-to-value

#### **6. What does the term "ACID" refer to in database transactions?**

A. A method for reducing data storage space.
B. A set of properties ensuring reliable transaction processing.
C. A database normalization technique.
D. A way of compressing data for faster retrieval.

**Answer**: B. A set of properties ensuring reliable transaction processing.

#### **7. Which SQL command is used to retrieve data from a database?**

A. `INSERT`
B. `UPDATE`
C. `SELECT`
D. `DELETE`

**Answer**: C. `SELECT`

#### **8. What is the purpose of an index in a database?**

A. To ensure data consistency across tables.
B. To speed up data retrieval operations.
C. To store backup copies of the database.
D. To enforce referential integrity.

**Answer**: B. To speed up data retrieval operations.

---

### **Part 2: True/False Questions**

#### **9. A foreign key is used to enforce a relationship between two tables.**

* **True**
* **False**

**Answer**: **True**

#### **10. In a relational database, tables should be designed with as many columns as possible to store data efficiently.**

* **True**
* **False**

**Answer**: **False** (This would likely lead to data redundancy and integrity issues. Tables should be designed with normalized structures.)

#### **11. The `GROUP BY` clause in SQL is used to filter records based on certain conditions.**

* **True**
* **False**

**Answer**: **False** (The `GROUP BY` clause is used to group rows that have the same values in specified columns. To filter records, you use `WHERE` or `HAVING`.)

#### **12. A table in 3NF (Third Normal Form) must not have any transitive dependencies.**

* **True**
* **False**

**Answer**: **True**

#### **13. NoSQL databases are better suited for applications that require complex queries and strong consistency.**

* **True**
* **False**

**Answer**: **False** (NoSQL databases are often used for flexibility, scalability, and performance with unstructured data, while SQL databases are typically better for complex queries and strong consistency.)

---

### **Part 3: Short Answer Questions**

#### **14. What is the difference between a **primary key** and a **foreign key** in relational databases?**

**Answer**:

* **Primary Key**: A field or set of fields that uniquely identifies each record in a table. It cannot have `NULL` values and must be unique.
* **Foreign Key**: A field or set of fields in one table that links to the **primary key** of another table, establishing a relationship between the two tables.

#### **15. What is a **many-to-many** relationship in a relational database, and how is it typically implemented?**

**Answer**:
A **many-to-many** relationship occurs when multiple records in one table are associated with multiple records in another table. It is typically implemented using a **junction table** that contains foreign keys from both tables, linking them together.

#### **16. What is the purpose of **referential integrity** in a relational database?**

**Answer**:
Referential integrity ensures that relationships between tables remain consistent. It guarantees that foreign keys point to valid records in the related tables, preventing orphaned records or invalid references.

---

### **Part 4: Scenario-Based Question**

#### **17. You have a `Customers` table and an `Orders` table. Each customer can have multiple orders. How would you establish a relationship between these two tables?**

**Answer**:
To establish a relationship between the `Customers` and `Orders` tables, we would use a **foreign key**. The `Orders` table would have a field, such as `CustomerID`, that references the primary key `CustomerID` from the `Customers` table. This would create a **one-to-many** relationship, where each customer can have multiple orders, but each order is associated with only one customer.

---

### **Quiz Scoring Guidelines**:

* **MCQs**: 1 point each.
* **True/False**: 1 point each.
* **Short Answer**: 2-3 points each based on correctness and clarity of the answer.
* **Scenario-Based**: 3-5 points based on the depth and clarity of the explanation.

---

This **Pre-Course Quiz** will help you evaluate the learners' baseline knowledge of basic database concepts, so you can adjust your lessons accordingly and address any gaps in understanding before diving into more advanced topics. 