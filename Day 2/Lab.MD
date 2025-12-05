# **Day 2 Lab: Advanced Database Design & Optimization**

---

### **Lab Overview:**

This lab will challenge you to apply advanced database design techniques, optimize queries, handle transactions, and explore the differences between SQL and NoSQL databases. You will work with sample databases, perform practical exercises, and make design decisions based on real-world use cases.

### **Objectives:**

By the end of this lab, you should be able to:

1. Normalize a complex schema to **BCNF, 4NF, and 5NF**.
2. Create **indexes** and optimize **SQL queries** for performance.
3. Demonstrate the use of **transactions** with ACID properties.
4. Compare and contrast **SQL** and **NoSQL** databases by designing schemas and performing CRUD operations.

---

### **Lab Part 1: Advanced Normalization**

**Task 1**: **Normalize the Following Table**
The table below contains information about a customer, their orders, and the products in those orders. The data is denormalized and violates several normalization rules.

**Customer Orders Table** (Unnormalized)

| CustomerID | CustomerName | OrderID | OrderDate  | ProductID | ProductName | Quantity | Price |
| ---------- | ------------ | ------- | ---------- | --------- | ----------- | -------- | ----- |
| 1001       | Alice        | 1       | 2023-11-01 | P001      | Laptop      | 2        | 1500  |
| 1001       | Alice        | 1       | 2023-11-01 | P002      | Mouse       | 1        | 25    |
| 1002       | Bob          | 2       | 2023-11-03 | P003      | Keyboard    | 1        | 100   |
| 1003       | Charlie      | 3       | 2023-11-05 | P001      | Laptop      | 1        | 1500  |

**Instructions**:

1. **Step 1**: Convert this table to **1NF** (remove repeating groups and ensure all values are atomic).
2. **Step 2**: Convert to **2NF** (eliminate partial dependencies).
3. **Step 3**: Convert to **3NF** (eliminate transitive dependencies).
4. **Step 4**: Normalize to **BCNF**, **4NF**, and **5NF**.

**Deliverables**:

* Submit the final normalized tables (BCNF, 4NF, and 5NF) with explanations for the steps you took.

---

### **Lab Part 2: Indexing & Query Optimization**

**Task 2**: **Optimize the Following Query Using Indexes**
You are given a table that stores information about products in an online store. Write SQL queries and use indexing to improve the performance of common queries.

**Products Table**:

| ProductID | ProductName | Category    | Price | StockQuantity |
| --------- | ----------- | ----------- | ----- | ------------- |
| P001      | Laptop      | Electronics | 1500  | 50            |
| P002      | Mouse       | Accessories | 25    | 200           |
| P003      | Keyboard    | Electronics | 100   | 100           |
| P004      | Desk Chair  | Furniture   | 200   | 30            |
| P005      | Monitor     | Electronics | 300   | 40            |

**Queries to Optimize**:

1. **Query 1**: Find all **Electronics** products with a price greater than 500.

   ```sql
   SELECT ProductName, Price FROM Products WHERE Category = 'Electronics' AND Price > 500;
   ```

2. **Query 2**: Get the **total stock quantity** for each product category.

   ```sql
   SELECT Category, SUM(StockQuantity) FROM Products GROUP BY Category;
   ```

**Instructions**:

1. **Step 1**: Create an index on the `Category` and `Price` columns to improve the performance of **Query 1**.
2. **Step 2**: Create a composite index to speed up **Query 2**, which groups by the `Category` column.
3. **Step 3**: Use the `EXPLAIN` command to compare the query execution plans before and after adding indexes. Provide a performance analysis.

**Deliverables**:

* SQL queries for creating indexes.
* Execution plan analysis with and without indexes.
* Performance improvements based on query time comparisons.

---

### **Lab Part 3: Transactions & ACID Properties**

**Task 3**: **Simulate a Banking Transaction System**
You are managing a banking system where users can transfer funds between accounts. Implement a system to simulate transactions and ensure the ACID properties.

**Accounts Table**:

| AccountID | AccountName | Balance |
| --------- | ----------- | ------- |
| A001      | Alice       | 5000    |
| A002      | Bob         | 3000    |
| A003      | Charlie     | 7000    |

**Instructions**:

1. **Step 1**: Create a transaction system to transfer money from one account to another, ensuring that both **withdrawal** and **deposit** operations are included in the transaction.

   * Example: Alice transfers 1000 to Bob.
   * SQL commands should use `BEGIN`, `COMMIT`, and `ROLLBACK`.

2. **Step 2**: Simulate a failure in the middle of the transaction (e.g., a network failure) and use **ROLLBACK** to restore the data to its previous state.

3. **Step 3**: Implement **SAVEPOINT** to allow partial rollback in the case of an error.

**Deliverables**:

* SQL code for transaction handling (with `BEGIN`, `COMMIT`, `ROLLBACK`, `SAVEPOINT`).
* Demonstration of a failed transaction and how the system recovers.

---

### **Lab Part 4: NoSQL Databases**

**Task 4**: **Explore NoSQL (MongoDB)**
Now, switch gears and explore how NoSQL databases differ from SQL databases. Use **MongoDB** to perform basic CRUD operations on a collection of documents.

**Instructions**:

1. **Step 1**: Create a **MongoDB** collection called `products` with documents representing items in an online store. Each document should include `productName`, `category`, `price`, and `stockQuantity`.

2. **Step 2**: Perform the following CRUD operations:

   * **Create**: Insert a new product into the `products` collection.
   * **Read**: Retrieve all products with a `price` greater than 200.
   * **Update**: Update the price of a product.
   * **Delete**: Delete a product by `productID`.

3. **Step 3**: Compare the data model in MongoDB with the **Products** table from the relational database. Discuss the pros and cons of using MongoDB for this scenario.

**Deliverables**:

* MongoDB commands for creating, reading, updating, and deleting documents.
* A short report comparing the NoSQL schema with the SQL schema.

---

### **Final Assessment**:

Once you've completed the tasks, you will be required to submit:

1. The normalized tables from **Lab Part 1**.
2. The indexing queries and performance analysis from **Lab Part 2**.
3. The SQL transaction handling code from **Lab Part 3**.
4. The MongoDB CRUD operations and comparison report from **Lab Part 4**.

---

### **Lab Submission:**

Submit the following items for assessment:

1. **Normalized Tables** (from Part 1)
2. **SQL Indexing Queries** (from Part 2)
3. **Transaction Handling SQL Scripts** (from Part 3)
4. **MongoDB CRUD Operations** and **NoSQL Report** (from Part 4)

### **Resources Needed:**

* A relational database system (e.g., **MySQL**, **PostgreSQL**).
* A **MongoDB** instance (local or cloud-based, such as MongoDB Atlas).
* SQL query editor (e.g., MySQL Workbench, pgAdmin).

---

This **Day 2 Lab** combines theory with practical exercises, allowing learners to deepen their understanding of database design and optimization techniques through hands-on activities. 