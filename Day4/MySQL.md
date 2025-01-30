Here’s a **comprehensive list of MySQL commands** categorized by their functionality, along with their usage.  

---

# **📌 MySQL Commands & Their Usage**  

## **1️⃣ Database Commands**  

| Command | Description | Example |
|---------|------------|---------|
| `SHOW DATABASES;` | Lists all available databases. | `SHOW DATABASES;` |
| `CREATE DATABASE database_name;` | Creates a new database. | `CREATE DATABASE school;` |
| `USE database_name;` | Selects a database for use. | `USE school;` |
| `DROP DATABASE database_name;` | Deletes a database. | `DROP DATABASE school;` |

---

## **2️⃣ Table Commands**  

| Command | Description | Example |
|---------|------------|---------|
| `SHOW TABLES;` | Lists all tables in the selected database. | `SHOW TABLES;` |
| `CREATE TABLE table_name (column1 datatype, column2 datatype, ...);` | Creates a new table. | `CREATE TABLE students (id INT, name VARCHAR(100));` |
| `DESC table_name;` | Describes table structure. | `DESC students;` |
| `ALTER TABLE table_name ADD COLUMN column_name datatype;` | Adds a new column. | `ALTER TABLE students ADD age INT;` |
| `ALTER TABLE table_name DROP COLUMN column_name;` | Deletes a column. | `ALTER TABLE students DROP COLUMN age;` |
| `DROP TABLE table_name;` | Deletes a table. | `DROP TABLE students;` |
| `TRUNCATE TABLE table_name;` | Removes all data from a table but keeps structure. | `TRUNCATE TABLE students;` |
| `RENAME TABLE old_table_name TO new_table_name;` | Rename the table name. | `RENAME TABLE students TO employees;` |

---

## **3️⃣ Data Manipulation (DML) Commands**  

| Command | Description | Example |
|---------|-------------|---------|
| `INSERT INTO table_name (column1, column2) VALUES (value1, value2);` | Inserts new data into a table. | `INSERT INTO students (id, name) VALUES (1, 'John');` |
| `SELECT * FROM table_name;` | Retrieves all records from a table. | `SELECT * FROM students;` |
| `SELECT column1, column2 FROM table_name;` | Retrieves specific columns. | `SELECT name FROM students;` |
| `SELECT * FROM table_name WHERE condition;` | Filters records based on a condition. | `SELECT * FROM students WHERE id = 1;` |
| `UPDATE table_name SET column1 = value1 WHERE condition;` | Updates records. | `UPDATE students SET name = 'Mike' WHERE id = 1;` |
| `DELETE FROM table_name WHERE condition;` | Deletes specific records. | `DELETE FROM students WHERE id = 1;` |
| `INSERT INTO table_name SELECT * FROM another_table;` | Inserts records from one table into another. | `INSERT INTO students (id, name) SELECT id, name FROM temp_students;` |
| `SELECT DISTINCT column_name FROM table_name;` | Retrieves unique values from a column. | `SELECT DISTINCT department FROM employees;` |
| `SELECT * FROM table_name ORDER BY column_name ASC/DESC;` | Sorts the result set in ascending or descending order. | `SELECT * FROM students ORDER BY name ASC;` |
| `SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name;` | Groups data and applies aggregate functions like COUNT. | `SELECT department, COUNT(*) FROM employees GROUP BY department;` |
| `SELECT * FROM table_name LIMIT number;` | Limits the number of rows returned. | `SELECT * FROM students LIMIT 5;` |
| `UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;` | Updates multiple columns in records. | `UPDATE students SET name = 'Mike', age = 20 WHERE id = 1;` |
| `DELETE FROM table_name;` | Deletes all records from a table. | `DELETE FROM students;` |
| `TRUNCATE TABLE table_name;` | Removes all records from a table, but keeps the structure intact. | `TRUNCATE TABLE students;` |
| `SELECT * FROM table_name WHERE column_name LIKE pattern;` | Filters records using wildcard patterns. | `SELECT * FROM students WHERE name LIKE 'J%';` |
| `SELECT * FROM table_name WHERE column_name IN (value1, value2, ...);` | Filters records where a column’s value matches any value in the list. | `SELECT * FROM students WHERE department IN ('Math', 'Science');` |
| `SELECT * FROM table_name WHERE column_name BETWEEN value1 AND value2;` | Filters records within a specific range. | `SELECT * FROM students WHERE age BETWEEN 18 AND 25;` |
| `SELECT * FROM table_name WHERE column_name IS NULL;` | Filters records where a column is NULL. | `SELECT * FROM students WHERE graduation_date IS NULL;` |
| `SELECT * FROM table_name WHERE column_name IS NOT NULL;` | Filters records where a column is not NULL. | `SELECT * FROM students WHERE graduation_date IS NOT NULL;` |

