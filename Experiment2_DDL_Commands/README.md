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
![image](https://github.com/user-attachments/assets/7ff5e5eb-40e8-4201-84c2-ec8cf4369ac8)


```sql
CREATE TABLE Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE
);
```

**Output:**

![image](https://github.com/user-attachments/assets/cd08c493-ffd9-4139-bfa3-6c9d1db277d4)


**Question 2**
---

![image](https://github.com/user-attachments/assets/b2b70941-a300-4ec3-9c51-98d7f83728b4)



```sql
CREATE TABLE Locations(
LocationID INTEGER,
LocationName  TEXT,
Address TEXT
);
```

**Output:**


![image](https://github.com/user-attachments/assets/e00c1eec-5043-4446-a2c8-ee8afaa41e0a)



**Question 3**
---
![image](https://github.com/user-attachments/assets/b01549f5-0ccc-4af2-bd92-cc827e67edd0)


```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER,
icom_id TEXT CHECK(LENGTH(icom_id)=4),
FOREIGN KEY (icom_id)REFERENCES company(com_id)
ON UPDATE CASCADE
ON DELETE CASCADE
);
```

**Output:**

![image](https://github.com/user-attachments/assets/3d50fd89-2e01-4068-b9cf-010ad7fe96ea)

**Question 4**
---

![image](https://github.com/user-attachments/assets/621d7480-bc24-4506-bb99-d1aac375ad2a)



```sql
CREATE TABLE Orders(
    OrderID INTEGER PRIMARY KEY,
    OrderDate DATE NOT NULL,
    CustomerID INTEGER,
    FOREIGN KEY(CustomerID)REFERENCES Customers(CustomerID)
);

```

**Output:**

![image](https://github.com/user-attachments/assets/93de3a8e-37e5-44a8-a83d-01c0e7e8978b)




**Question 5**
---

![image](https://github.com/user-attachments/assets/6190693e-8b8b-405c-b284-ed46bca8afe3)



```sql
ALTER TABLE employee
ADD COLUMN designation varchar(50);
```

**Output:**

![image](https://github.com/user-attachments/assets/f74ff937-f633-44df-a123-cb30ff97f408)



**Question 6**
---
![image](https://github.com/user-attachments/assets/54f909c0-80cd-4287-86ed-c507ee6cd9ba)


```sql
ALTER TABLE employee ADD COLUMN department_id INTEGER;
ALTER TABLE employee ADD COLUMN manager_id INTEGER DEFAULT NULL;
```

**Output:**

![image](https://github.com/user-attachments/assets/4b8e3261-5588-4bdc-a11e-7a04b5c42f99)


**Question 7**
---
![image](https://github.com/user-attachments/assets/2f08110e-1fcc-454a-ab90-c4c61d5068f8)


```sql
CREATE TABLE Products(
ProductID  INTEGER PRIMARY KEY,
ProductName INTEGER NOT NULL,
Price REAL CHECK(Price>0),
Stock INTEGER CHECK(Stock>=0)
)
```

**Output:**

![image](https://github.com/user-attachments/assets/21749ddf-4c0a-4eaf-9242-9f320ed8df43)


**Question 8**
---

![image](https://github.com/user-attachments/assets/153008f6-4fde-4b1f-9835-9065a46cf853)


```sql
ALTER TABLE customer
ADD COLUMN discount DECIMAL(5,2);
```

**Output:**


![Screenshot 2025-04-29 141257](https://github.com/user-attachments/assets/83cbf050-ee72-4450-bb1c-0677e72f0c4b)


**Question 9**
---
![image](https://github.com/user-attachments/assets/91deda84-035c-4510-a6db-44d30af6e1bc)


```sql
ALTER TABLE Student_details ADD COLUMN MobileNumber NUMBER;
ALTER TABLE Student_details ADD COLUMN Address VARCHAR(100);
```

**Output:**

![image](https://github.com/user-attachments/assets/4a9640f5-d1d1-4533-90ed-362e3413092e)

**Question 10**
---


![Screenshot 2025-04-29 141558](https://github.com/user-attachments/assets/771b2889-7e46-4fd7-8f12-9e0fd09f5a29)


```sql
CREATE TABLE Products(
ProductID INTEGER PRIMARY KEY,
ProductName TEXT UNIQUE NOT NULL,
Price REAL CHECK (Price>0),
StockQuantity INTEGER CHECK (StockQuantity>=0)
);
```

**Output:**


![Screenshot 2025-04-29 141615](https://github.com/user-attachments/assets/72da2449-3183-4778-8ddf-5d2b2341645a)




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
