# **Database Design with MySQL 2025**

**Audience:** Beginner to advanced engineers, data analysts, or developers seeking to master MySQL database design and implementation.

**Goal:** Learn relational database theory, design principles, MySQL implementation, optimization, advanced features, and real-world usage.

---

## **Module 1: Database Fundamentals – Understanding the Basics**

### **1.1 What is a Database?**

A **database** is an organized collection of data, designed to be **efficiently stored, retrieved, and maintained**.

**Key Concepts:**

* **Relational Database (RDBMS):** Stores data in tables (rows and columns).
* **Primary Key (PK):** Unique identifier for each row.
* **Foreign Key (FK):** Links tables to maintain relationships.
* **Index:** Speeds up queries.
* **Normalization:** Reduces redundancy and ensures data integrity.
* **ACID Properties:** Atomicity, Consistency, Isolation, Durability – ensures reliable transactions.

**Example:**

Imagine an **online bookstore**:

* `books` table: id, title, author_id, price
* `authors` table: id, name, country
* `orders` table: id, user_id, order_date
* `order_items` table: id, order_id, book_id, quantity

**Exercise 1.1:** Identify PK and FK for each table above.

---

### **1.2 Types of Relationships**

1. **One-to-One (1:1)** – Example: User → UserProfile
2. **One-to-Many (1:N)** – Example: Author → Books
3. **Many-to-Many (M:N)** – Example: Books ↔ Categories

**Implementation Tip:** Use a **join table** for M:N relationships.

**Exercise 1.2:** Draw relationship diagram for `students` and `courses`.

---

## **Module 2: Requirements Gathering & Planning**

### **2.1 Collecting Requirements**

* Identify **entities** and **attributes**
* Determine **relationships**
* Decide **constraints** (uniqueness, not null, default values)

**Example – Library System:**

* **Books:** book_id, title, genre_id, published_year
* **Authors:** author_id, name, birth_year
* **Genres:** genre_id, name
* **Borrowers:** borrower_id, name, email
* **Borrowing Records:** record_id, borrower_id, book_id, borrow_date, return_date

**Exercise 2.1:** List all entities and attributes for an **E-learning Platform** (Courses, Students, Instructors, Enrollments).

---

### **2.2 Defining Constraints & Business Rules**

* **PK** – unique row identifier
* **FK** – ensures referential integrity
* **UNIQUE** – prevents duplicate values
* **NOT NULL** – mandatory data
* **CHECK** – validates data (MySQL 8+ supports CHECK)
* **DEFAULT** – automatic default value

**Example:**

```sql
CREATE TABLE borrowers (
    borrower_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL
);
```

**Exercise 2.2:** Add appropriate constraints for the library `books` and `authors` tables.

---

## **Module 3: Entity-Relationship Modeling**

### **3.1 ER Diagram Components**

* **Entities:** Tables
* **Attributes:** Columns
* **Relationships:** Connect tables
* **Cardinality:** 1:1, 1:N, M:N
* **Participation:** Optional vs mandatory

**Example: Online Store**

```
Customers 1---* Orders *---* Products
Products *---* Categories
```

**Exercise 3.1:** Draw ER diagram for a **Movie Database** (Movies, Actors, Directors, Genres).

---

### **3.2 Converting ER Diagram to Tables**

1. **Entities → Tables**
2. **Attributes → Columns**
3. **Relationships → FK or Join Tables**

**M:N Example:**

* `movies` table
* `actors` table
* `movie_actors` join table: movie_id, actor_id

**Exercise 3.2:** Convert **Student-Course ER diagram** into tables with PK, FK, and constraints.

---

## **Module 4: Normalization**

### **4.1 First Normal Form (1NF)**

* Eliminate repeating groups
* Ensure **atomic values**

```sql
-- BAD (1NF violation)
students(id, name, courses)
```

```sql
-- GOOD (1NF)
students(id, name)
enrollments(student_id, course_id)
```

---

### **4.2 Second Normal Form (2NF)**

* 1NF + remove partial dependency
* Every column depends on the whole PK

**Example:**

```sql
-- BAD
order_items(order_id, product_id, product_name)
-- product_name depends only on product_id, not the full PK
```

```sql
-- GOOD
products(product_id, name)
order_items(order_id, product_id, quantity)
```

---

### **4.3 Third Normal Form (3NF)**

* 2NF + remove transitive dependency
* Every column depends only on PK

**Example:**

```sql
-- BAD
books(book_id, title, author_name)
-- author_name depends on author_id, not book_id
```

```sql
-- GOOD
authors(author_id, name)
books(book_id, title, author_id)
```

**Exercise 4.1:** Normalize a table:

| OrderID | CustomerName | ProductName | Quantity | ProductPrice |

---

## **Module 5: Implementing Tables in MySQL**

### **5.1 Table Creation with Constraints**

```sql
CREATE TABLE authors (
    author_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    country VARCHAR(50)
);

CREATE TABLE books (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author_id INT NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    FOREIGN KEY(author_id) REFERENCES authors(author_id) ON DELETE CASCADE
);
```

