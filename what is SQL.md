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

  A **datatype** defines what kind of value a column can store, such as text, a number, a date, or a true/false value.

  A **size** defines the maximum length or capacity of a value when the datatype supports a size. The meaning of size depends on the datatype:

  - `VARCHAR(100)` stores variable-length text up to 100 characters.
  - `CHAR(2)` stores fixed-length text of up to 2 characters.
  - `DECIMAL(10,2)` allows 10 total digits, including 2 digits after the decimal point. For example, `12345678.90`.
  - `INT` stores whole numbers. In modern MySQL, the optional number in `INT(n)` does not limit the number of digits; it is a display-width feature and is generally not needed.
  - `TEXT`, `DATE`, and `BOOLEAN` usually do not need a size.

  ## Common SQL datatypes

  | Column example | Datatype | Description |
  |---|---|---|
  | `empid` | `INT` | Stores whole numbers, such as employee IDs or ages |
  | `large_id` | `BIGINT` | Stores very large whole numbers |
  | `name` | `VARCHAR(255)` | Stores variable-length text up to 255 characters |
  | `country_code` | `CHAR(2)` | Stores fixed-length text, such as `IN` or `US` |
  | `description` | `TEXT` | Stores variable-length text without specifying a small size |
  | `notes` | `LONGTEXT` | Stores a very large amount of text |
  | `price` | `DECIMAL(10,2)` | Stores exact decimal values, useful for money |
  | `rating` | `FLOAT` | Stores approximate decimal or floating-point values |
  | `status` | `ENUM('active', 'inactive')` | Stores one value from a predefined list |
  | `is_active` | `BOOLEAN` | Stores a true or false value |
  | `birth_date` | `DATE` | Stores a date such as `2026-09-24` |
  | `created_at` | `DATETIME` | Stores a date and time |

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

 |column / Field	|Data Type|	Description|
 |........|..........|...........|
|name	|CHAR(0–255)|	Stores fixed-length character/string data. Intended for characters/text only.|
|name|	VARCHAR(0–255)|	Stores variable-length character/string data. Can contain letters, numbers, spaces, and special characters.|
|id	INT|	Stores whole numbers,| commonly used for IDs and numeric values.|
|bigint_id|	BIGINT	|Stores very large whole numbers, commonly used for large IDs|
|age	|TINYINT|	Stores small whole numbers, commonly used for values such as age.|
|amount|	DECIMAL(p,s)|	Stores exact decimal numbers, commonly used for money and financial values.|
|price|	FLOAT|	Stores approximate decimal/floating-point numbers.|
|percentage|	DOUBLE	|Stores approximate decimal numbers with higher precision than FLOAT.|
|is_active	|BOOLEAN|	Stores a true/false value.|
|status|	ENUM	|Stores one value from a predefined list of allowed values.|
|description	|TEXT|	Stores variable-length text without a small VARCHAR-style limit.|
|long_description|	LONGTEXT|	Stores very large amounts of text.|
|code|	CHAR(n)	|Stores fixed-length text. Useful for values with a known, consistent length, such as country codes.|
|email	|VARCHAR(255)|	Stores email addresses as variable-length text.|
|phone	|VARCHAR(20)	|Stores phone numbers. VARCHAR is preferred because phone numbers may contain +, spaces, -, etc.|
|url	|VARCHAR(2048)	|Stores website or URL strings.
date_of_birth	DATE	Stores a calendar date in YYYY-MM-DD format.|
|created_at|	DATETIME|	Stores date and time without timezone conversion.|
|updated_at|	TIMESTAMP|	Stores a date and time, commonly used for record creation/update timestamps.|
|time|	TIME	|Stores a time value such as 14:30:00.
year	YEAR	Stores a year value.|
|json_data|	JSON	|Stores structured JSON data.|
|binary_data|	BLOB|	Stores binary data such as files or raw bytes.|
|uuid	|CHAR(36)|	Stores a UUID string such as 550e8400-e29b-41d4-a716-446655440000.|

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
 
 