---

## **4️⃣ Query Filtering & Sorting**  

| Command | Description | Example |
|---------|-------------|---------|
| `WHERE` | Filters records based on a condition. | `SELECT * FROM students WHERE age > 18;` |
| `ORDER BY column_name ASC/DESC;` | Sorts results by a column in ascending (ASC) or descending (DESC) order. | `SELECT * FROM students ORDER BY name ASC;` |
| `LIMIT n;` | Limits the number of rows returned. | `SELECT * FROM students LIMIT 5;` |
| `DISTINCT column_name;` | Removes duplicates from the result set. | `SELECT DISTINCT age FROM students;` |
| `AND` | Combines multiple conditions. | `SELECT * FROM students WHERE age > 18 AND grade = 'A';` |
| `OR` | Returns records that meet at least one of the conditions. | `SELECT * FROM students WHERE grade = 'A' OR grade = 'B';` |
| `BETWEEN` | Filters records within a range (inclusive). | `SELECT * FROM students WHERE age BETWEEN 18 AND 25;` |
| `LIKE` | Filters records using pattern matching with wildcards. | `SELECT * FROM students WHERE name LIKE 'J%';` |
| `IN` | Filters records based on a set of possible values. | `SELECT * FROM students WHERE department IN ('Math', 'Science');` |
| `IS NULL` | Filters records where a column has a NULL value. | `SELECT * FROM students WHERE graduation_date IS NULL;` |
| `IS NOT NULL` | Filters records where a column does not have a NULL value. | `SELECT * FROM students WHERE graduation_date IS NOT NULL;` |
| `NOT` | Reverses the logic of a condition. | `SELECT * FROM students WHERE NOT grade = 'F';` |
| `GROUP BY` | Groups rows that have the same values into summary rows, often with aggregate functions. | `SELECT department, COUNT(*) FROM students GROUP BY department;` |
| `HAVING` | Filters groups created by `GROUP BY` based on a condition. | `SELECT department, COUNT(*) FROM students GROUP BY department HAVING COUNT(*) > 5;` |
| `ORDER BY column_name ASC/DESC NULLS FIRST/LAST;` | Sorts results, placing NULLs at the beginning (FIRST) or end (LAST). | `SELECT * FROM students ORDER BY name ASC NULLS LAST;` |
| `OFFSET n` | Skips the first n rows, often used with `LIMIT` for pagination. | `SELECT * FROM students LIMIT 5 OFFSET 10;` |
| `EXCEPT` | Returns the difference between two result sets (records in the first set but not in the second). | `SELECT name FROM students WHERE grade = 'A' EXCEPT SELECT name FROM students WHERE age < 20;` |
| `INTERSECT` | Returns records that exist in both result sets. | `SELECT name FROM students WHERE grade = 'A' INTERSECT SELECT name FROM students WHERE age > 18;` |
| `FULL OUTER JOIN` | Retrieves records when there is a match in either of the tables involved in the join. | `SELECT * FROM students FULL OUTER JOIN courses ON students.id = courses.student_id;` |

---

## **5️⃣ Joins (Combining Tables)**  

| Command | Description | Example |
|---------|-------------|---------|
| `INNER JOIN` | Returns records that have matching values in both tables. | `SELECT students.name, courses.course FROM students INNER JOIN courses ON students.id = courses.student_id;` |
| `LEFT JOIN` (or `LEFT OUTER JOIN`) | Returns all records from the left table and the matched records from the right table. If no match, NULL values are returned for columns from the right table. | `SELECT students.name, courses.course FROM students LEFT JOIN courses ON students.id = courses.student_id;` |
| `RIGHT JOIN` (or `RIGHT OUTER JOIN`) | Returns all records from the right table and the matched records from the left table. If no match, NULL values are returned for columns from the left table. | `SELECT students.name, courses.course FROM students RIGHT JOIN courses ON students.id = courses.student_id;` |
| `FULL JOIN` (or `FULL OUTER JOIN`) | Returns all records when there is a match in either left or right table. If there’s no match, NULL values are returned for non-matching columns. | `SELECT students.name, courses.course FROM students FULL JOIN courses ON students.id = courses.student_id;` |
| `CROSS JOIN` | Returns the Cartesian product of both tables (every row of the left table is combined with every row of the right table). | `SELECT students.name, courses.course FROM students CROSS JOIN courses;` |
| `SELF JOIN` | Joins a table with itself. Typically used to find relationships within the same table (e.g., employee-manager relationships). | `SELECT e.name AS Employee, m.name AS Manager FROM employees e LEFT JOIN employees m ON e.manager_id = m.id;` |
| `NATURAL JOIN` | Automatically joins tables based on columns with the same name in both tables (columns must have the same name and compatible data types). | `SELECT students.name, courses.course FROM students NATURAL JOIN courses;` |
| `JOIN USING` | A simplified form of `JOIN ON` where the column name used for joining is specified in the `USING` clause. | `SELECT students.name, courses.course FROM students JOIN courses USING (student_id);` |
| `JOIN ON` | Explicitly specifies the condition for joining tables using the `ON` keyword. (Commonly used for `INNER`, `LEFT`, `RIGHT`, `FULL` joins.) | `SELECT students.name, courses.course FROM students LEFT JOIN courses ON students.id = courses.student_id;` |

