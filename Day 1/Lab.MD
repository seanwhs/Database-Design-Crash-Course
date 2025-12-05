# **Day 1 Lab: Fundamentals and Relational Design**

---

### **Lab Objectives for Day 1:**

By the end of the lab, students will:

* Create **Entity-Relationship (ER) Diagrams** for real-world systems.
* Normalize data to **1NF, 2NF, and 3NF**.
* Write **SQL CREATE TABLE** statements based on ER diagrams.
* Apply **integrity constraints** (Primary Keys, Foreign Keys, Not Null) and optimize query performance using indexing.

---

### **Lab Setup:**

* **Required Tools**:

  * A **DBMS** (MySQL, PostgreSQL, or SQLite) installed on each student’s machine or a shared environment.
  * **ER diagramming tool** (optional, e.g., dbdiagram.io, Lucidchart, or pen and paper).
  * A code editor or SQL client (e.g., MySQL Workbench, pgAdmin, or SQLFiddle).

---

### **Lab Tasks Overview:**

1. **Task 1**: Create an ER diagram for a simple system.
2. **Task 2**: Normalize a given unnormalized table to 1NF, 2NF, and 3NF.
3. **Task 3**: Write SQL **CREATE TABLE** statements based on the ER diagram.
4. **Task 4**: Apply integrity constraints (Primary Key, Foreign Key, Not Null).
5. **Task 5**: Index frequently queried columns to optimize performance.

---

### **Lab Task 1: Create an ER Diagram for a Simple System**

**Objective:**
Design an ER diagram for a real-world system based on the following requirements.

#### **Scenario**:

You are tasked with designing a database for a **Library Management System**. The system must track information about books, authors, and the borrow/return process. Here are the details:

1. **Books**: Each book has a title, ISBN, publication year, and a relationship with one or more authors.
2. **Authors**: Each author has a first name and last name.
3. **Borrowing**: Users can borrow books. A user has a name and user ID, and each borrowing has a date.

#### **Task**:

* Create an ER diagram that shows:

  * Entities: **Books**, **Authors**, **Users**, **Borrowing**.
  * Relationships: **Books** are written by **Authors** (Many-to-Many), **Users** borrow **Books** (Many-to-Many).

**Deliverable:**

* Submit an ER diagram showing the entities, attributes, and relationships. Use appropriate cardinality notation.

---

### **Lab Task 2: Normalize the Given Table to 1NF, 2NF, and 3NF**

**Objective:**
Normalize an unnormalized table into 1NF, 2NF, and 3NF to eliminate redundancy and ensure data integrity.

#### **Unnormalized Table (Orders)**:

| OrderID | CustomerName | Product1 | Product2 | Product3 | OrderDate  | TotalAmount |
| ------- | ------------ | -------- | -------- | -------- | ---------- | ----------- |
| 101     | John Doe     | Book     | Pen      | Notebook | 2025-11-01 | 45.00       |
| 102     | Jane Smith   | Pencil   | NULL     | NULL     | 2025-11-02 | 10.00       |
| 103     | John Doe     | Laptop   | Phone    | NULL     | 2025-11-03 | 1500.00     |

#### **Task:**

* **Step 1**: Convert the table into **1NF** (ensure atomic values, eliminate repeating groups).
* **Step 2**: Convert the table into **2NF** (remove partial dependencies, ensure non-key attributes depend on the entire primary key).
* **Step 3**: Convert the table into **3NF** (eliminate transitive dependencies).

**Deliverable:**

* Submit the normalized tables for **1NF**, **2NF**, and **3NF**.

---

### **Lab Task 3: Write SQL CREATE TABLE Statements Based on the ER Diagram**

**Objective:**
Translate the ER diagram you created in **Task 1** into SQL **CREATE TABLE** statements. This will involve defining the structure of each table and establishing relationships between them.

#### **Task**:

