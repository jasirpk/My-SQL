# MySQL Learning Project

This repository contains my MySQL learning exercises and database projects.

## Topics Covered

* Database Creation
* Tables and Relationships
* CRUD Operations
* Primary & Foreign Keys
* Constraints
* Joins
* Aggregate Functions
* Views
* Indexes

## Technologies Used

* MySQL
* SQL
* MySQL Workbench

## Getting Started

1. Install MySQL Server and MySQL Workbench.
2. Create a database.
3. Run the SQL scripts provided in this repository.
4. Explore and practice different database operations.

## Purpose

This project was created to improve my understanding of relational databases and SQL while building a strong foundation for backend development.

## Author

**Jasir PK**

---

# MySQL Examples

## Create Database

```sql
CREATE DATABASE employee_db;
```

## Use Database

```sql
USE employee_db;
```

## Create Table

```sql
CREATE TABLE persons (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    phone VARCHAR(20),
    age INT
);
```

## Insert Data

```sql
INSERT INTO persons (name, phone, age)
VALUES ('Jasir', '9876543210', 24);
```

## View Data

```sql
SELECT * FROM persons;
```

## Update Data

```sql
UPDATE persons
SET age = 25
WHERE id = 1;
```

## Delete Data

```sql
DELETE FROM persons
WHERE id = 1;
```

## Drop Table

```sql
DROP TABLE persons;
```

## Copy Records from One Table to Another

### Create Backup Table

```sql
CREATE TABLE persons_backup (
    id INT,
    name VARCHAR(100),
    phone VARCHAR(20),
    age INT
);
```

### Copy All Records

```sql
INSERT INTO persons_backup
SELECT * FROM persons;
```

### Copy Specific Records

```sql
INSERT INTO persons_backup
SELECT * FROM persons
WHERE age > 18;
```

---

## Delete a Specific Record

### Delete Record by ID

```sql
DELETE FROM persons
WHERE id = 1;
```

### Delete Record by Name

```sql
DELETE FROM persons
WHERE name = 'Jasir';
```

### Delete Multiple Records

```sql
DELETE FROM persons
WHERE age < 18;
```

### Delete All Records (Keep Table Structure)

```sql
DELETE FROM persons;
```

### Delete All Records Faster

```sql
TRUNCATE TABLE persons;
```

---

## Move Record from One Table to Another

### Step 1: Copy Record

```sql
INSERT INTO persons_backup
SELECT * FROM persons
WHERE id = 1;
```

### Step 2: Delete Record from Original Table

```sql
DELETE FROM persons
WHERE id = 1;
```

This effectively moves the record from `persons` to `persons_backup`.


## Drop Database

```sql
DROP DATABASE employee_db;
```