---

## **6️⃣ Aggregate Functions**  

| Command | Description | Example |
|---------|-------------|---------|
| `COUNT(column_name)` | Counts the number of records in a column (excluding NULLs). | `SELECT COUNT(id) FROM students;` |
| `COUNT(*)` | Counts the total number of rows in a table. | `SELECT COUNT(*) FROM students;` |
| `SUM(column_name)` | Sums the numeric values in a column. | `SELECT SUM(price) FROM orders;` |
| `AVG(column_name)` | Calculates the average value of a numeric column. | `SELECT AVG(salary) FROM employees;` |
| `MIN(column_name)` | Returns the minimum value in a column. | `SELECT MIN(age) FROM students;` |
| `MAX(column_name)` | Returns the maximum value in a column. | `SELECT MAX(price) FROM products;` |
| `GROUP_CONCAT(column_name)` | Concatenates values from multiple rows into a single string, separated by commas. | `SELECT GROUP_CONCAT(name) FROM students;` |
| `STDDEV(column_name)` | Calculates the standard deviation of a numeric column. | `SELECT STDDEV(salary) FROM employees;` |
| `VARIANCE(column_name)` | Returns the variance of a numeric column. | `SELECT VARIANCE(salary) FROM employees;` |
| `BIT_AND(column_name)` | Performs a bitwise AND operation on all values in a column. | `SELECT BIT_AND(value) FROM table_name;` |
| `BIT_OR(column_name)` | Performs a bitwise OR operation on all values in a column. | `SELECT BIT_OR(value) FROM table_name;` |
| `BIT_XOR(column_name)` | Performs a bitwise XOR operation on all values in a column. | `SELECT BIT_XOR(value) FROM table_name;` |
| `FIRST()` | Returns the first value in a group (non-standard, MySQL-specific function). | `SELECT FIRST(price) FROM products;` |
| `LAST()` | Returns the last value in a group (non-standard, MySQL-specific function). | `SELECT LAST(price) FROM products;` |

---

## **7️⃣ Subqueries**  