**Exercise 5.1:** Implement tables for Library System: Borrowers, Borrowing Records.

---

### **5.2 Handling Many-to-Many Relationships**

```sql
CREATE TABLE book_genres (
    book_id INT,
    genre_id INT,
    PRIMARY KEY(book_id, genre_id),
    FOREIGN KEY(book_id) REFERENCES books(book_id),
    FOREIGN KEY(genre_id) REFERENCES genres(genre_id)
);
```

**Exercise 5.2:** Implement join table for Students ↔ Courses.

---

### **5.3 Data Insertion Examples**

```sql
INSERT INTO authors(name, country) VALUES ('J.K. Rowling', 'UK');
INSERT INTO books(title, author_id, price) VALUES ('Harry Potter', 1, 29.99);
```

**Exercise 5.3:** Insert 5 sample authors and 10 books, ensuring FK integrity.

---

## **Module 6: Querying Data**

### **6.1 SELECT Queries**

```sql
SELECT * FROM books;
SELECT title, price FROM books WHERE price > 20;
SELECT b.title, a.name AS author FROM books b JOIN authors a ON b.author_id = a.author_id;
```

**Exercise 6.1:** Query all books by authors from the USA.

---

### **6.2 Aggregation & Grouping**

```sql
SELECT author_id, COUNT(*) AS book_count
FROM books
GROUP BY author_id;
```

**Exercise 6.2:** Find total borrowed books per borrower.

---

### **6.3 Advanced Queries**

* **Subqueries**
* **Joins (INNER, LEFT, RIGHT)**
* **Window Functions (MySQL 8+)**

```sql
SELECT title, price, RANK() OVER (ORDER BY price DESC) AS price_rank FROM books;
```

**Exercise 6.3:** Rank books by price.

---

## **Module 7: Indexing & Performance**

* **Primary Key:** Automatically indexed
* **Secondary Index:** Speeds up queries
* **Composite Index:** Index multiple columns

```sql
CREATE INDEX idx_book_title ON books(title);
```

**Exercise 7.1:** Compare query speed with and without index on 10k sample rows.

---

### **7.1 Query Optimization Tips**

* Avoid `SELECT *`
* Use proper indexes
* Minimize joins in heavy queries
* Use EXPLAIN to analyze query plan

```sql
EXPLAIN SELECT * FROM books WHERE title LIKE '%Harry%';
```

---

## **Module 8: Advanced Features**

### **8.1 Views**

```sql
CREATE VIEW book_summary AS
SELECT a.name AS author, COUNT(b.book_id) AS total_books
FROM authors a
JOIN books b ON a.author_id = b.author_id
GROUP BY a.name;
```

### **8.2 Triggers**

```sql
CREATE TRIGGER before_borrow_insert
BEFORE INSERT ON borrow_records
FOR EACH ROW
SET NEW.borrow_date = NOW();
```

### **8.3 Stored Procedures & Functions**

```sql
DELIMITER //
CREATE PROCEDURE add_book(IN b_title VARCHAR(255), IN a_id INT, IN b_price DECIMAL(10,2))
BEGIN
  INSERT INTO books(title, author_id, price) VALUES(b_title, a_id, b_price);
END;
//
DELIMITER ;
```

---

## **Module 9: Security & Backup**

* Create users with limited privileges:

```sql
CREATE USER 'librarian'@'localhost' IDENTIFIED BY 'SecurePass';
GRANT SELECT, INSERT, UPDATE ON library.* TO 'librarian'@'localhost';
```

* Backup:

```bash
mysqldump -u root -p library > backup.sql
```

* Restore:

```bash
mysql -u root -p library < backup.sql
```

---

## **Module 10: Real-World Mini-Projects**

### **10.1 Library Management System**

* Entities: Books, Authors, Borrowers, Borrowing Records
* Many-to-Many: Books ↔ Genres
* Features: Triggers for borrow dates, views for top authors, stored procedures for adding books

### **10.2 E-Commerce Database**

* Entities: Users, Products, Orders, Order_Items, Categories
* Features: Indexing on products, triggers for stock updates, views for top-selling products

### **10.3 Blog Database**

* Entities: Users, Posts, Comments, Tags
* M:N: Posts ↔ Tags
* Features: Stored procedures for adding posts, triggers for timestamp updates

**Exercise 10.1:** Build any one system from scratch: design ER diagram, create tables, insert sample data, write queries, and implement triggers/views.

---

## **Module 11: Best Practices & Pitfalls**

* Use **InnoDB** for transactional support
* Always **plan schema first**
* Normalize, but selectively denormalize for reports
* Use **foreign keys for data integrity**
* Avoid `SELECT *` in production queries
* Use **prepared statements** to prevent SQL injection

---

### ✅ **Summary**

* Relational database concepts
* ER diagrams and normalization
* Table creation and relationships
* CRUD operations, joins, and aggregation
* Indexing and performance optimization
* Advanced MySQL features: triggers, views, procedures
* Security, backup, and real-world application integration

---


