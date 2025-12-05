# **Day 2 Quiz: Advanced Database Design & Optimization**

---

### **Part 1: Multiple Choice Questions (MCQs)**

#### **1. Which of the following statements is true about Boyce-Codd Normal Form (BCNF)?**

A. Every attribute in a table must be a key.
B. Every determinant in a table must be a candidate key.
C. Every non-prime attribute must depend on the primary key.
D. A table in BCNF must have no composite keys.

**Answer**: B. Every determinant in a table must be a candidate key.

#### **2. What is the main goal of indexing in a database?**

A. To reduce the size of the database.
B. To speed up query performance.
C. To enforce data integrity.
D. To normalize the database schema.

**Answer**: B. To speed up query performance.

#### **3. Which of the following isolation levels allows for dirty reads in a database transaction?**

A. Read Uncommitted
B. Repeatable Read
C. Serializable
D. Read Committed

**Answer**: A. Read Uncommitted

#### **4. In which of the following scenarios is a NoSQL database more appropriate than an SQL database?**

A. When you need to store data in highly structured tables with relationships.
B. When you need to perform complex joins and transactions.
C. When the data schema is flexible and you require horizontal scalability.
D. When you require strong consistency across all data.

**Answer**: C. When the data schema is flexible and you require horizontal scalability.

#### **5. What is the primary difference between a clustered index and a non-clustered index?**

A. A clustered index determines the physical order of data rows in the table.
B. A clustered index can be created on multiple columns.
C. A non-clustered index modifies the actual data stored in the table.
D. A non-clustered index stores data directly in the index itself.

**Answer**: A. A clustered index determines the physical order of data rows in the table.

#### **6. Which of the following is **not** a characteristic of an ACID-compliant database?**

A. Atomicity
B. Durability
C. Partition tolerance
D. Consistency

**Answer**: C. Partition tolerance (this is part of the CAP theorem, not ACID).

---

### **Part 2: True/False Questions**

#### **7. A table in 4NF must eliminate multi-valued dependencies.**

* **True**
* **False**

**Answer**: **True**

#### **8. A composite index is an index that is created on multiple columns.**

* **True**
* **False**

**Answer**: **True**

#### **9. In SQL transactions, the `ROLLBACK` command is used to permanently commit changes to the database.**

* **True**
* **False**

**Answer**: **False** (The `ROLLBACK` command undoes changes, while `COMMIT` is used to permanently apply them).

#### **10. Denormalization is the process of making the database schema less normalized to improve performance.**

* **True**
* **False**

**Answer**: **True**

#### **11. NoSQL databases use a schema-less data model, meaning they do not require a fixed schema before storing data.**

* **True**
* **False**

**Answer**: **True**

---

### **Part 3: Short Answer Questions**

#### **12. Explain the concept of "Atomicity" in the context of database transactions.**

**Answer**:
Atomicity means that a transaction in a database must be treated as a single unit of work, which either fully completes or fully fails. If any part of the transaction fails, the entire transaction is rolled back, ensuring that the database remains in a consistent state.

#### **13. What is the purpose of a "Composite Index"? When should it be used?**

**Answer**:
A composite index is an index that includes multiple columns. It is used when queries often filter or sort data based on several columns together. By indexing multiple columns, it allows the database to efficiently handle queries that involve these columns simultaneously, improving performance.

#### **14. What is a "multi-valued dependency," and why is it problematic in database design?**

**Answer**:
A multi-valued dependency occurs when one attribute determines multiple independent attributes in a relation. It is problematic because it leads to redundancy in the database, which can cause anomalies when updating, deleting, or inserting data. To eliminate multi-valued dependencies, a table should be in **4NF**.

#### **15. What is the difference between **SQL** and **NoSQL** databases, and when would you choose one over the other?**

**Answer**:

* **SQL databases** are relational databases that use structured schemas and support **ACID** transactions. They are ideal for applications with structured data and complex relationships.
* **NoSQL databases** are non-relational and flexible, often schema-less, and provide horizontal scalability. They are better for unstructured or semi-structured data and applications that require high scalability and performance.

**Choose SQL** when data is structured and needs complex querying and **ACID** compliance.
**Choose NoSQL** when data is unstructured, scalability is a priority, or a flexible schema is needed.

---

### **Part 4: Practical SQL Query**

#### **16. Given the following Products table, write an SQL query to find the total stock quantity for each product category.**

**Products Table**:

| ProductID | ProductName | Category    | StockQuantity |
| --------- | ----------- | ----------- | ------------- |
| P001      | Laptop      | Electronics | 50            |
| P002      | Mouse       | Accessories | 200           |
| P003      | Keyboard    | Electronics | 100           |
| P004      | Desk Chair  | Furniture   | 30            |
| P005      | Monitor     | Electronics | 40            |

**Answer**:

```sql
SELECT Category, SUM(StockQuantity) AS TotalStock
FROM Products
GROUP BY Category;
```

---

### **Part 5: Scenario-Based Question**

#### **17. You have a database that tracks user orders. The table below is denormalized with order details repeated for each product. Normalize this table to **3NF**.

**Order Details Table (Denormalized)**:

| OrderID | CustomerID | ProductID | ProductName | Quantity | Price | CustomerName |
| ------- | ---------- | --------- | ----------- | -------- | ----- | ------------ |
| 101     | 1001       | P001      | Laptop      | 1        | 1000  | Alice        |
| 101     | 1001       | P002      | Mouse       | 2        | 25    | Alice        |
| 102     | 1002       | P003      | Keyboard    | 1        | 150   | Bob          |
| 103     | 1003       | P001      | Laptop      | 1        | 1000  | Charlie      |

**Answer**:
Step 1: **1NF** - Remove repeating groups and ensure all columns have atomic values.

Step 2: **2NF** - Remove partial dependencies. Separate Customer and Order information into two tables: `Customers` and `Orders`.

Step 3: **3NF** - Remove transitive dependencies. Create a `Products` table to separate product details from orders.

**Normalized Tables**:

1. **Customers**:

   | CustomerID | CustomerName |
   | ---------- | ------------ |
   | 1001       | Alice        |
   | 1002       | Bob          |
   | 1003       | Charlie      |

2. **Orders**:

   | OrderID | CustomerID |
   | ------- | ---------- |
   | 101     | 1001       |
   | 102     | 1002       |
   | 103     | 1003       |

3. **Products**:

   | ProductID | ProductName | Price |
   | --------- | ----------- | ----- |
   | P001      | Laptop      | 1000  |
   | P002      | Mouse       | 25    |
   | P003      | Keyboard    | 150   |

4. **OrderDetails**:

   | OrderID | ProductID | Quantity |
   | ------- | --------- | -------- |
   | 101     | P001      | 1        |
   | 101     | P002      | 2        |
   | 102     | P003      | 1        |
   | 103     | P001      | 1        |

---

### **Quiz Scoring Guidelines**:

* **Multiple Choice & True/False**: 1 point each.
* **Short Answer**: 2-3 points each based on the completeness and correctness of the answer.
* **Practical SQL Query**: 5 points for a correct query and explanation.
* **Scenario-Based Normalization**: 5-10 points based on the normalization process and final tables.

---

This **Day 2 Quiz** covers all the key topics from the day’s lesson plan, allowing you to assess learners' understanding of complex database design concepts and practical skills. 