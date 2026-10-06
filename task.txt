answers:

1. DELETE = remove selected rows
    TRUNCATE = clear the whole table
   DROP = delete the table itself


   2.
   ```
   create table employee(
   empid auto_increment primary key,
   name varchar(255),
   salary int,
   department_id int
   )
   ```
   3. by using alter query we can add new column
   ```
   alter table employee
   add email varchar(255);
   ```

   4.
   ```
   alter table employees
   modify salary decimal (10,2);

   ```

   5.
   ```
   alter table employees
   rename column old_name to new_name;
   ```

   6.
   ```
   ALTER TABLE employees
   RENAME TO staff;
   ```
   7.
```
ALTER TABLE employees
DROP COLUMN email;
```

8.  
```
CREATE TABLE employees (
    id INT,
    name VARCHAR(100),
    salary DECIMAL(10,2),
    PRIMARY KEY (id)
);
```

14. 
truncate remove all rows from the table, but the table remains.
table structure stays the same
table existed in database
we cannot roll back nthe data after delete
```
TRUNCATE TABLE employees;
```

15. 
**Difference between DROP TABLE and TRUNCATE TABLE**

**TRUNCATE TABLE**

1.Deletes all rows from the table
2.Keeps the table structure
3.Keeps the table name and schema
4.cannot rollback the data


**DROP TABLE**

1.Deletes the entire table from the database
2.Removes the table structure, columns, constraints, and data
3.The table no longer exists
4.cannot rollback the data

9. not null means the column must contain a value when inserying a rows
```
CREATE TABLE employees (
    id INT NOT NULL,
    name VARCHAR(255) NOT NULL,
    department VARCHAR(50) NOT NULL
);
```
10. unique query represent a column must contains unique values
```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    email VARCHAR(100) UNIQUE,
    name VARCHAR(100)
);
```
here email must be unique across all the rows

12.
```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    salary DECIMAL(10,2),
    CHECK (salary > 0)
);
```

16.
```
INSERT INTO employees (employee_id, name, department_id, salary)
VALUES (1, 'mansi', 10, 50000);
```

