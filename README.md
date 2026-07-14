# MySQL DDL & DML Cheat Sheet (Easy to Learn)

## 1. Create Database
```sql
CREATE DATABASE college;
USE college;
```

## 2. Create Table
```sql
CREATE TABLE student(
 id INT PRIMARY KEY,
 name VARCHAR(50) NOT NULL,
 age INT,
 email VARCHAR(100) UNIQUE
);
```

## 3. Common Constraints
|Constraint|Purpose|
|---|---|
|PRIMARY KEY|Unique ID|
|FOREIGN KEY|Links tables|
|NOT NULL|Cannot be empty|
|UNIQUE|No duplicates|
|DEFAULT|Default value|
|AUTO_INCREMENT|Auto number|
|CHECK|Validates data|

## 4. Modify Table
```sql
ALTER TABLE student ADD phone VARCHAR(15);
ALTER TABLE student DROP COLUMN phone;
ALTER TABLE student MODIFY age BIGINT;
```

## 5. Delete Structure/Data
```sql
TRUNCATE TABLE student;
DROP TABLE student;
DROP DATABASE college;
```

## 6. Insert, Read, Update, Delete (CRUD)
```sql
INSERT INTO student VALUES(1,'Rahul',20,'a@mail.com');
SELECT * FROM student;
UPDATE student SET age=21 WHERE id=1;
DELETE FROM student WHERE id=1;
```

## 7. Filtering
```sql
WHERE age>18
ORDER BY age DESC
LIMIT 5
LIKE 'A%'
BETWEEN 18 AND 25
IN (18,20)
```

## 8. Aggregate Functions
```sql
COUNT(*)
SUM(age)
AVG(age)
MAX(age)
MIN(age)
GROUP BY age
HAVING COUNT(*)>1
```

## 9. Joins
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- CROSS JOIN
- SELF JOIN

## 10. Foreign Key Actions
- ON DELETE CASCADE
- ON UPDATE CASCADE
- ON DELETE SET NULL
- ON DELETE RESTRICT

## 11. Transactions
```sql
START TRANSACTION;
SAVEPOINT s1;
ROLLBACK;
COMMIT;
```

## Easy Learning Order
1. CREATE DATABASE
2. USE
3. CREATE TABLE
4. Constraints
5. INSERT
6. SELECT
7. UPDATE
8. DELETE
9. WHERE
10. ORDER BY
11. GROUP BY
12. JOINS
13. CASCADE
14. TRANSACTIONS

> Learn in this order and practice each command with a small table.
