# **Database Design with MySQL – 2025 Workbook**

**Objective:** Walk learners from basic concepts to advanced MySQL database design with hands-on exercises and practical projects.

---

## **Module 1: Database Fundamentals – Hands-On**

### **Exercise 1.1: Identify Keys**

**Scenario:** Online Bookstore

| Table       | Columns                         |
| ----------- | ------------------------------- |
| books       | id, title, author_id, price     |
| authors     | id, name, country               |
| orders      | id, user_id, order_date         |
| order_items | id, order_id, book_id, quantity |

**Task:**

1. Mark the **Primary Key** for each table.
2. Mark the **Foreign Keys** and which table they reference.

**Hint:** PK uniquely identifies each row. FK links to another table’s PK.

---

### **Checkpoint 1**

* Can you explain what a PK and FK are in your own words?
* Can you identify which relationships are 1:1, 1:N, and M:N in this example?

---

## **Module 2: Requirements & Planning – Exercise**

**Scenario:** Library System

Entities:

* Books: book_id, title, genre_id, published_year
* Authors: author_id, name, birth_year
* Genres: genre_id, name
* Borrowers: borrower_id, name, email
* Borrowing Records: record_id, borrower_id, book_id, borrow_date, return_date

### **Exercise 2.1: Identify Attributes & Constraints**

1. Define PK for each table.
2. Define FK relationships.
3. Add constraints: NOT NULL, UNIQUE, DEFAULT, CHECK (MySQL 8+).

**Example Hint:** borrower_id → PK, email → UNIQUE NOT NULL

---

### **Checkpoint 2**

* Do you understand why constraints improve data integrity?
* Can you explain how FK maintains relationships?

---

## **Module 3: ER Modeling – Exercise**

**Scenario:** Movie Database

Entities:

* Movies
* Actors
* Directors
* Genres

### **Exercise 3.1: Draw ER Diagram**

1. Identify all entities.
2. Determine relationships: 1:N, M:N.
3. Draw ER diagram including PK, FK, and cardinality.

**Hint:** Actors ↔ Movies is M:N → use a join table: `movie_actors`.

---

### **Checkpoint 3**

* Can you convert your ER diagram into a MySQL schema?
* Can you explain which relationships require join tables?

---

## **Module 4: Normalization – Exercises**

### **Exercise 4.1: First Normal Form (1NF)**

Table: `students(id, name, courses)`

* Split repeating groups into separate tables.
* Create `enrollments(student_id, course_id)`.

---

### **Exercise 4.2: Second & Third Normal Form (2NF & 3NF)**

Table: `order_items(order_id, product_id, product_name, quantity)`

* Identify partial dependencies → move `product_name` to `products` table.
* Remove transitive dependencies.

**Hint:** 3NF ensures columns depend only on PK.

---

### **Checkpoint 4**

* Can you explain the difference between 1NF, 2NF, and 3NF?
* Can you identify redundant data in your tables?

---

## **Module 5: Implementing Tables in MySQL – Hands-On**

### **Exercise 5.1: Create Tables**

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

**Task:**

1. Create tables for `Borrowers` and `Borrowing Records` with appropriate PK/FK and constraints.
2. Insert 5 sample authors and 10 books.

---

### **Exercise 5.2: Many-to-Many Relationships**

```sql
CREATE TABLE book_genres (
    book_id INT,
    genre_id INT,
    PRIMARY KEY(book_id, genre_id),
    FOREIGN KEY(book_id) REFERENCES books(book_id),
    FOREIGN KEY(genre_id) REFERENCES genres(genre_id)
);
```

**Task:** Implement join tables for Students ↔ Courses or Movies ↔ Actors.

---

### **Checkpoint 5**

* Can you insert sample data maintaining FK constraints?
* Can you explain why join tables are necessary for M:N?

---

## **Module 6: Querying Data – Exercises**

### **Exercise 6.1: SELECT Queries**

* List all books: `SELECT * FROM books;`
* List books > $20: `SELECT title, price FROM books WHERE price > 20;`
* Join authors:

```sql
SELECT b.title, a.name AS author
FROM books b
JOIN authors a ON b.author_id = a.author_id;
```

---

### **Exercise 6.2: Aggregation**

* Count books per author:

```sql
SELECT author_id, COUNT(*) AS total_books
FROM books
GROUP BY author_id;
```

* Find top 5 borrowed books.

---

### **Exercise 6.3: Advanced Queries**

* Subqueries, joins, window functions (RANK, ROW_NUMBER)
* Example: Rank books by price:

```sql
SELECT title, price, RANK() OVER (ORDER BY price DESC) AS price_rank
FROM books;
```

---

### **Checkpoint 6**

* Can you write queries using joins and aggregate functions?
* Can you rank or filter results efficiently?

---

## **Module 7: Indexing & Optimization**

### **Exercise 7.1: Indexing**

* Create index on book titles:

```sql
CREATE INDEX idx_book_title ON books(title);
```

* Compare query speed with `EXPLAIN`.

### **Exercise 7.2: Query Optimization**

* Avoid `SELECT *`.
* Analyze EXPLAIN plans.
* Add composite indexes if necessary.

---

### **Checkpoint 7**

* Can you identify queries that need indexes?
* Can you explain how indexing improves performance?

---

## **Module 8: Advanced Features – Exercises**

### **Exercise 8.1: Views**

```sql
CREATE VIEW book_summary AS
SELECT a.name AS author, COUNT(b.book_id) AS total_books
FROM authors a
JOIN books b ON a.author_id = b.author_id
GROUP BY a.name;
```

### **Exercise 8.2: Triggers**

```sql
CREATE TRIGGER before_borrow_insert
BEFORE INSERT ON borrow_records
FOR EACH ROW
SET NEW.borrow_date = NOW();
```

### **Exercise 8.3: Stored Procedures**

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

## **Module 9: Security & Backup – Exercises**

* Create restricted users:

```sql
CREATE USER 'librarian'@'localhost' IDENTIFIED BY 'SecurePass';
GRANT SELECT, INSERT, UPDATE ON library.* TO 'librarian'@'localhost';
```

* Backup and restore:

```bash
mysqldump -u root -p library > backup.sql
mysql -u root -p library < backup.sql
```

**Exercise 9.1:** Create a backup and restore it to test integrity.

---

## **Module 10: Mini-Projects**

### **10.1 Library Management System**

* Tables: Books, Authors, Borrowers, Borrowing Records
* M:N: Books ↔ Genres
* Features: Views, triggers, stored procedures

### **10.2 E-Commerce Database**

* Tables: Users, Products, Orders, Order_Items, Categories
* Features: Indexes, triggers for stock updates, reports using views

### **10.3 Blog Database**

* Tables: Users, Posts, Comments, Tags
* M:N: Posts ↔ Tags
* Stored procedures for adding posts, triggers for timestamp updates

**Exercise 10.1:** Choose one project and:

1. Draw ER diagram
2. Create tables with constraints
3. Insert sample data
4. Write queries for analytics
5. Add one view, trigger, and stored procedure

---

### ✅ **Workbook Checkpoints**

* Completed exercises from all modules
* Can design normalized schema for real-world scenarios
* Can implement queries, indexes, and advanced features
* Understand MySQL security, backups, and optimization

---


