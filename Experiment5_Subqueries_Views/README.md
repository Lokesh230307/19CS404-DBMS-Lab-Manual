# Experiment 5: Subqueries and Views
```
LOKESH S
212224230143
```
## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="1169" height="666" alt="image" src="https://github.com/user-attachments/assets/be0a3ab3-1a8f-45f5-9a9d-54edff708d0e" />

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';
```

**Output:**
<img width="1114" height="330" alt="image" src="https://github.com/user-attachments/assets/69961cca-14c6-491f-8d49-5a0670aab740" />


**Question 2**
---
<img width="1204" height="567" alt="image" src="https://github.com/user-attachments/assets/ac66be8b-9cd1-4059-9133-1e56e39b3705" />


```sql
SELECT 
    student_id,
    student_name,
    subject,
    grade
FROM 
    Grades
WHERE 
    grade = (
        SELECT MIN(g2.grade)
        FROM Grades g2
        WHERE g2.subject = Grades.subject
    );
```

**Output:**

<img width="1197" height="357" alt="image" src="https://github.com/user-attachments/assets/3dfb536b-20ff-4a23-98ee-59b8519558a7" />

**Question 3**
---
<img width="1119" height="531" alt="image" src="https://github.com/user-attachments/assets/8e3de4db-dbde-4e20-a8ed-89f05957fe45" />

```sql
SELECT medication_id AS medic, medication_name, dosage
FROM Medications
WHERE dosage = (SELECT MIN(dosage) FROM Medications);
```

**Output:**

<img width="824" height="341" alt="image" src="https://github.com/user-attachments/assets/1089ed62-5ec1-4db2-895e-d75ca1ff0328" />


**Question 4**
---
<img width="1022" height="454" alt="image" src="https://github.com/user-attachments/assets/f8863400-da6b-4a81-96b7-bb9acb5482d5" />

```sql
SELECT medication_id AS medic, medication_name, dosage
FROM Medications
WHERE dosage = (SELECT MAX(dosage) FROM Medications);
```

**Output:**

<img width="873" height="325" alt="image" src="https://github.com/user-attachments/assets/5f53419c-ccf2-4280-8a0d-65748472ebbc" />



**Question 5**
---
<img width="926" height="486" alt="image" src="https://github.com/user-attachments/assets/1fe330ed-705e-4dc6-a569-6cc6c54060bc" />

```sql
WHERE city != (SELECT city FROM customer WHERE id = (SELECT MAX(id) FROM customer));
```

**Output:**

<img width="1229" height="399" alt="image" src="https://github.com/user-attachments/assets/04aadcdc-f1d1-4a01-a272-fb7f81e4d6c3" />

**Question 6**
---
<img width="1204" height="561" alt="image" src="https://github.com/user-attachments/assets/cf79c63f-a0f3-42db-ac55-92d3a6d29877" />


```sql
SELECT * FROM CUSTOMERS WHERE SALARY=1500;
```

**Output:**

<img width="1050" height="274" alt="image" src="https://github.com/user-attachments/assets/caed26f8-5cbd-421a-9a23-3516307e0f5f" />

**Question 7**
---
<img width="1239" height="642" alt="image" src="https://github.com/user-attachments/assets/3928527d-4490-44b7-aa84-6705fa735e2d" />

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city = 'London';
```

**Output:**

<img width="1099" height="352" alt="image" src="https://github.com/user-attachments/assets/dd44df65-5ce3-4d00-b01a-03cab3fa04c6" />

**Question 8**
---
<img width="1125" height="477" alt="image" src="https://github.com/user-attachments/assets/f3184cbe-1f7a-4da0-b9d4-72fe552ed73a" />

```sql
SELECT name, city
FROM customer
WHERE city IN (SELECT city FROM customer WHERE id=3 OR id=7);
```

**Output:**

<img width="802" height="396" alt="image" src="https://github.com/user-attachments/assets/78febe0e-b5e6-4db0-96b3-fbb8f5f21608" />

**Question 9**
---
<img width="1136" height="553" alt="image" src="https://github.com/user-attachments/assets/02609ab3-785f-43f8-b642-b48deeb0dc24" />

```sql
SELECT * 
FROM Grades
WHERE grade = (SELECT MAX(grade) FROM Grades g2 WHERE g2.subject = Grades.subject);
```

**Output:**

<img width="1216" height="375" alt="image" src="https://github.com/user-attachments/assets/23041915-e11f-4909-b6f3-05c26bd06ae0" />


**Question 10**
---
<img width="1131" height="595" alt="image" src="https://github.com/user-attachments/assets/052f6279-5d76-4c7b-92e7-bd5d07b291b8" />

```sql
SELECT * FROM CUSTOMERS WHERE SALARY>4500;
```

**Output:**

<img width="1210" height="362" alt="image" src="https://github.com/user-attachments/assets/785fa813-d5a5-4638-a096-3330d4fb18d6" />




## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
