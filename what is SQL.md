# what is sql?
1. SQL stands for **structured query language**
2. SQL used for create database | tables structured
3. SQL is a case insensitive query language
**example**
'''
insert |INSERT | Insert

'''

4. SQL is used to create structured of datatbase and tables via its **query or command**
5. SQL create logics and functional
6. SQL execute query 
7. SQL create views or index to fast load data
8. SQL create a structured data
  **structured data formate column and rows**
  **example**

  | id       | name      | age        |   addresss |
  |----------|-----------|------------|------------|
  |1         |   mansi   |      25    |       rjt  |
|2           |  mansi    |    25      |  rjt       |  |2            |  mansi    |    25      |  rjt       |  |2            |  mansi    |    25      |  rjt       |  


# types of SQL query or commands

1. **DDL (data definition language)**
2.**DML (data manipulation language)**
3. **DQL(data query language)**
4. **TCL( transactional control language**)

# DDL (DATA DEFINITION LANGUAGE)
!. STANDS FOR DATA DEFINITION LANGUAGE
2. CREATE AN STRUCTURED OF database and tables
3. rename tables
4. update|add|modify| drop data in table or column in tables
5. truncate data from tables

**DDLquery are**

1. create
2. alter
3. rename
4. drop
5. truncate
6. change

**How to create database and table structured**

1. create a database

**syntax**

```
create database databasename;
```
*example*

```
create database data_analytics_11am
```
2. create a table structured

**syntax**

```
create table tablename
```
(
  id datatype(size) auto_increment primary key,
  columnname datatype (size),
  .
  .
  .
  .
  .
  .
  columnname datatype (size)
);

**examples**

```
cretae table tbl_employee(
  empid int auto_increment primary key,
  name varchar(255),
  age int,
  address text,
  salary decimal(10,2),
  city varchar(200)
);


  # What are datatypes and column sizes in tables?

  A **datatype** defines what kind of value a column can store, such as text, a number, a date, or a true\false value.

  ## Example

  ```sql
  CREATE TABLE employees (
    empid INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT,
    address TEXT,
    salary DECIMAL(10,2),
    city VARCHAR(50),
    department VARCHAR(100),
    is_active BOOLEAN DEFAULT TRUE,
    created_at DATETIME
  );
  ```

  In this example:

  - `name VARCHAR(100)` allows a name of up to 100 characters.
  - `salary DECIMAL(10,2)` allows 10 total digits, with 2 digits after the decimal point.
  - `age INT` stores a whole number and does not require a character size.
  - `address TEXT` stores longer text without declaring a size such as `TEXT(500)`.

# SQL Data Types Table

| Data Type | Used For | Example | Size/Notes |
|---|---|---|---|
| `INT` | Whole numbers | `25`, `1000` | Usually 4 bytes |
| `BIGINT` | Large whole numbers | `9876543210` | Larger than `INT` |
| `SMALLINT` | Small integers | `10`, `500` | Smaller than `INT` |
| `TINYINT` | Very small integers | `1`, `255` | Small range |
| `FLOAT` | Approximate decimal numbers | `12.5` | Less precise |
| `DOUBLE` | Large decimal values | `123.456` | More precise than `FLOAT` |
| `DECIMAL(p,s)` | Exact decimal values | `9999.99` | Used for money |
| `CHAR(n)` | Fixed-length text | `CHAR(5)` | Always fixed length |
| `VARCHAR(n)` | Variable-length text | `VARCHAR(50)` | Up to n characters |
| `TEXT` | Long text | `address` | Large text data |
| `DATE` | Date only | `2026-09-25` | YYYY-MM-DD |
| `TIME` | Time only | `14:30:00` | HH:MM:SS |
| `DATETIME` | Date + time | `2026-09-25 14:30:00` | Includes both |
| `TIMESTAMP` | Date + time record | `2026-09-25 14:30:00` | Often used for updates |
| `BOOLEAN` | True/False | `TRUE` | Logical value |
| `ENUM` | Predefined list | `ACTIVE`, `INACTIVE` | Only allowed values |
| `JSON` | Structured data | `{"name":"Mansi"}` | Stores JSON object |
| `BLOB` | Binary data | image/file data | Stores raw binary |

## Quick Summary

- `INT`, `BIGINT`, `SMALLINT` = numbers
- `VARCHAR`, `CHAR`, `TEXT` = text
- `DATE`, `TIME`, `DATETIME`, `TIMESTAMP` = date/time
- `DECIMAL`, `FLOAT`, `DOUBLE` = decimal numbers
- `BOOLEAN`, `ENUM`, `JSON`, `BLOB` = special types

```sql
CREATE TABLE student (
    id INT,
    name VARCHAR(50),
    age INT,
    marks DECIMAL(5,2),
    dob DATE,
    is_active BOOLEAN
);
```
 # alter;
 1. alter is used to add new column after create a table
 2. alter is used to modify|rename|or delete a column name is table
 3. alter ia used to add unique key of any column name

 **examples**
1. table tbl_employee add country varchar(255)
2. alter table tbl_employee add state varchar(255)
3. alter table tbl_employee add city varchar(255);
4. alter table tbl_employee add photo blob after name;
5. ALTER TABLE tbl_users
ADD COLUMN country VARCHAR(255) AFTER pincode,
ADD COLUMN state VARCHAR(255) AFTER country,
ADD COLUMN city VARCHAR(255) AFTER state;
6. alter table tbl_users change photo  upload_photo blob;
7. alter table tbl_users drop created_at;
8. alter table tbl_users add UNIQUE(`email`);

# rename table:
1. after create table via SQL we can changed a table name via **rename**
  **examples**
  ```
   rename table tbl_country to country
   or
   rename table tbl_users to users

  ```

# rename database name :

  ```  
 CREATE DATABASE IF NOT EXISTS data_analytics_db_11am_tts;
 DROP DATABASE IF EXISTS data_analytics_db_11am;

  ```
# change :

1. change is a **keyword** that can be changed the column name of table

**examples**

```
alter table employee change photo upload_photo blob;
```
  

# drop : 

1. drop is used to drop database after drop we can not rollback 
2. drop is also used to drop table after drop we never rollback data or its structures 
3. drop is also delete a column name 

# note : after drop we never rollback

**examples**

```
drop database data_analytics_db_11am_tts;
or
drop table users;
or 
drop table users
or
alter table users drop upload_photo;
or 
ALTER TABLE users
DROP COLUMN `state`,
DROP COLUMN `city`;

