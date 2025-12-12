# **Engineering Guide**

---

## **Day 1 — Fundamentals and Relational Design**

### **Session 1: Introduction to Databases (1 hour)**

---

## **1.1 Overview of Databases**

A **database** is an organized collection of structured information, typically stored electronically. Databases allow efficient **storage, retrieval, modification, and deletion** of data.

### **Why Databases Matter**

* Enable applications to store persistent data
* Support multi-user access and concurrency control
* Ensure high performance for large datasets

### **Key Terminology**

| Term               | Meaning                  | Example                      |
| ------------------ | ------------------------ | ---------------------------- |
| **Table**          | Logical grouping of data | `users`, `orders`            |
| **Record (Row)**   | Single entry in a table  | `{'id': 1, 'name': 'John'}`  |
| **Field (Column)** | Attribute of data        | `email`, `price`, `category` |

### **Database Types**

* **Relational (RDBMS):** MySQL, PostgreSQL, SQLite (uses tables, SQL)
* **NoSQL:** MongoDB (documents), Redis (key-value), Cassandra (wide column)

---

## **1.2 Relational Database Basics**

### **Primary Key**

A unique identifier for each row.

```sql
CREATE TABLE users (
    user_id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE
);
```

### **Foreign Key**

Defines a relationship between tables.

```sql
CREATE TABLE orders (
    order_id SERIAL PRIMARY KEY,
    user_id INT REFERENCES users(user_id),
    amount DECIMAL(10,2)
);
```

### **Referential Integrity**

Ensures linked data remains valid.

Examples:

* Cannot delete a user who still has orders.
* Cannot insert an order with a non-existent `user_id`.

---

## **Session 2: Data Modeling & ER Diagrams (2 hours)**

---

## **2.1 Data Modeling Concepts**

### **Entities**

Represent objects or concepts.

* `User`
* `Order`
* `Product`

### **Attributes**

Properties describing entities.

* User → `name`, `email`, `password`

### **Relationships**

| Type    | Example               | Meaning                                 |
| ------- | --------------------- | --------------------------------------- |
| **1:1** | User ↔ Profile        | One user has one profile                |
| **1:N** | User → Orders         | One user has many orders                |
| **M:N** | Products ↔ Categories | Many products belong to many categories |

---

## **2.2 ER Diagram Example: E‑Commerce**

**Entity: User**

* id (PK)
* name
* email

**Entity: Order**

* id (PK)
* user_id (FK → User)
* status

**Relationship:** 1 user ↔ N orders

---

## **Session 3: Database Normalization (2 hours)**

---

## **3.1 Why Normalize?**

Normalization reduces:

* Data duplication
* Update anomalies
* Delete anomalies
* Inconsistent data

---

## **3.2 Normal Forms with Examples**

### **First Normal Form (1NF)**

No repeating groups. Values must be atomic.

❌ **Bad Example:**

```sql
table Orders (
    id INT,
    items TEXT, -- "apple, banana, orange"
)
```

✔ **Fixed Example:**

```sql
table OrderItems (
    id INT,
    order_id INT,
    item_name VARCHAR(50)
)
```

---

### **Second Normal Form (2NF)**

No partial dependency (applies only if composite key).

❌ **Bad Example:**

```sql
CREATE TABLE Enrollment (
    student_id INT,
    course_id INT,
    student_name VARCHAR(50)
);
```

✔ **Fixed:** Move `student_name` to `Students` table.

---

### **Third Normal Form (3NF)**

No transitive dependencies.

❌ **Bad Example:**

```sql
products(id, name, price, category, category_description)
```

✔ **Fixed:**

```sql
categories(id, name, description)
products(id, name, price, category_id)
```

---

## **Session 4: Translating ERD to Schema (2 hours)**

---

### **ERD → Relational Tables Example**

Entity **Book** + Entity **Author** with M:N relationship.

#### **ERD:**

* Book
* Author
* Relationship: A book can have many authors.

#### **Relational Model:**

```sql
CREATE TABLE authors (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100)
);

CREATE TABLE books (
    id SERIAL PRIMARY KEY,
    title VARCHAR(200)
);

CREATE TABLE book_authors (
    book_id INT REFERENCES books(id),
    author_id INT REFERENCES authors(id),
    PRIMARY KEY(book_id, author_id)
);
```

---

## **Session 5: Best Practices (1 hour)**

---

### **Integrity Constraints**

* **NOT NULL**
* **UNIQUE**
* **CHECK** (e.g., age ≥ 18)

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    age INT CHECK (age >= 18)
);
```

### **Indexing Basics**

```sql
CREATE INDEX idx_user_email ON users(email);
```

Indexes speed up reads but slow writes.

---

## **Day 2 — Advanced Topics, SQL & Practical Design**

### **Session 1: Advanced Concepts (2 hours)**

---

## **Advanced Normalization**

* 4NF: Remove multi-valued dependencies
* 5NF: Break down join dependencies
* BCNF: Stricter than 3NF

### **Example of BCNF Violation**

```sql
-- A table where multiple candidate keys exist
```

*(You can add real examples based on your use case.)*

---

## **Session 2: NoSQL Design Overview (1 hour)**

---

### **MongoDB Example Schema**

```json
{
  "_id": 1,
  "name": "John",
  "orders": [
    { "order_id": 101, "items": ["apple", "banana"] }
  ]
}
```

Denormalization is common for performance.

---

## **Session 3: SQL Implementation (2 hours)**

---

### **DDL Example (Create/Alter/Drop)**

```sql
CREATE TABLE products (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50),
    price DECIMAL(10,2)
);

ALTER TABLE products ADD COLUMN stock INT DEFAULT 0;

DROP TABLE products;
```

### **DML Example (Select/Insert/Update/Delete)**

```sql
INSERT INTO products(name, price) VALUES ('Laptop', 1200);

UPDATE products SET price = 1100 WHERE id = 1;

DELETE FROM products WHERE id = 1;
```

### **JOINS**

```sql
SELECT u.name, o.amount
FROM users u
JOIN orders o ON u.id = o.user_id;
```

---

## **Session 4: Final Hands-on Project (2 hours)**

---

### **Scenario Example: Library System**

Design an ERD and convert it into SQL.

#### **Tables**

* Books
* Members
* Loans (relationship)

```sql
CREATE TABLE members (...);
CREATE TABLE books (...);
CREATE TABLE loans (
    member_id INT,
    book_id INT,
    loan_date DATE,
    PRIMARY KEY(member_id, book_id)
);
```

---

## **Session 5: Review & Wrap-Up (1 hour)**

