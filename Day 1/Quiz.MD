# **Day 1 Quiz: Database Fundamentals & Relational Design**

### **Quiz 1: Relational Databases & Key Concepts (10 questions)**

---

**1. What is a relational database?**
a) A database that stores data in tables with rows and columns
b) A database that stores data in JSON format
c) A database that stores data in key-value pairs
d) A database that stores data as files in directories

**2. Which of the following defines a **primary key** in a relational database?**
a) A column that uniquely identifies each row in a table
b) A column that links two tables together
c) A column that stores unique non-null values
d) A column that ensures data integrity across tables

**3. Which of the following defines a **foreign key** in a relational database?**
a) A column that uniquely identifies each row in a table
b) A column that references the primary key of another table
c) A column that stores a unique value across multiple rows
d) A column that ensures data uniqueness within a table

**4. What is **referential integrity** in a relational database?**
a) The consistency and validity of data within a single table
b) The enforcement of constraints between related tables to maintain consistency
c) The removal of redundant data within a table
d) The creation of relationships between unrelated tables

**5. What does the **SQL command `CREATE TABLE` do?**
a) Deletes a table from the database
b) Modifies the structure of an existing table
c) Creates a new table in the database
d) Updates the data in an existing table

**6. Which of the following is **NOT** an example of a **relation** in a relational database?**
a) A table
b) A row
c) A column
d) A graph

**7. How is data stored in a relational database?**
a) In rows and columns
b) In JSON objects
c) As key-value pairs
d) In spreadsheets

**8. What is a **candidate key**?**
a) A column that can be used as a primary key but is not yet chosen
b) A column that links tables together
c) A column that stores foreign key values
d) A column that stores unique values across tables

**9. What type of relationship does a **many-to-many** (M:N) represent in an ER diagram?**
a) A relationship where one record in Table A is related to only one record in Table B
b) A relationship where multiple records in Table A are related to only one record in Table B
c) A relationship where one record in Table A is related to multiple records in Table B
d) A relationship where multiple records in Table A are related to multiple records in Table B

**10. Which of the following is an example of a **transitive dependency**?**
a) When a non-key attribute is dependent on the primary key
b) When a non-key attribute depends on another non-key attribute
c) When a foreign key references a primary key
d) When a column contains non-atomic values

---

### **Quiz 2: Entity-Relationship Diagrams (5 questions)**

---

**1. In an ER diagram, what does a **rectangle** represent?**
a) An attribute
b) A relationship
c) An entity
d) A primary key

**2. In an ER diagram, what does a **diamond** represent?**
a) A relationship
b) An attribute
c) A foreign key
d) A table

**3. What is the purpose of **cardinality** in an ER diagram?**
a) To define the attributes of an entity
b) To show the relationship between two entities
c) To define the minimum and maximum number of instances of one entity related to another
d) To indicate which entities are primary

**4. If an ER diagram shows a relationship between **Authors** and **Books** with a **many-to-many** (M:N) cardinality, what is the best way to represent this in a relational database?**
a) Store the relationship directly in the Books table
b) Store the relationship in an **AuthorBook** junction table
c) Store the relationship directly in the Authors table
d) Combine Authors and Books into a single table

**5. In an ER diagram, what does a **line** between two entities represent?**
a) An attribute
b) A foreign key
c) A relationship
d) A primary key

---

### **Quiz 3: Normalization (5 questions)**

---

**1. What is the main goal of **normalization** in database design?**
a) To reduce the size of the database
b) To eliminate redundancy and ensure data integrity
c) To improve the speed of queries
d) To increase data security

**2. Which of the following is **NOT** a requirement for a table to be in **First Normal Form (1NF)**?**
a) The table must have a primary key
b) Each column must contain atomic (indivisible) values
c) Each row must be unique
d) The table must have a foreign key

**3. What is a **partial dependency** in the context of **Second Normal Form (2NF)**?**
a) A non-key attribute that depends on part of a composite primary key
b) A non-key attribute that depends on another non-key attribute
c) A column that contains multiple values
d) A column that does not contain unique values

**4. What does **Third Normal Form (3NF)** require?**
a) Eliminate partial dependencies
b) Eliminate transitive dependencies (non-key attributes must not depend on other non-key attributes)
c) Eliminate repeating groups
d) Both a and b

**5. Which of the following **is NOT** an example of **transitive dependency** in a database?**
a) When an employee’s department depends on their department manager
b) When an employee’s salary depends on their department
c) When an employee’s department depends on the department manager’s phone number
d) When an employee’s name depends on their employee ID

---

### **Quiz 4: SQL and Database Design (5 questions)**

---

**1. Which of the following is the correct SQL statement to create a table called **Customers** with a **CustomerID** as the primary key?**
a) `CREATE TABLE Customers (CustomerID INT, CustomerName VARCHAR(100), PRIMARY KEY (CustomerID));`
b) `CREATE TABLE Customers (CustomerID INT PRIMARY KEY, CustomerName VARCHAR(100));`
c) `CREATE TABLE Customers (CustomerID INT NOT NULL PRIMARY KEY, CustomerName VARCHAR(100));`
d) `CREATE TABLE Customers (CustomerName VARCHAR(100), CustomerID INT PRIMARY KEY);`

**2. Which SQL constraint would you use to ensure that a **CustomerName** column cannot be left empty?**
a) `NOT NULL`
b) `UNIQUE`
c) `CHECK`
d) `FOREIGN KEY`

**3. In SQL, what is the purpose of a **Foreign Key** constraint?**
a) To create relationships between tables by ensuring that one table’s column references another table’s primary key
b) To ensure that all rows in a table have unique values
c) To check for invalid data entries in a column
d) To automatically generate values for a column

**4. What is the correct SQL statement to **add a foreign key constraint** to a table?**
a) `ALTER TABLE TableName ADD FOREIGN KEY (columnName) REFERENCES AnotherTable (columnName);`
b) `ALTER TABLE TableName ADD PRIMARY KEY (columnName);`
c) `ALTER TABLE TableName ADD CONSTRAINT (columnName) FOREIGN KEY REFERENCES AnotherTable;`
d) `CREATE FOREIGN KEY (columnName) REFERENCES AnotherTable;`

**5. What does the **SQL statement `DROP TABLE` do?**
a) Deletes all rows in the table but keeps the table structure
b) Deletes the entire table, including all data and structure
c) Modifies the structure of an existing table
d) Renames the table to a new name

---

### **Answer Key:**

**Quiz 1:**

1. a
2. a
3. b
4. b
5. c
6. d
7. a
8. a
9. d
10. b

**Quiz 2:**

1. c
2. a
3. c
4. b
5. c

**Quiz 3:**

1. b
2. d
3. a
4. b
5. c

**Quiz 4:**

1. b
2. a
3. a
4. a
5. b

---

These quizzes are designed to assess students’ understanding of key concepts in **relational database design**, **normalization**, **ER diagrams**, and **SQL**. They can be used for formative assessments during or after the course. 