```

# truncate :

1. truncate is used to empty all data from tables 
2. after truncate we never rollback data from tables

**examples**

```
truncate table users;
or 
truncate table review
```
# after truncate we never rollback data

# **DML (data manipulation language)**

1. DMl is used to insert single data or multiple data in tables 
2. DMl is used to delete all data or particular one data or alternate data or range of data from tables
3. DMl is used to update single data or multiple data in tables 

**examples**

1. **insert a single data or row**
**examples**

```
insert into country (cname,created_at) values('india','29/09/2026')
```

2. **insert a multiple data or row**
**examples**

```
insert into country (cname,created_at) values('usa','29/09/2026'),('australia','29/09/2026'),('uk','29/09/2026'),('iran','29/09/2026')

or
insert into country (cname,created_at) values('usa','29/09/2026'),('australia','29/09/2026'),('uk','29/09/2026'),('iran','29/09/2026')
or

insert into country values(null,'canada','29/09/2026'),(null,'thailand','29/09/2026'),(null,'china','29/09/2026'),(null,'japan','29/09/2026')

or

INSERT into employee values(null, 'smith','smith.jpg','s254545',21,14500,'IT','150 rajkot','india','gujrat','rajkot'),(null, 'rushikesh','rushi.jpg','r254545',22,15500,'IT','150 rajkot','india','gujrat','rajkot'),(null, 'priyanshu','p.jpg','p254545',24,16500,'CSE','150 rajkot','india','gujrat','junagad'),(null, 'ashtha','astha.jpg','a254545',25,16500,'CSE','150 rajkot','india','gujrat','jamanagar'),(null, 'mansi','mansi.jpg','m254545',24,18500,'IT','150 feet ring road lucknow','india','uttar pradesh','lucknow')

