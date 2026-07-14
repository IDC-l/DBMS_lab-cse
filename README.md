# MySQL DDL & DML Commands (Beginner to Advanced)

## DDL
### Create Database
```sql
CREATE DATABASE college;
USE college;
```

### Create Table
```sql
CREATE TABLE student(
 id INT PRIMARY KEY,
 name VARCHAR(50) NOT NULL,
 email VARCHAR(100) UNIQUE,
 age INT CHECK(age>=18)
);
```

### Constraints
```sql
PRIMARY KEY(id)
FOREIGN KEY(student_id) REFERENCES student(id)
NOT NULL
UNIQUE
CHECK(age>=18)
DEFAULT 'Active'
AUTO_INCREMENT
```

### ALTER TABLE
```sql
ALTER TABLE student ADD phone VARCHAR(15);
ALTER TABLE student DROP COLUMN phone;
ALTER TABLE student MODIFY age BIGINT;
ALTER TABLE student RENAME COLUMN name TO student_name;
ALTER TABLE student RENAME TO students;
```

### Keys & Indexes
```sql
ALTER TABLE student ADD PRIMARY KEY(id);
ALTER TABLE student DROP PRIMARY KEY;
ALTER TABLE marks ADD CONSTRAINT fk_student
FOREIGN KEY(student_id) REFERENCES student(id);
ALTER TABLE marks DROP FOREIGN KEY fk_student;
CREATE INDEX idx_name ON student(name);
CREATE UNIQUE INDEX idx_email ON student(email);
DROP INDEX idx_name ON student;
```

### TRUNCATE & DROP
```sql
TRUNCATE TABLE student;
DROP TABLE student;
DROP DATABASE college;
```

## Foreign Key Actions
```sql
ON DELETE CASCADE
ON UPDATE CASCADE
ON DELETE SET NULL
ON DELETE RESTRICT
ON DELETE NO ACTION
```

## DML
```sql
INSERT INTO student VALUES(1,'Rahul',20);
INSERT INTO student(id,name) VALUES(2,'Amit');
UPDATE student SET age=25 WHERE id=1;
DELETE FROM student WHERE id=2;
SELECT * FROM student;
SELECT name,age FROM student;
```

## Filtering
```sql
WHERE age>20
DISTINCT
ORDER BY age DESC
LIMIT 5
BETWEEN 18 AND 25
IN (18,20,22)
NOT IN (18,20)
LIKE 'A%'
IS NULL
IS NOT NULL
```

## Aggregate
```sql
COUNT(*)
SUM(age)
AVG(age)
MAX(age)
MIN(age)
GROUP BY age
HAVING COUNT(*)>2
```

## Joins
```sql
INNER JOIN
LEFT JOIN
RIGHT JOIN
CROSS JOIN
SELF JOIN
```

## Advanced Queries
```sql
Subquery
EXISTS
ANY
ALL
UNION
UNION ALL
```

## Transactions
```sql
START TRANSACTION;
SAVEPOINT sp1;
ROLLBACK TO sp1;
ROLLBACK;
COMMIT;
```

## Views
```sql
CREATE VIEW student_view AS
SELECT id,name FROM student;
SELECT * FROM student_view;
DROP VIEW student_view;
```

## Functions
```sql
NOW()
CURDATE()
CURTIME()
UPPER()
LOWER()
LENGTH()
ROUND()
CONCAT()
SUBSTRING()
COALESCE()
IFNULL()
```

## Learning Order
1. CREATE DATABASE / USE
2. CREATE TABLE
3. Constraints
4. ALTER TABLE
5. TRUNCATE / DROP
6. INSERT / SELECT / UPDATE / DELETE
7. WHERE, LIKE, IN, BETWEEN
8. ORDER BY / LIMIT
9. Aggregate Functions
10. GROUP BY / HAVING
11. Joins
12. Subqueries
13. UNION
14. Transactions
15. CASCADE / RESTRICT / SET NULL
16. Views & Indexes
