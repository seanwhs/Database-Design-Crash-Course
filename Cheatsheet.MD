# **Database Design Cheatsheet**

## **1. Database Design Concepts**

### **Normalization**

Normalization is the process of organizing data to minimize redundancy and improve data integrity. The most common normal forms (NF) are:

* **1NF (First Normal Form)**:

  * No repeating groups or arrays.
  * Each cell contains a single value (atomic).

* **2NF (Second Normal Form)**:

  * Meets 1NF.
  * All non-key attributes are fully functionally dependent on the primary key (no partial dependencies).

* **3NF (Third Normal Form)**:

  * Meets 2NF.
  * No transitive dependencies (non-key attributes depend on other non-key attributes).

* **BCNF (Boyce-Codd Normal Form)**:

  * Meets 3NF.
  * Every determinant is a candidate key.

* **4NF (Fourth Normal Form)**:

  * Meets BCNF.
  * No multi-valued dependencies (no attributes depend on multiple independent attributes).

* **5NF (Fifth Normal Form)**:

  * Meets 4NF.
  * No join dependencies (data should not be reconstructed by joining multiple tables).

---

## **2. SQL Basics**

### **Creating Tables**

```sql
CREATE TABLE table_name (
    column1 datatype PRIMARY KEY,
    column2 datatype,
    column3 datatype,
    ...
);
```

### **Inserting Data**

```sql
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);
```

### **Selecting Data**

```sql
SELECT column1, column2
FROM table_name
WHERE condition
ORDER BY column1;
```

### **Updating Data**

```sql
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE condition;
```

### **Deleting Data**

```sql
DELETE FROM table_name
WHERE condition;
```

---

## **3. Relationships in Database Design**

### **One-to-One (1:1)**:

* Each record in Table A is related to one record in Table B.

### **One-to-Many (1:N)**:

* One record in Table A can be associated with multiple records in Table B.
* **Example**: One customer can have multiple orders.
* Implemented using a **foreign key**.

### **Many-to-Many (M:N)**:

* Multiple records in Table A are associated with multiple records in Table B.
* Implemented using a **junction table** (also known as a **linking table**).

---

## **4. Keys and Constraints**

### **Primary Key (PK)**

* Uniquely identifies each record in a table.
* Cannot contain `NULL` values.
* There can be only one primary key in a table.

### **Foreign Key (FK)**

* A field that uniquely identifies a row in another table.
* Ensures referential integrity.

### **Unique Key**

* Ensures that all values in a column are unique, but can allow `NULL` values.

### **Composite Key**

* A primary key that consists of two or more columns.

### **Check Constraint**

* Ensures that values in a column satisfy a specific condition.

---

## **5. Indexes**

### **Clustered Index**

* The data rows are stored in the order of the index.
* A table can only have **one clustered index**.

### **Non-Clustered Index**

* The index is stored separately from the data rows, containing pointers to the actual data.
* A table can have **multiple non-clustered indexes**.

### **Composite Index**

* An index that involves multiple columns.
* Helps optimize queries involving multiple columns.

---

## **6. ACID Properties (Transaction Management)**

### **Atomicity**:

* A transaction is either fully completed or fully rolled back.

### **Consistency**:

* A transaction takes the database from one valid state to another.

### **Isolation**:

* Transactions are executed independently, even if they run concurrently.

### **Durability**:

* Once a transaction is committed, its changes are permanent.

---

## **7. SQL Transaction Commands**

* **Begin a transaction**:

  ```sql
  BEGIN TRANSACTION;
  ```

* **Commit a transaction** (save changes):

  ```sql
  COMMIT;
  ```

* **Rollback a transaction** (undo changes):

  ```sql
  ROLLBACK;
  ```

* **Savepoint** (partial rollback):

  ```sql
  SAVEPOINT savepoint_name;
  ROLLBACK TO SAVEPOINT savepoint_name;
  ```

---

## **8. NoSQL Basics**

### **Types of NoSQL Databases**:

* **Document-Based (e.g., MongoDB)**:
  Stores data as documents, often in **JSON** or **BSON** format.

* **Key-Value Store (e.g., Redis)**:
  Stores data as key-value pairs.

* **Column-Family Store (e.g., Cassandra)**:
  Stores data in columns rather than rows.

* **Graph Databases (e.g., Neo4j)**:
  Stores data as nodes and edges for graph-like relationships.

### **When to use NoSQL**:

* High scalability.
* Schema-less, flexible data models.
* Unstructured or semi-structured data.
* High throughput or real-time applications.

---

## **9. Query Optimization**

### **Common Optimization Techniques**:

* **Indexing**: Create indexes on frequently queried columns to speed up retrieval.
* **Avoid SELECT *:** Only retrieve the columns you need.
* **Use WHERE Clauses Effectively**: Reduce the number of rows processed.
* **Avoid Nested Queries**: Where possible, try to flatten complex subqueries.
* **Analyze Query Plans**: Use `EXPLAIN` (MySQL/PostgreSQL) to analyze the query execution plan.

---

## **10. Best Practices for Database Design**

### **Scalability**:

* **Sharding**: Distribute data across multiple servers to handle high volume.
* **Partitioning**: Divide large tables into smaller, more manageable pieces.

### **Maintainability**:

* **Modular Design**: Break large tables into smaller, logical entities.
* **Naming Conventions**: Use clear and consistent naming conventions for tables and columns.

### **Security**:

* **Use of Roles and Permissions**: Grant the minimum necessary permissions to users.
* **Data Encryption**: Encrypt sensitive data both at rest and in transit.
* **Backup and Recovery**: Implement regular backups and test recovery procedures.

---

## **11. SQL Examples**

### **Join Types**:

* **INNER JOIN**: Retrieves matching rows from both tables.

  ```sql
  SELECT * FROM table1
  INNER JOIN table2 ON table1.id = table2.id;
  ```

* **LEFT JOIN**: Retrieves all rows from the left table and matching rows from the right table.

  ```sql
  SELECT * FROM table1
  LEFT JOIN table2 ON table1.id = table2.id;
  ```

* **RIGHT JOIN**: Retrieves all rows from the right table and matching rows from the left table.

  ```sql
  SELECT * FROM table1
  RIGHT JOIN table2 ON table1.id = table2.id;
  ```

* **FULL JOIN**: Retrieves matching rows from both tables and non-matching rows from both sides.

  ```sql
  SELECT * FROM table1
  FULL JOIN table2 ON table1.id = table2.id;
  ```

---

## **12. Common SQL Functions**

* **COUNT()**: Returns the number of rows that match the query.

  ```sql
  SELECT COUNT(*) FROM table_name;
  ```

* **SUM()**: Returns the sum of a numeric column.

  ```sql
  SELECT SUM(column_name) FROM table_name;
  ```

* **AVG()**: Returns the average value of a numeric column.

  ```sql
  SELECT AVG(column_name) FROM table_name;
  ```

* **GROUP BY**: Groups rows sharing a property for aggregate functions.

  ```sql
  SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name;
  ```

---

This **Database Design Cheatsheet** serves as a handy reference for learners who need to quickly recall key database design concepts, SQL syntax, and best practices. It consolidates the most important points from the **2-Day Crash Course** and provides practical examples.
