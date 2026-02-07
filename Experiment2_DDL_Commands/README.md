# Experiment 2: DDL Commands

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
<img width="1232" height="595" alt="image" src="https://github.com/user-attachments/assets/b3fdde58-8101-4a6b-9378-3fa00a6bb901" />


```
ALTER TABLE customer
ADD discount DECIMAL(5,2);
```

**Output:**

<img width="1236" height="449" alt="image" src="https://github.com/user-attachments/assets/6f4fb72e-d8d6-4efa-9166-48eec23c0735" />


**Question 2**
---
<img width="1403" height="371" alt="image" src="https://github.com/user-attachments/assets/024ae1a8-c713-4991-b3e8-f469e11f5b9f" />


```
CREATE TABLE ProjectAssignments (
    AssignmentID   INTEGER PRIMARY KEY,
    EmployeeID     INTEGER,
    ProjectID      INTEGER,
    AssignmentDate DATE NOT NULL,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
    FOREIGN KEY (ProjectID)  REFERENCES Projects(ProjectID)
);
```

**Output:**

<img width="1233" height="374" alt="image" src="https://github.com/user-attachments/assets/70100131-d7f5-4150-b4ab-2ce9ea303431" />

**Question 3**
---
<img width="1398" height="258" alt="image" src="https://github.com/user-attachments/assets/cda1cd98-128d-4bd9-a673-6e2a9376ae32" />

```sql
ALTER TABLE customer
ADD COLUMN email VARCHAR(100);
```

**Output:**

<img width="1651" height="324" alt="image" src="https://github.com/user-attachments/assets/b82c54b9-fb09-410d-97a7-a9d49c343cfe" />

**Question 4**
---
<img width="1523" height="321" alt="image" src="https://github.com/user-attachments/assets/f696ba50-ae47-4c6c-977b-297d3172e69d" />


```
CREATE TABLE contacts (
    contact_id  INTEGER PRIMARY KEY,
    first_name  TEXT NOT NULL,
    last_name   TEXT NOT NULL,
    email       TEXT,
    phone       TEXT NOT NULL CHECK (length(phone) >= 10)
);
```

**Output:**

<img width="1883" height="293" alt="image" src="https://github.com/user-attachments/assets/f32fb280-d44d-41db-9390-c91a04280830" />


**Question 5**
---
<img width="1499" height="818" alt="image" src="https://github.com/user-attachments/assets/8a63c717-f004-44f2-acea-12d6f177be96" />

```sql
INSERT INTO Student_details (RollNo, Name, Gender, Subject, Marks)
SELECT RollNo, Name, Gender, Subject, Marks
FROM Archived_students;
```

**Output:**

<img width="1903" height="443" alt="image" src="https://github.com/user-attachments/assets/5f8c14af-133b-4a5d-bd48-c3a0619cb653" />


**Question 6**
---
<img width="1736" height="330" alt="image" src="https://github.com/user-attachments/assets/d6035eb3-b12a-417b-bf81-936a350cb67f" />


```sql
INSERT INTO Books (ISBN, Title, Author, Publisher, Year)
VALUES ('978-1234567890', 'Data Science Essentials', 'Jane Doe', 'TechBooks', 2024);
```

**Output:**

<img width="1899" height="344" alt="image" src="https://github.com/user-attachments/assets/082fd26d-435f-4220-975a-6b9b45c0b437" />


**Question 7**
---
<img width="1710" height="577" alt="image" src="https://github.com/user-attachments/assets/3b501233-82e7-494f-8c7a-3f20c8447667" />


```sql
CREATE TABLE products (
    product_id    INTEGER PRIMARY KEY,
    product_name  TEXT NOT NULL,
    list_price    DECIMAL(10,2) NOT NULL,
    discount      DECIMAL(10,2) NOT NULL DEFAULT 0,
    CHECK (
        list_price >= discount
        AND discount >= 0
        AND list_price >= 0
    )
);
```

**Output:**

<img width="1896" height="329" alt="image" src="https://github.com/user-attachments/assets/c4f0076d-7bda-4073-a102-9856054f7b73" />


**Question 8**
---
<img width="1435" height="547" alt="image" src="https://github.com/user-attachments/assets/e35723b7-c05d-41e3-8747-15fe6fe23dd5" />

```sql
CREATE TABLE Orders (
    OrderID    INTEGER,
    OrderDate  TEXT,
    CustomerID INTEGER
);
```

**Output:**

<img width="1742" height="401" alt="image" src="https://github.com/user-attachments/assets/44a24914-7a2a-45b8-8ba4-25527bec87f2" />

**Question 9**
---
<img width="1874" height="428" alt="image" src="https://github.com/user-attachments/assets/65b1a72b-2020-4f89-a896-503c6df3826e" />


```sql
CREATE TABLE Orders (
    OrderID     INTEGER PRIMARY KEY,
    OrderDate   DATE NOT NULL,
    CustomerID  INTEGER,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

**Output:**

<img width="1878" height="294" alt="image" src="https://github.com/user-attachments/assets/fe997036-ce96-47c4-84b1-a7358ebcbc08" />


**Question 10**
---
<img width="1482" height="616" alt="image" src="https://github.com/user-attachments/assets/2e3c9da3-6ec3-4dbe-a3d4-73904a89f990" />

```sql
INSERT INTO Employee (EmployeeID, Name, Position, Department, Salary)
VALUES 
(2, 'John Smith', 'Developer', 'IT', 75000),
(3, 'Anna Bell', 'Designer', 'Marketing', 68000);
```

**Output:**

<img width="1762" height="384" alt="image" src="https://github.com/user-attachments/assets/fd02f36d-3b99-4601-9d61-dcc518c0564b" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