| Command | Description | Example |
|---------|-------------|---------|
| **Subquery inside `WHERE`** | Filters records based on the result of another query, often with operators like `IN`, `EXISTS`, `ANY`, or `ALL`. | `SELECT name FROM students WHERE id IN (SELECT student_id FROM enrollments WHERE course = 'Math');` |
| **Subquery inside `FROM`** | Uses a subquery as a temporary table (also called a derived table or inline view) in the `FROM` clause. | `SELECT AVG(salary) FROM (SELECT salary FROM employees WHERE department = 'IT') AS temp;` |
| **Subquery inside `SELECT`** | Uses a subquery to calculate or retrieve values in the `SELECT` statement. | `SELECT name, (SELECT MAX(salary) FROM employees WHERE department = 'IT') AS max_salary FROM students;` |
| **Correlated Subquery** | A subquery that refers to columns from the outer query, meaning it is executed once for each row of the outer query. | `SELECT name FROM students s WHERE EXISTS (SELECT 1 FROM enrollments e WHERE e.student_id = s.id AND e.course = 'Math');` |
| **Subquery inside `HAVING`** | Filters grouped records using a subquery, often in combination with aggregate functions. | `SELECT department, COUNT(*) FROM employees GROUP BY department HAVING COUNT(*) > (SELECT COUNT(*) FROM employees WHERE department = 'HR');` |
| **Subquery with `IN`** | Compares a value with the results of a subquery, typically returning true if the value is found in the list of results from the subquery. | `SELECT name FROM students WHERE id IN (SELECT student_id FROM enrollments WHERE course = 'Math');` |
| **Subquery with `ANY`** | Compares a value to the set of values returned by the subquery. If the comparison is true for any value, the result is true. | `SELECT name FROM students WHERE score > ANY (SELECT score FROM students WHERE course = 'Math');` |
| **Subquery with `ALL`** | Compares a value to all the values returned by the subquery. If the comparison is true for all values, the result is true. | `SELECT name FROM students WHERE score > ALL (SELECT score FROM students WHERE course = 'Math');` |
| **Subquery with `EXISTS`** | Returns true if the subquery returns any rows. Typically used to check if there are any matching rows in the subquery. | `SELECT name FROM students WHERE EXISTS (SELECT 1 FROM enrollments WHERE enrollments.student_id = students.id AND enrollments.course = 'Math');` |
| **Scalar Subquery** | A subquery that returns a single value (a single row and column). Often used in `SELECT`, `WHERE`, or `HAVING` clauses. | `SELECT name, (SELECT MAX(salary) FROM employees WHERE department = 'IT') AS max_salary FROM students;` |
| **Subquery with `NOT IN`** | Compares a value to the results of a subquery and returns true if the value is not in the set of values returned by the subquery. | `SELECT name FROM students WHERE id NOT IN (SELECT student_id FROM enrollments WHERE course = 'Math');` |
| **Subquery with `NOT EXISTS`** | Returns true if the subquery does not return any rows. Often used to check the absence of rows in the subquery. | `SELECT name FROM students WHERE NOT EXISTS (SELECT 1 FROM enrollments WHERE enrollments.student_id = students.id AND enrollments.course = 'Math');` |

---

## **8️⃣ Indexing & Optimization**  

| Command | Description | Example |
|---------|-------------|---------|
| **`CREATE INDEX index_name ON table(column);`** | Creates an index on a specified column in a table to speed up query performance, especially for searches and joins. | `CREATE INDEX idx_name ON students(name);` |
| **`DROP INDEX index_name ON table;`** | Deletes an existing index from a table. | `DROP INDEX idx_name ON students;` |
| **`EXPLAIN query;`** | Shows the query execution plan, helping analyze how MySQL processes the query and if indexes are being used effectively. | `EXPLAIN SELECT * FROM students WHERE age > 18;` |
| **`SHOW INDEX FROM table;`** | Displays information about the indexes on a specified table. | `SHOW INDEX FROM students;` |
| **`ALTER TABLE table ADD INDEX index_name (column);`** | Adds an index to an existing table on a specific column. | `ALTER TABLE students ADD INDEX idx_name (name);` |
| **`ALTER TABLE table DROP INDEX index_name;`** | Removes an index from a table. | `ALTER TABLE students DROP INDEX idx_name;` |
| **`CREATE UNIQUE INDEX index_name ON table(column);`** | Creates a unique index, ensuring that no two rows have the same value for the indexed column(s). | `CREATE UNIQUE INDEX idx_unique_name ON students(name);` |
| **`CREATE FULLTEXT INDEX index_name ON table(column);`** | Creates a full-text index for performing full-text searches on the specified column. | `CREATE FULLTEXT INDEX idx_fulltext_name ON articles(title, content);` |
| **`OPTIMIZE TABLE table;`** | Reorganizes the table and optimizes its indexes. This helps reclaim space and improve performance after large insertions or deletions. | `OPTIMIZE TABLE students;` |
| **`ANALYZE TABLE table;`** | Analyzes the table for index statistics and updates the index information. Helps improve query optimization. | `ANALYZE TABLE students;` |
| **`CHECK TABLE table;`** | Checks the integrity of a table, which can help in identifying issues with indexes or data corruption. | `CHECK TABLE students;` |
| **`REPAIR TABLE table;`** | Repairs a corrupted table by fixing issues with indexes or table structure. | `REPAIR TABLE students;` |

---

## **9️⃣ Transactions (Rollback & Commit)**  

| Command | Description | Example |
|---------|-------------|---------|
| **`START TRANSACTION;`** | Begins a new transaction, allowing multiple SQL statements to be executed together as a single unit. Changes are not saved until a `COMMIT` is issued. | `START TRANSACTION;` |
| **`SAVEPOINT savepoint_name;`** | Creates a savepoint within the transaction, allowing you to roll back to this point without affecting the entire transaction. | `SAVEPOINT sp1;` |
| **`ROLLBACK TO savepoint_name;`** | Rolls back the transaction to a specific savepoint. Any changes made after the savepoint will be undone, but changes made before the savepoint will remain. | `ROLLBACK TO sp1;` |
| **`COMMIT;`** | Commits the transaction, making all changes made during the transaction permanent in the database. | `COMMIT;` |
| **`ROLLBACK;`** | Rolls back the entire transaction, undoing all changes made since the `START TRANSACTION;`. | `ROLLBACK;` |

