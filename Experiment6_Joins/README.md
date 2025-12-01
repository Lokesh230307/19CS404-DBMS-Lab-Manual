# Experiment 6: Joins
```
LOKESH S
212224230143
```
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
<img width="1260" height="617" alt="image" src="https://github.com/user-attachments/assets/4584fa17-1368-4fd7-b0de-13aa90c1f597" />


```sql
SELECT p.*
FROM patients p, test_results t
WHERE p.patient_id = t.patient_id
  AND t.test_name IN ('Blood Test','Blood Pressure')
  AND t.result NOT LIKE '%Normal%';
```

**Output:**

<img width="1218" height="228" alt="image" src="https://github.com/user-attachments/assets/aa9576d6-70b3-444d-88a9-48720e00a200" />

**Question 2**
---
<img width="1247" height="430" alt="image" src="https://github.com/user-attachments/assets/32223ab7-d886-409d-ab82-014a033a14b6" />

```sql
SELECT p.first_name AS patient_name, d.first_name AS doctor_name
FROM patients p
JOIN doctors d ON p.doctor_id = d.doctor_id
WHERE p.discharge_date IS NOT NULL;
```

**Output:**

<img width="433" height="217" alt="image" src="https://github.com/user-attachments/assets/e1b4646f-a5bd-4cbf-85be-a3bd8c3fa689" />

**Question 3**
---
<img width="1247" height="503" alt="image" src="https://github.com/user-attachments/assets/212f97a7-b304-4ad0-b9b2-b00eb3fcd3f8" />

```sql
SELECT c.cust_name AS "Customer Name", c.city AS "city",
       s.name AS "Salesman", s.city AS "city", s.commission AS "commission"
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city AND s.commission > 0.12;
```

**Output:**

<img width="912" height="336" alt="image" src="https://github.com/user-attachments/assets/9436cbd1-2f4d-4426-9b6f-aec14596f4e4" />

**Question 4**
---
<img width="1143" height="173" alt="image" src="https://github.com/user-attachments/assets/6b18d618-1154-43d4-85bd-c3ef5144b51c" />

```sql
SELECT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id
WHERE c.city = 'New York';
```

**Output:**

<img width="432" height="216" alt="image" src="https://github.com/user-attachments/assets/5eaf09cc-c808-4a97-88e8-fbcbd82c8677" />

**Question 5**
---
<img width="1003" height="517" alt="image" src="https://github.com/user-attachments/assets/d10425a1-b79b-4846-9d78-62b747975b22" />

```sql
SELECT c.cust_name AS "Customer Name", c.city AS "city",
       s.name AS "Salesman", s.commission AS "commission"
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;
```

**Output:**

<img width="884" height="396" alt="image" src="https://github.com/user-attachments/assets/14a440d7-63a4-48ab-bb0c-829d27e9b7c8" />

**Question 6**
---
<img width="1183" height="263" alt="image" src="https://github.com/user-attachments/assets/d48d248b-84be-4232-90d4-9ce642b090e9" />

```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';

```

**Output:**

<img width="1012" height="467" alt="image" src="https://github.com/user-attachments/assets/9666de31-b02b-4897-a1ce-03984565cb9c" />


**Question 7**
---
<img width="981" height="552" alt="image" src="https://github.com/user-attachments/assets/2d958fe7-3cc7-4973-a56b-c2e7a06380c2" />

```sql
SELECT a.cust_name, a.city, b.ord_no,
       b.ord_date, b.purch_amt AS "Order Amount", 
       c.name, c.commission 
-- Specifying the tables to retrieve data from ('customer' as 'a', 'orders' as 'b', and 'salesman' as 'c')
FROM customer a 
-- Performing a left outer join based on the customer_id, including unmatched rows from 'customer'
LEFT OUTER JOIN orders b 
ON a.customer_id = b.customer_id 
-- Performing another left outer join with the result of the previous join and the 'salesman' table based on salesman_id
LEFT OUTER JOIN salesman c 
ON c.salesman_id = b.salesman_id;
```

**Output:**

<img width="816" height="556" alt="image" src="https://github.com/user-attachments/assets/d210549f-aac0-4389-a63b-2dc0ce0be0ae" />

**Question 8**
---
<img width="1200" height="669" alt="image" src="https://github.com/user-attachments/assets/3932fac7-6efe-40bd-94f2-18704837f173" />

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="931" height="436" alt="image" src="https://github.com/user-attachments/assets/0e6451b7-ce7a-4268-b768-1f7c6702bd97" />

**Question 9**
---
<img width="846" height="547" alt="image" src="https://github.com/user-attachments/assets/bd82f371-0cb0-460b-84eb-05fa39f558ef" />

```sql
SELECT a.cust_name, a.city, a.grade, 
       b.name AS "Salesman", b.city 
FROM customer a 
LEFT JOIN salesman b 
ON a.salesman_id = b.salesman_id 
ORDER BY a.customer_id;
```

**Output:**

<img width="1043" height="503" alt="image" src="https://github.com/user-attachments/assets/a033d2be-fcdb-4c9b-a2b1-3cf35d50c62b" />

**Question 10**
---
<img width="1149" height="397" alt="image" src="https://github.com/user-attachments/assets/159a7cc2-73e7-4409-ad00-9895abb0122a" />

```sql
SELECT 
    p.first_name AS patient_name,
    t.test_name
FROM patients p
INNER JOIN test_results t 
    ON p.patient_id = t.patient_id;
```

**Output:**

<img width="579" height="298" alt="image" src="https://github.com/user-attachments/assets/1798f554-4f4a-48f4-a1df-a98f91c95af0" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
