# **Post-Course Assessment: Advanced Database Design & Optimization**

---

### **Part 1: Multiple Choice Questions (MCQs)**

#### **1. Which of the following is a key advantage of using **BCNF** over **3NF**?**

A. BCNF reduces redundancy by eliminating partial dependencies.
B. BCNF ensures that every determinant is a candidate key, even in cases where 3NF allows non-candidate key dependencies.
C. BCNF removes transitive dependencies between non-key attributes.
D. BCNF requires fewer tables than 3NF.

**Answer**: B. BCNF ensures that every determinant is a candidate key, even in cases where 3NF allows non-candidate key dependencies.

#### **2. Which of the following SQL commands is used to undo the effects of a transaction before it is committed?**

A. `COMMIT`
B. `ROLLBACK`
C. `SAVEPOINT`
D. `UNDO`

**Answer**: B. `ROLLBACK`

#### **3. What does the **isolation** property of a transaction guarantee?**

A. Transactions are permanent once committed.
B. Transactions do not interfere with each other and execute independently.
C. Transactions are executed in the same order they are received.
D. Transactions will be automatically rolled back if there is a failure.

**Answer**: B. Transactions do not interfere with each other and execute independently.

#### **4. In a **many-to-many** relationship between two tables, what is typically used to implement the relationship?**

A. A foreign key in one of the tables
B. A new composite key in both tables
C. A junction table that holds foreign keys from both tables
D. A primary key in the relationship table

**Answer**: C. A junction table that holds foreign keys from both tables

#### **5. Which of the following is **not** a typical use case for **NoSQL** databases?**

A. Storing large amounts of unstructured or semi-structured data
B. Handling high-throughput data with horizontal scalability
C. Maintaining strong consistency for relational data
D. Using flexible schema models for rapidly evolving applications

**Answer**: C. Maintaining strong consistency for relational data

#### **6. Which of the following is **not** a valid type of index in a relational database?**

A. Clustered Index
B. Non-Clustered Index
C. Composite Index
D. Dynamic Index

**Answer**: D. Dynamic Index

---

### **Part 2: True/False Questions**

#### **7. The purpose of normalization is to minimize the number of tables in a database design.**

* **True**
* **False**

**Answer**: **False** (Normalization is about reducing redundancy and ensuring data integrity, not necessarily minimizing the number of tables.)

#### **8. A non-clustered index creates a separate structure from the table and contains pointers to the data rows.**

* **True**
* **False**

**Answer**: **True**

#### **9. In a transaction, the **COMMIT** command ensures that all changes made during the transaction are saved permanently in the database.**

* **True**
* **False**

**Answer**: **True**

#### **10. In **4NF**, a table should not have multi-valued dependencies, and these can be removed through decomposition.**

* **True**
* **False**

**Answer**: **True**

#### **11. A NoSQL database can only handle key-value pairs and cannot support structured data like tables and rows.**

* **True**
* **False**

**Answer**: **False** (NoSQL databases can handle multiple data models, including document-based, columnar, graph, and key-value.)

---

### **Part 3: Short Answer Questions**

#### **12. Explain the difference between a **clustered index** and a **non-clustered index** in SQL.**

**Answer**:

* **Clustered Index**: Determines the physical order of the data rows in the table. A table can have only one clustered index because data rows can only be stored in one order. The data is organized according to the indexed column(s).
* **Non-Clustered Index**: Does not alter the physical order of the data rows but creates a separate structure with pointers to the actual data. A table can have multiple non-clustered indexes.

#### **13. What is the role of a **foreign key** in database relationships, and how does it help enforce referential integrity?**

**Answer**:
A **foreign key** is a column or set of columns in one table that uniquely identifies a row in another table. It establishes a relationship between the two tables and helps enforce **referential integrity** by ensuring that the value in the foreign key column(s) matches a primary key value in the related table or is `NULL`.

#### **14. Describe the **ACID** properties of database transactions and why they are important.**

**Answer**:

* **Atomicity**: Ensures that a transaction is treated as a single unit, meaning it either completes fully or does not happen at all.
* **Consistency**: Ensures that a transaction brings the database from one valid state to another, maintaining data integrity.
* **Isolation**: Ensures that concurrent transactions do not interfere with each other and are executed independently.
* **Durability**: Ensures that once a transaction is committed, its changes are permanent, even in the event of a system crash.

These properties are important for maintaining data integrity, reliability, and consistency in the database, particularly in multi-user environments.

#### **15. What is **denormalization**, and when might it be used in database design?**

**Answer**:
**Denormalization** is the process of combining tables or reducing the level of normalization to improve query performance. It involves intentionally introducing redundancy into the database to make read operations faster by reducing the need for joins. Denormalization is often used when performance is prioritized over data integrity, especially in read-heavy applications.

---

### **Part 4: Practical SQL Query**

#### **16. Given the following schema for an e-commerce application:

* **Customers**: (CustomerID, CustomerName)
* **Orders**: (OrderID, CustomerID, OrderDate)
* **Products**: (ProductID, ProductName, Price)
* **OrderDetails**: (OrderID, ProductID, Quantity)

Write a query to retrieve the **total price** of each order, including the customer's name and the total quantity of products ordered.**

**Answer**:

```sql
SELECT 
    c.CustomerName, 
    o.OrderID, 
    SUM(od.Quantity * p.Price) AS TotalPrice,
    SUM(od.Quantity) AS TotalQuantity
FROM 
    Customers c
JOIN 
    Orders o ON c.CustomerID = o.CustomerID
JOIN 
    OrderDetails od ON o.OrderID = od.OrderID
JOIN 
    Products p ON od.ProductID = p.ProductID
GROUP BY 
    c.CustomerName, o.OrderID;
```

---

### **Part 5: Scenario-Based Question**

#### **17. You are tasked with designing a database for an online bookstore. The store needs to store information about books, authors, and customers. Each book can have multiple authors, and each author can write multiple books. Customers can place multiple orders, and each order can contain multiple books. Describe the tables and relationships you would use to model this scenario.**

**Answer**:

* **Books** table: Stores information about each book (BookID, BookTitle, ISBN, etc.).
* **Authors** table: Stores information about each author (AuthorID, AuthorName, etc.).
* **Customers** table: Stores information about customers (CustomerID, CustomerName, Email, etc.).
* **Orders** table: Stores information about customer orders (OrderID, CustomerID, OrderDate).
* **OrderDetails** table: A junction table to represent which books are in which orders (OrderID, BookID, Quantity, Price).
* **AuthorBooks** table: A junction table to represent the many-to-many relationship between authors and books (AuthorID, BookID).

**Relationships**:

* **Books ↔ Authors**: Many-to-many relationship (via **AuthorBooks** table).
* **Books ↔ Orders**: Many-to-many relationship (via **OrderDetails** table).
* **Customers ↔ Orders**: One-to-many relationship (one customer can place multiple orders).

---

### **Quiz Scoring Guidelines**:

* **MCQs**: 1 point each.
* **True/False**: 1 point each.
* **Short Answer**: 2-3 points each based on the correctness and depth of the answer.
* **Practical SQL Query**: 5 points for correct query structure and logic.
* **Scenario-Based Question**: 5-10 points based on the completeness and accuracy of the database design.

---

This **Post-Course Assessment** will help you evaluate how well the learners have grasped the concepts taught during the course, including both theoretical knowledge and practical application skills.