# Experiment 2: DDL Commands
```
LOKESH S
212224230143
```
## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="1151" height="527" alt="image" src="https://github.com/user-attachments/assets/e081a08a-020f-442c-b0ad-e904335c2a5e" />


```sql
Create TABLE Customers(
CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME);
```

**Output:**
<img width="1267" height="449" alt="image" src="https://github.com/user-attachments/assets/ac906078-ef46-4604-90e0-5dd5626a783e" />


**Question 2**
---
<img width="1080" height="519" alt="image" src="https://github.com/user-attachments/assets/a3844996-ed63-4f84-a9aa-97d70787a23a" />

```sql
CREATE TABLE Employees(
EmployeeID INTEGER,
FirstName TEXT,
LastName TEXT,
HireDate DATE);
```

**Output:**
<img width="1268" height="363" alt="image" src="https://github.com/user-attachments/assets/3d1d4651-a969-4e21-817e-0ddf4e499b08" />


**Question 3**
---
<img width="1252" height="301" alt="image" src="https://github.com/user-attachments/assets/b0216554-b26d-414d-8ee3-fb90ae3ffa7d" />


```sql
INSERT INTO Products(ProductID,Name,Category,Price,Stock) VALUES (101,'Laptop','Electronics',1500,50);
```

**Output:**
<img width="1263" height="281" alt="image" src="https://github.com/user-attachments/assets/da12cc4b-9d61-4579-b375-bb56a1c405cd" />


![Output3](output.png)

**Question 4**
---
<img width="1090" height="469" alt="image" src="https://github.com/user-attachments/assets/9e10a63e-11e4-4770-b872-d4bd54b7cca1" />



```sqlCREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE);
```

**Output:**
<img width="1262" height="403" alt="image" src="https://github.com/user-attachments/assets/7e4dff29-db20-4c22-8143-9bf4bc91b742" />


**Question 5**
---
<img width="1207" height="654" alt="image" src="https://github.com/user-attachments/assets/ee11bf12-a111-4291-868d-b4df78f0b5e5" />

-- Paste Question 5 here

```sql
ALTER TABLE Student_details
ADD Mobilenumber number
```

**Output:**
<img width="1259" height="387" alt="image" src="https://github.com/user-attachments/assets/5558fe50-3128-4c7c-945a-127512b66981" />



**Question 6**
---
<img width="1263" height="254" alt="image" src="https://github.com/user-attachments/assets/29edc204-5497-4c20-9026-926fa28fbe82" />



```sql
INSERT INTO Products(PRODUCTID ,Name, Category, Price, Stock) VALUES (104, 'Tablet', 'Electronics',100,50);
```

**Output:**
<img width="1268" height="301" alt="image" src="https://github.com/user-attachments/assets/2e7f950b-83d9-4e0a-ae2a-0b87e3ff4b1f" />



**Question 7**
---
<img width="1251" height="361" alt="image" src="https://github.com/user-attachments/assets/15dc917c-4b30-49ad-b3f9-a32dc4f2aeec" />

```sql
CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT UNIQUE NOT NULL,
    Price REAL CHECK (Price > 0),
    StockQuantity INTEGER CHECK (StockQuantity >= 0)
);

```

**Output:**
<img width="1256" height="311" alt="image" src="https://github.com/user-attachments/assets/8deffb76-efa2-488d-a876-61037ff20c62" />



**Question 8**
---
<img width="1095" height="458" alt="image" src="https://github.com/user-attachments/assets/3f1076e0-6c44-48cc-a4fc-a889c889f7f2" />



```sql
CREATE TABLE Tasks (
    TaskID INTEGER,
    TaskName TEXT,
    DueDate DATE
);

```

**Output:**
<img width="1262" height="366" alt="image" src="https://github.com/user-attachments/assets/04913edf-4518-4cbd-b1eb-04bbf5ab5972" />



**Question 9**
---
<img width="1028" height="561" alt="image" src="https://github.com/user-attachments/assets/13e821cd-3679-47b5-9f7a-64e90dd854c6" />



```sql
INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
SELECT RollNo, Name, Gender, Subject, MARKS
FROM Archived_students;
```

**Output:**
<img width="1257" height="266" alt="image" src="https://github.com/user-attachments/assets/c1f11f42-4c12-4d17-a512-5aa72d00ce7a" />


**Question 10**
---
<img width="1269" height="335" alt="image" src="https://github.com/user-attachments/assets/96c51e11-c074-4fd7-a6e0-7d3e9183a945" />



```sql
ALTER TABLE Student_details
ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';

```

**Output:**

<img width="1253" height="221" alt="image" src="https://github.com/user-attachments/assets/add9437d-43ae-4bfe-971c-d257dd833023" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