* Create **CREATE TABLE** statements for the following tables based on the ER diagram:

  * **Books** (BookID, Title, ISBN, PublicationYear)
  * **Authors** (AuthorID, FirstName, LastName)
  * **Users** (UserID, UserName)
  * **Borrowing** (BorrowingID, BookID, UserID, BorrowDate, ReturnDate)

  Define the following constraints:

  * **Primary Keys** for each table (e.g., BookID for Books).
  * **Foreign Keys** for relationships between tables (e.g., BookID in the Borrowing table, referencing Books).

#### **Task Example (Books Table)**:

```sql
CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(255) NOT NULL,
    ISBN VARCHAR(50),
    PublicationYear INT
);
```

**Deliverable:**

* Submit the SQL **CREATE TABLE** statements for all entities and relationships in the Library Management System.

---

### **Lab Task 4: Apply Integrity Constraints (Primary Key, Foreign Key, Not Null)**

**Objective:**
Implement **integrity constraints** in the SQL schema to enforce data integrity.

#### **Task**:

* Add **Primary Key**, **Foreign Key**, and **Not Null** constraints to your previously written **CREATE TABLE** statements.
* For example:

  * In the **Borrowing** table, the **BookID** should be a **Foreign Key** that references **Books(BookID)**.
  * In the **Borrowing** table, the **UserID** should be a **Foreign Key** that references **Users(UserID)**.

#### **Task Example (Borrowing Table)**:

```sql
CREATE TABLE Borrowing (
    BorrowingID INT PRIMARY KEY,
    BookID INT NOT NULL,
    UserID INT NOT NULL,
    BorrowDate DATE NOT NULL,
    ReturnDate DATE,
    FOREIGN KEY (BookID) REFERENCES Books(BookID),
    FOREIGN KEY (UserID) REFERENCES Users(UserID)
);
```

**Deliverable:**

* Submit the SQL **CREATE TABLE** statements with integrity constraints applied.

---

### **Lab Task 5: Index Frequently Queried Columns to Optimize Performance**

**Objective:**
Optimize the database by creating **indexes** on frequently queried columns to improve query performance.

#### **Task:**

* Identify columns that are likely to be frequently queried (e.g., **BookID** in the **Borrowing** table, **UserID** in the **Users** table).
* Create **indexes** on these columns to speed up lookups.

#### **Task Example (Index Creation)**:

```sql
CREATE INDEX idx_bookid ON Borrowing(BookID);
CREATE INDEX idx_userid ON Borrowing(UserID);
```

**Deliverable:**

* Submit the SQL statements for creating indexes on relevant columns.

---

### **Lab Recap and Review:**

* **Review Key Concepts**:

  * **ER Diagrams**, **Normalization** (1NF, 2NF, 3NF), **SQL CREATE TABLE** with integrity constraints, and **Indexing**.
* **Q&A Session**: Answer any questions from students, provide clarification on SQL syntax and normalization.

---

### **Additional Notes for Trainers:**

* **Encourage student interaction**: Ask students to work in pairs or small groups for the hands-on exercises.
* **Provide immediate feedback**: While students are working on the tasks, walk around and give feedback on their SQL queries and ER diagrams.
* **Use real-world examples**: Share examples from industries like **e-commerce**, **education**, or **healthcare** to show how normalization and relational design are applied in practical scenarios.
* **Optional Challenge**: After completing the main tasks, challenge students to create a new system (e.g., **Movie Rental System**) and design the database on their own.

---

### **Materials Needed:**

* **ER diagramming tool** (dbdiagram.io, Lucidchart, or pen and paper).
* **SQL client** or **DBMS** (MySQL, PostgreSQL, SQLite).
* **Instructor resources**: Sample answers for each task to review during class.

---

This **Day 1 Lab** ensures that students can apply what they've learned about relational databases through hands-on activities. It focuses on practical skills like database design, normalization, writing SQL statements, and optimizing database performance. 