---

## **🔟 User Management & Security**  

| Command | Description | Example |
|---------|-------------|---------|
| **`CREATE USER 'username'@'host' IDENTIFIED BY 'password';`** | Creates a new user with a specified password and assigns access from a specific host. | `CREATE USER 'john'@'localhost' IDENTIFIED BY '12345';` |
| **`GRANT privileges ON database.* TO 'username'@'host';`** | Grants specific privileges (e.g., `SELECT`, `INSERT`, `ALL PRIVILEGES`) to a user on a specific database. | `GRANT ALL PRIVILEGES ON school.* TO 'john'@'localhost';` |
| **`REVOKE privileges ON database.* FROM 'username'@'host';`** | Revokes specific privileges from a user on a particular database. | `REVOKE SELECT ON school.* FROM 'john'@'localhost';` |
| **`DROP USER 'username'@'host';`** | Deletes a user from the database system. | `DROP USER 'john'@'localhost';` |
| **`SHOW GRANTS FOR 'username'@'host';`** | Displays the privileges assigned to a specific user. | `SHOW GRANTS FOR 'john'@'localhost';` |
| **`ALTER USER 'username'@'host' IDENTIFIED BY 'new_password';`** | Changes the password for an existing user. | `ALTER USER 'john'@'localhost' IDENTIFIED BY 'newpassword123';` |
| **`CREATE ROLE 'role_name';`** | Creates a new role, which can be assigned to multiple users to group privileges together. | `CREATE ROLE 'admin_role';` |
| **`GRANT 'role_name' TO 'username'@'host';`** | Grants a role to a user, which allows them to inherit the privileges of the role. | `GRANT 'admin_role' TO 'john'@'localhost';` |
| **`SET DEFAULT ROLE 'role_name' TO 'username'@'host';`** | Sets a default role for a user, which will automatically be assigned when they log in. | `SET DEFAULT ROLE 'admin_role' TO 'john'@'localhost';` |
| **`DROP ROLE 'role_name';`** | Deletes a role from the database. | `DROP ROLE 'admin_role';` |
| **`SHOW USERS;`** | Lists all users in the MySQL database system. (Not a native command in all MySQL versions, but can be simulated in some systems). | `SHOW USERS;` |

---

## **#️⃣ View**
| Command | Description | Example |
|---------|------------|---------|
| `SHOW FULL TABLES WHERE Table_type = 'VIEW';` | Lists all views in the selected database. | `SHOW FULL TABLES WHERE Table_type = 'VIEW';` |
| `CREATE VIEW view_name AS SELECT ...;` | Creates a new view based on a SELECT query. | `CREATE VIEW student_view AS SELECT id, name FROM students;` |
| `SHOW CREATE VIEW view_name;` | Shows the SQL statement that creates the view. | `SHOW CREATE VIEW student_view;` |
| `SELECT * FROM view_name;` | Queries data from the view (just like a regular table). | `SELECT * FROM student_view;` |
| `DROP VIEW view_name;` | Deletes an existing view. | `DROP VIEW student_view;` |
| `ALTER VIEW view_name AS SELECT ...;` | Alters an existing view (redefines it with a new SELECT query). | `ALTER VIEW student_view AS SELECT id, name, age FROM students;` |
| `RENAME VIEW old_view_name TO new_view_name;` | Renames an existing view. | `RENAME VIEW student_view TO student_info_view;` |
| `CREATE OR REPLACE VIEW view_name AS SELECT ...;` | Creates or replaces an existing view. If the view exists, it is replaced. | `CREATE OR REPLACE VIEW student_view AS SELECT id, name FROM students WHERE age > 18;` |

## **🔚 Backup & Restore**  

| Command | Description | Example |
|---------|-------------|---------|
| **`mysqldump -u user -p database_name > backup.sql`** | Backs up a database into a SQL file, which contains all the database schema and data. | `mysqldump -u root -p school > backup.sql` |
| **`mysql -u user -p database_name < backup.sql`** | Restores a database from a SQL backup file, re-creating the database schema and populating it with data. | `mysql -u root -p school < backup.sql` |

---

💡 **Pro Tip:** Mastering these commands will help you perform CRUD operations, optimize queries, manage databases, and ensure security in MySQL.  