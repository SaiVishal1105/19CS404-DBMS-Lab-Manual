# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/ece34717-b634-48b5-b304-d44a6ac1b42f)


```sql
SELECT c.customer_id,c.cust_name,c.city,c.grade,c.salesman_id
FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id
WHERE o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';
```

**Output:**

![image](https://github.com/user-attachments/assets/cfd7b5aa-4145-47d7-9c43-97ed447dbbef)


**Question 2**
---
![image](https://github.com/user-attachments/assets/8b4afcfb-9b80-4def-bc0f-247924c7a56c)


```sql
SELECT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id=c.salesman_id
WHERE c.city='London';
```

**Output:**

![image](https://github.com/user-attachments/assets/edc98a03-b6ef-4f72-b54f-dfa5035a17d2)


**Question 3**
---
![image](https://github.com/user-attachments/assets/1075003f-dc7a-4f87-bc42-85920ea6019a)

```sql
SELECT p.first_name AS patient_name,d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d ON p.patient_id=d.doctor_id
WHERE p.date_of_birth > '1990-01-01';
```

**Output:**

![image](https://github.com/user-attachments/assets/411e89b5-daee-42d2-9916-7ff9ca0cc09d)


**Question 4**
---
![image](https://github.com/user-attachments/assets/6f520fa8-6f25-4758-ae02-fa4e1c420a47)


```sql
SELECT s.name AS Salesman, c.cust_name, c.city
FROM salesman s
INNER JOIN customer c
ON s.city = c.city;
```

**Output:**

![image](https://github.com/user-attachments/assets/845f00eb-7647-4330-b00d-ddd7733da0c8)


**Question 5**
---
![image](https://github.com/user-attachments/assets/496e3333-97ac-487b-a75f-165c921715b1)


```sql
SELECT p.first_name AS "patient_name",d.first_name AS "doctor_name"
FROM patients p
INNER JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE p.discharge_date IS NULL;

```

**Output:**

![image](https://github.com/user-attachments/assets/a6a51d6b-f5c7-42b0-9735-040b2c1e1465)


**Question 6**
---
![image](https://github.com/user-attachments/assets/91ae71a4-538a-40fc-afe4-5a193651ed6b)


```sql
SELECT p.first_name AS "patient_name",d.first_name AS "doctor_name"
FROM patients p
INNER JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE p.discharge_date IS NOT NULL;
```

**Output:**

![image](https://github.com/user-attachments/assets/9c7a9058-3a40-422b-bab6-24b51ce367b2)


**Question 7**
---
![image](https://github.com/user-attachments/assets/c2501ffb-73a8-4c68-b444-203d8c51c0ab)


```sql
SELECT n.*
FROM nurses n
INNER JOIN departments d ON n.department_id=d.department_id
WHERE d.department_name='Pediatrics';
```

**Output:**

![image](https://github.com/user-attachments/assets/31bebbc2-c57b-41f4-b0d4-cf3c98cc936b)


**Question 8**
---
![image](https://github.com/user-attachments/assets/bb1ab3a0-64d9-4420-b56d-ddaeaafdce99)


```sql
SELECT o.ord_no, o.purch_amt, c.cust_name, c.city
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

![image](https://github.com/user-attachments/assets/035037ac-74ad-49bb-9839-7e46a243b373)


**Question 9**
---
![image](https://github.com/user-attachments/assets/3321f5cc-7f02-44fc-ba58-0aff6b5317e5)


```sql
SELECT p.first_name AS patient_name,t.test_name
FROM patients p
INNER JOIN test_results t ON p.patient_id=t.patient_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/3ae92ab6-35fb-40eb-b200-e93f3c91eb9a)


**Question 10**
---
![image](https://github.com/user-attachments/assets/007ea367-a37a-4c4a-af97-8df888c64fb8)


```sql
SELECT p.first_name AS patient_name
FROM patients p
INNER JOIN test_results t ON p.patient_id = t.patient_id
WHERE t.test_name = 'Blood Pressure';

```

**Output:**

![image](https://github.com/user-attachments/assets/5b852264-7f47-490d-b0a1-03e8d7e52b49)



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
