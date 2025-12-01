# Experiment 3: DML Commands
```
LOKESH S
212224230143
```
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
Write a SQL statement to Update the grade of all customers in Chennai city as 5.

```sql
update customer 
set grade=5
where city='Chennai';
```

**Output:**
<img width="1247" height="368" alt="image" src="https://github.com/user-attachments/assets/852f42f3-de68-42fd-9108-9f7c3cad6373" />


**Question 2**
---
Write a SQL statement to Update the per_unit_price to 25 and total_price accordingly in purchases table where purchase_date is '2022-08-15' and product_id is 12.
```sql
update purchases
set per_unit_price=25, total_price=25*quantity
where purchase_date='2022-08-15' and product_id=12;
```

**Output:**

<img width="1259" height="444" alt="image" src="https://github.com/user-attachments/assets/8e1242af-8f4c-42c4-9338-c7e7f7b2259d" />


**Question 3**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.

```sql
delete from customer
where GRADE not in(3);
```

**Output:**

<img width="932" height="647" alt="image" src="https://github.com/user-attachments/assets/da880631-988d-4c33-bd88-884f107fff39" />

**Question 4**
---
Write a SQL query to Delete a Specific Surgery which was made on 28th Feb 2024.

```sql
delete from surgeries
where surgery_date = '2024-02-28';
```

**Output:**
<img width="1236" height="342" alt="image" src="https://github.com/user-attachments/assets/50e65bfc-ded5-4de9-ad5c-27d1d1a53ced" />


**Question 5**
---
Write a SQL query to Delete All Doctors with a NULL Specialization



```sql
Write a SQL query to Delete All Doctors with a NULL Specialization
```

**Output:**
<img width="1217" height="950" alt="image" src="https://github.com/user-attachments/assets/041fdc4c-805d-45c6-a00e-7baaaedf7256" />



**Question 6**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is greater than or equal to 2.


```sql
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is greater than or equal to 2.
```

**Output:**
<img width="679" height="520" alt="image" src="https://github.com/user-attachments/assets/28b8cd8c-6af3-4a10-90b8-1e29bffc4ee9" />


**Question 7**
---
Write a SQL query to label rows in the Calculations table as 'Even' if value1 is even, otherwise 'Odd'.


```sql
select id,value1,
    CASE
        WHEN CAST(value1 AS
        INTEGER) % 2=0 THEN 'Even'
        ELSE 'Odd'
    END AS parity
FROM calculations;
```

**Output:**
<img width="745" height="407" alt="image" src="https://github.com/user-attachments/assets/1b3493b5-50fd-41e1-a280-2bf7c556c2a9" />


**Question 8**
---
Write a SQL query to find the details of those salespeople who live in cities other than Paris and Rome. Return salesman_id, name, city, commission.


```sql
Write a SQL query to find the details of those salespeople who live in cities other than Paris and Rome. Return salesman_id, name, city, commission.
```

**Output:**
<img width="1037" height="400" alt="image" src="https://github.com/user-attachments/assets/0eedebd3-0e48-4d9d-80f4-8fb6de71d8f3" />


**Question 9**
---
write a SQL query to find customers who are either from the city 'New York' or who do not have a grade greater than 100. Return customer_id, cust_name, city, grade, and salesman_id.

```sql
select customer_id,cust_name,city ,grade,salesman_id from customer
where city='New York' OR grade<=100;
```

**Output:**
<img width="1246" height="394" alt="image" src="https://github.com/user-attachments/assets/2e7dff23-1e7d-4107-a265-b7242a8ab1ec" />

**Question 10**
---
Write a SQL query to calculate the discounted price for products whose original price is between $50 and $150. Return product_id, original_price, discount_percentage, and discounted_price.



```sql
select product_id,original_price,discount_percentage,
(original_price - (original_price * discount_percentage)) AS discounted_price
from products
where original_price BETWEEN 50 AND 150;
```

**Output:**
<img width="1250" height="252" alt="image" src="https://github.com/user-attachments/assets/7920289e-c061-488b-a2de-c159cd7c39d8" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