```
   
**update data or row**

1. update a single data 
   **examples**
   ```
   update country set cname='america' where cid=9;
   or
   update country set cname='bharat', created_at='27/09/2026' where cid=1;

   ```

**delete data or rows**

1. delete all data 
   **examples**
   ```
   delete from country;
   ```
2. delete one  data from table 
   **examples**
   ```
   delete from country where cid=2;
   ```

3. delete one  data from table via its name 
   **examples**
   ```
   delete from country where cname='america';
   ```

4. delete alternate  data from table 
   **examples**
   ```
   delete from country where cid in (2,4,6);
   ```

5. delete range of   data from table 
   **examples**
   ```
   delete from country where cid between 100 and 255;
   ```


# DQL (data query language)
**DQL only used **select** keyword to fetch or retrieve data from tables


1. DQL is used to fetch or retrieve data from tables
2. DQL is used to fetch data from single table or multiple tables via join query
3. DQL is used to select data from tables using **select** keyword
4. DQL is also used to filter data from tables using **where** keyword
5. select is also used to fetch or filter data in order by ascending or descending order using **order by** keyword
6. select is also used to fetch or filter data in group by using **group by**
7. select is also used to select range of from tables using **between** keyword
8. select alternative data from tables using **in** keyword
9. select data from tables using **like** keyword it is also used to search data from tables using **%** and **_** keyword or wildcard
10. select data from tables using **distinct** keyword it is also used to fetch unique data from tables
11. select data from tables using **limit** keyword it is also used to fetch limited data from tables.
12. select data from tables using **join** keyword it is also used to fetch data from multiple tables via join query
13. select data from tables using **union** keyword it is also used to fetch data from multiple tables via union query
14. select data from tables using **subquery** keyword it is also used to fetch data from multiple tables via subquery

  **examples**
  ```
  subquery means query inside query
  
  ```
 15. select data from tables using **alias** keyword it is also used to fetch data from multiple tables via alias query

 **examples**
  ```
  alias means rename a column name or table name via select query
  alias used keyword **as** to rename a column name or table name

  ``` 

  16. select data from tables using **aggregate functions** keyword it is also used to fetch data from multiple tables via aggregate functions query

  **examples of aggrigate functions**
  ```
  1) max() - it is used to fetch maximum value from tables
  2) min() - it is used to fetch minimum value from tables
  3) sum() - it is used to fetch sum of values from tables
  4) avg() - it is used to fetch average of values from tables
  5) count() - it is used to fetch count of values from tables

  ```

  17. select used in scalar functions to fetch data from tables using **scalar functions** keyword it is also used to fetch data from multiple tables via scalar functions query

  **examples of scalar functions**
  ```
   1) upper() - it is used to convert data in uppercase from tables
   2) lower() - it is used to convert data in lowercase from tables
   3) length() - it is used to fetch length of data from tables
   4) round() - it is used to round the decimal values from tables
   5) now() - it is used to fetch current date and time from tables
   6) curdate() - it is used to fetch current date from tables
   7) curtime() - it is used to fetch current time from tables

   ```

18. select used in date functions to fetch data from tables using **date functions** keyword it is also used to fetch data from multiple tables via date functions query

  **examples of date functions**
  ```
   1) date() - it is used to fetch date from datetime values from tables
   2) time() - it is used to fetch time from datetime values from tables
   3) year() - it is used to fetch year from datetime values from tables
   4) month() - it is used to fetch month from datetime values from tables
   5) day() - it is used to fetch day from datetime values from tables
   6) datediff() - it is used to fetch difference between two dates from tables
   7) date_add() - it is used to add days, months, years to a date value in tables
   8) date_sub() - it is used to subtract days, months, years from a date value in tables

   ```
19. select used in string functions to fetch data from tables using **string functions** keyword it is also used to fetch data from multiple tables via string functions query

  **examples of string functions**
  ```
   1) concat() - it is used to concatenate two or more strings from tables
   2) substring() - it is used to fetch a substring from a string value in tables
   3) replace() - it is used to replace a substring with another substring in a string value in tables

   4) trim() - it is used to remove leading and trailing spaces from a string value in tables
   
   5) instr() - it is used to find the position of a substring in a string value in tables

   ```

20. select used in mathematical functions to fetch data from tables using **mathematical functions** keyword it is also used to fetch data from multiple tables via mathematical functions query

  **examples of mathematical functions**
  ```
   1) abs() - it is used to fetch absolute value of a number from tables

   2) ceil() - it is used to fetch the smallest integer greater than or equal to a number from tables
   
   3) floor() - it is used to fetch the largest integer less than or equal to a number from tables
   
   4) power() - it is used to fetch the power of a number from tables
   
   5) sqrt() - it is used to fetch the square root of a number from tables

   ```

   **examples of DQL query**

   1. select all data from table
   
   ```
   select * from tablename;
   or
   select * from employee;
   ```
   2. select particular column name from table
   
   ```
   select columnname from tablename;
   or
   select empid,name,age,salary from employee;

   ```

  3. select data of 1 rows 

    **where** keyword is used to filter data from tables

   ```
   select * from tablename where columnname=value;
   or
   select * from employee where name='mansi';
   or
   select * from employee where empid=1;
   or
   select * from employee where empid=1 and name='smith';
   or
   select * from employee where empid=1 or name='mansi';
   ```

# select range of data from tables using **between** keyword

   ```
   select * from employee where empid between 1 and 4;

   ```
# select alternative data from tables using **in** keyword

   ```
   select * from employee where empid in (2,3,5);
   or
   select * from employee where name in ('smith','mansi');
   or
   select * from employee where empid not in (2,3,5);
   or
   select * from employee where name not in ('smith','mansi');
   or
   select * from employee where age in (25,30,35);
   ```
# select data using limit keyword to fetch limited data from tables

   ```
   select * from employee limit 3;
   or
   select * from employee limit 4;
   or
   select * from employee limit 6;
   or
   select * from employee limit 1,4;
   or
   select * from employee limit 0,4;
   or
   select * from employee limit 7,8;
   ```
# select data using like keyword to fetch data from tables
  
  **like** keyword is used to search data from tables using **%** and **_** keyword or wildcard

   ```
   select * from employee where name like 'a%';
   or
   select * from employee where name like '%h';
   or
   select * from employee where name like '%h';
   or
   select * from employee where name like '%m%';
   or
   select * from employee where name like '%a%';
   or
   select * from employee where name like '_m%';
   or
   select * from employee where name like '____h';
   or
   select * from employee where name like '____%h';

   ```

**list out all types of keywords used in SQL query**

1. select
2. from
3. where
4. order by
5. group by
6. having
7. limit
8. distinct
9. in
10. between
11. like
12. join
13. union
14. subquery
15. alias
16. aggregate functions
17. scalar functions
18. date functions
19. string functions
20. mathematical functions
21. insert
22. update
13. delete
14. alter
15. rename
16. drop
17. truncate
18. create
19. change
20. add

# how to rename a column name in table using **alias** keyword

1. alias is used to rename a column name in table using **as** keyword

```
select name as employee_name from employee;
or
select empid, name as employee_name from employee;
or
select empid, name as employee_name, address as employee_address from employee;
or
select cname as country_name from tbl_country;

