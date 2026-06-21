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

## DISTINCT Keyword

The `DISTINCT` keyword is used to return only unique values.

### View Unique Names

```sql
SELECT DISTINCT name
FROM persons;
```

### View Unique Ages

```sql
SELECT DISTINCT age
FROM persons;
```

---

## Filter Records Using WHERE

The `WHERE` clause is used to filter records based on a condition.

### Find Person by ID

```sql
SELECT *
FROM persons
WHERE id = 1;
```

### Find Person by Name

```sql
SELECT *
FROM persons
WHERE name = 'Jasir';
```

### Find Persons Older Than 18

```sql
SELECT *
FROM persons
WHERE age > 18;
```

### Find Persons Younger Than 30

```sql
SELECT *
FROM persons
WHERE age < 30;
```

### Find Persons Between Ages 20 and 30

```sql
SELECT *
FROM persons
WHERE age BETWEEN 20 AND 30;
```

### Find Names Starting With 'J'

```sql
SELECT *
FROM persons
WHERE name LIKE 'J%';
```

### Find Phone Numbers Containing '987'

```sql
SELECT *
FROM persons
WHERE phone LIKE '%987%';
```

### Multiple Conditions

```sql
SELECT *
FROM persons
WHERE age > 18 AND name = 'Jasir';
```

### OR Condition

```sql
SELECT *
FROM persons
WHERE name = 'Jasir' OR name = 'John';
```

## Sort Records

### Sort by Name (Ascending)

```sql
SELECT * FROM persons
ORDER BY name ASC;
```

### Sort by Age (Descending)

```sql
SELECT * FROM persons
ORDER BY age DESC;
```

### Sort by Multiple Columns

```sql
SELECT * FROM persons
ORDER BY age ASC, name ASC;
```

---

## Add New Column

### Add Email Column

```sql
ALTER TABLE persons
ADD email VARCHAR(100);
```

### Add Address Column

```sql
ALTER TABLE persons
ADD address VARCHAR(255);
```

---

## Rename Column

### Rename Phone Column to Mobile

```sql
ALTER TABLE persons
RENAME COLUMN phone TO mobile;
```

### Rename Name Column to Full Name

```sql
ALTER TABLE persons
RENAME COLUMN name TO full_name;
```

---

## Modify Column Data Type

### Increase Phone Column Length

```sql
ALTER TABLE persons
MODIFY COLUMN phone VARCHAR(50);
```

---

## Delete Column

### Remove Address Column

```sql
ALTER TABLE persons
DROP COLUMN address;
```
