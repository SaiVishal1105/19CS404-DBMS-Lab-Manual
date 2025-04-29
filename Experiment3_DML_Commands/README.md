# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
![image](https://github.com/user-attachments/assets/9dd00853-53f3-4145-b258-d89df64b3f1f)

```sql
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS) VALUES(205,'Olivia Green','F',NULL,NULL);
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS) VALUES(207,'Liam Smith','M','Mathematics',85);
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS) VALUES(208,'Sophia Johns','F','Science',NULL);
```

**Output:**

![image](https://github.com/user-attachments/assets/1f9c4fa9-8b9f-4fbf-bbbb-556fef81e476)


**Question 2**
---
![image](https://github.com/user-attachments/assets/6c17dd17-d4a7-4f63-bc56-8eda25e6fe4c)


```sql
UPDATE products
SET product_name = 'Grapefruit' WHERE product_id = 4;
```

**Output:**

![image](https://github.com/user-attachments/assets/1683eb9a-011b-4c67-a819-039650e17b37)

**Question 3**
---
![image](https://github.com/user-attachments/assets/4ac3da12-16b7-4af4-9d4c-903b9fc40cfa)


```sql
UPDATE Employees
SET salary =
CASE 
WHEN department_id = 40 THEN salary*1.25
WHEN department_id = 90 THEN salary*1.15
WHEN department_id = 110 THEN salary*1.10
ELSE salary
END;
UPDATE Employees
SET salary = ROUND(salary,0);
```

**Output:**

![image](https://github.com/user-attachments/assets/f4398d1e-db92-4688-bf91-d2082681d386)


**Question 4**
---

![Screenshot 2025-04-29 135028](https://github.com/user-attachments/assets/3d4d55b4-267b-4992-b93c-16fbde8705ea)

```sql
UPDATE SALES
SET total_sell_price = quantity*sell_price WHERE product_id = 10; 
```

**Output:**

![image](https://github.com/user-attachments/assets/8ebf283a-8033-4cf2-a626-7ab1d3f3408c)


**Question 5**
---

![image](https://github.com/user-attachments/assets/cc1bac02-29d9-4e05-a102-6cbeb571ed21)


```sql
DELETE FROM Doctors
WHERE specialization IS NULL;
```

**Output:**

![image](https://github.com/user-attachments/assets/007d71aa-2af5-4f2a-9a5a-b21cbc02837f)


**Question 6**
---

![image](https://github.com/user-attachments/assets/5f24a5f0-eba6-4fbf-985e-35399e7224ab)

```sql
DELETE FROM Customer
WHERE CUST_COUNTRY ='UK' AND WORKING_AREA = 'London' AND GRADE < 3;
```

**Output:**

![image](https://github.com/user-attachments/assets/af5c52b6-0e33-4a9a-bf84-6fefad80be15)


**Question 7**
---

![image](https://github.com/user-attachments/assets/b6aa4535-6e0c-4c0e-997e-36227879ead3)


```sql
DELETE FROM Doctors
WHERE specialization = 'Pediatrics' AND first_name = 'Michael';
```

**Output:**

![image](https://github.com/user-attachments/assets/0cbb2be7-54ff-4df8-a5d3-11c1e2b14d8a)


**Question 8**
---

![image](https://github.com/user-attachments/assets/6ba4b344-c738-4cf0-8540-41dc3b2845c3)


```sql
SELECT COUNT(*)
FROM EmployeeInfo WHERE department = 'HR'; 
```

**Output:**

![image](https://github.com/user-attachments/assets/dd9a77aa-dcbc-45e2-babc-d2333070b975)


**Question 9**
---

![image](https://github.com/user-attachments/assets/69cbe509-5b71-4fbf-875c-258ad25b6959)


```sql
SELECT customer_id, cust_name, city, grade,salesman_id FROM customer
WHERE grade>100;
```

**Output:**

![image](https://github.com/user-attachments/assets/27c5db7d-02bd-4e57-ab2f-aba7bf73de86)


**Question 10**
---

![image](https://github.com/user-attachments/assets/e86665a7-8064-4d9b-b8f5-a7f54f8b8313)

```sql
SELECT id, value1,
CASE 
WHEN value1>50 THEN 'High'
ELSE 'Low' 
END AS value_category
FROM Calculations;
```

**Output:**

![image](https://github.com/user-attachments/assets/30a63098-de46-40d9-810f-d957dcc16195)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