```

# select a range of data 

1. select * from country limit 0,15
2. select * from country where cid between 1 and 8;
3. select * from country where cname in ('bharat','usa','uk');

# SQL function 
 There are two types of sql function
1. Aggregate function
  
   - sum()
   - avg()
   - max()
   - min()
   - count()

2. scalar function 

   - first()
   - last()
   - lcase()
   - ucase()
   - now ()
   
**examples**

1. select sum(salary) as sum_of_salary from employee;
2. select sum(salary) as sum_of_salary from employee where empid in (1,4,5);
3. select sum(salary) as sum_of_salary from employee where empid limit 0,4;
4. select sum(salary) as sum_of_salary from employee where empid limit 0,4
5. select sum(salary) from employee where salary>17500 and salary < 20500;

6. select avg(salary) as avg_of_salary from employee;
7. select max(salary) as max_of_salary from employee
8. select min(salary) as min_of_salary from employee
9. select count(empid) as total_number_employee from employee

# group by :

 1. group by is used to filter data on group of columns there we used group by 

 2. **having** is a cluse that can be used with aggrigate function but always after **group by** 

 ```
 select sum(salary), department from employee GROUP by department;
 or
 select sum(salary), department from employee GROUP by department having department='IT';
  or
 select sum(salary), department from employee GROUP by department having department='CSE';
 or
 select sum(salary), department from employee GROUP by department having department='EC'; 

 ```

 # scalar function:

 1. select first (empid) from tbl_employee;
 2. select last (empid) from tbl_employee;
 3. select lcase (name) from tbl_employee;
 4. select ucase (name) from tbl_employee;
 1. select now () from tbl_employee;

 # what is difference b/w delete | truncate| drop

 **Difference between DELETE, TRUNCATE and DROP**

| Command | What it does | Can use WHERE? | Removes rows only or whole table? | Rollback | Important note |
|---|---|---:|---|---|---|
| `DELETE` | Deletes specific rows from a table | Yes | Only rows | Yes, if used before commit in a transaction | Keeps table structure |
| `TRUNCATE` | Deletes all rows from a table quickly | No | All rows from the table | Usually not easily reversible, and often auto-commits | Keeps table structure but resets data |
| `DROP` | Deletes the entire table or database | No | Whole table/database object | Not normally reversible | Removes structure permanently |

**Examples**

```sql
-- delete one row
DELETE FROM employee WHERE empid = 5;

-- delete all rows
DELETE FROM employee;

-- truncate table
TRUNCATE TABLE employee;

-- drop table
DROP TABLE employee;
```

**Summary**
- `DELETE` = remove selected records
- `TRUNCATE` = remove all records from table quickly
- `DROP` = remove the complete table or database

 # TCL :
 1. TCL stands transactional control language
 2. TCL is used to commit and rollback data from tables
 3. TCLis used to save data after delete
 4. TCL is used to rollback data after delete

# queries in TCL
1. commit
2. rollback

**commit**

1. commit used to save data after delete
2. commit is used in TCL

**QUERY OF COMMIT**
```
START TRANSACTION;
DELETE FROM tbl_country where cid=8;
commit;
```
**rollback**














 