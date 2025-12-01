# Experiment 4: Aggregate Functions, Group By and Having Clause
```
LOKESH S
212224230143
```
## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="839" height="465" alt="image" src="https://github.com/user-attachments/assets/846447c4-13a8-4cdf-9b65-e2616e62164b" />


```sql
select name,max(income)
from employee
where city = 'California';
```

**Output:**

<img width="626" height="276" alt="image" src="https://github.com/user-attachments/assets/bbc0158e-5552-4040-989d-92d800ff2e70" />


**Question 2**
---
<img width="800" height="485" alt="image" src="https://github.com/user-attachments/assets/a4858cfc-650b-4b09-b4b0-d7d809b685a9" />

```sql
SELECT COUNT(DISTINCT customer_id)
AS COUNT
FROM customer
WHERE grade IS NOT NULL;
```

**Output:**
<img width="451" height="287" alt="image" src="https://github.com/user-attachments/assets/a6575403-7771-40f2-963d-31c77d343007" />



**Question 3**
---
<img width="1037" height="463" alt="image" src="https://github.com/user-attachments/assets/060ef2e8-1190-4122-80bb-0ebfec4bbb2d" />


```sql
SELECT MAX(age) - MIN(age) AS
age_difference
from employee

```

**Output:**

<img width="532" height="278" alt="image" src="https://github.com/user-attachments/assets/04621c94-cd8e-41d6-9aad-af642bf58680" />




**Question 4**
---
<img width="747" height="580" alt="image" src="https://github.com/user-attachments/assets/65182956-10c4-4475-b1a0-13e7cf8fcbb0" />


```sql
select patientID, count(*) as TotalAppointments
from Appointments
group by PatientID;
```

**Output:**

<img width="757" height="606" alt="image" src="https://github.com/user-attachments/assets/91337cd1-bef3-4ae0-94f2-32a841ab2ffe" />



**Question 5**
---
<img width="700" height="631" alt="image" src="https://github.com/user-attachments/assets/b052a388-0996-4877-87f2-e9baaba8e063" />

```sql
select InsuranceCompany , count(*) as TotalPatients
from Insurance
group by InsuranceCompany;
```

**Output:**

<img width="771" height="663" alt="image" src="https://github.com/user-attachments/assets/f0580171-8b07-4ef6-b834-660f4a7559c4" />



**Question 6**
---
<img width="1062" height="448" alt="image" src="https://github.com/user-attachments/assets/63ff812b-9d18-42d9-91ab-06e986cca24f" />

```sql
select Gender , count(*) as TotalPatients
from Patients
group by Gender;
```

**Output:**

<img width="692" height="339" alt="image" src="https://github.com/user-attachments/assets/5b064781-71ce-4fdf-9916-4fb1bad8f234" />


**Question 7**
---
<img width="1252" height="364" alt="image" src="https://github.com/user-attachments/assets/ca180337-e9ec-45bc-8daf-91126330e86d" />

```sql
select (age/5)*5 as age_group,
SUM(salary)
from customer1
group by (age/5)*5
having SUM(salary) >5000;
```

**Output:**

<img width="583" height="340" alt="image" src="https://github.com/user-attachments/assets/7b553a3d-1567-4ce9-b153-815a02c6ebc4" />


**Question 8**
---
<img width="1168" height="464" alt="image" src="https://github.com/user-attachments/assets/3c08c3e8-4af2-4706-be2b-ea0b52c4ee87" />

```sql
select address,
AVG(salary)
from customer1
group by address
having AVG(salary) > 5000;
```

**Output:**

<img width="601" height="405" alt="image" src="https://github.com/user-attachments/assets/5246672e-2b58-4fb3-b023-bbebf226119e" />


**Question 9**
---
<img width="906" height="579" alt="image" src="https://github.com/user-attachments/assets/3a6cb375-5415-4999-ba15-a0dfb97f7248" />

```sql
select address, AVG(salary)
from customer1
group by address
having AVG(salary) < 15000;
```

**Output:**

<img width="638" height="581" alt="image" src="https://github.com/user-attachments/assets/1996f3fa-ce1d-45f7-be54-ebe9dbe666f1" />

**Question 10**
---
<img width="1252" height="358" alt="image" src="https://github.com/user-attachments/assets/27c0937a-78cd-4c8f-adf1-a97c6237be09" />

```sql
select (age/5)*5 as age_group,
MIN(age)
from customer1
group by (age/5)*5
having MIN(age) < 25;
```

**Output:**

<img width="570" height="285" alt="image" src="https://github.com/user-attachments/assets/fb442f18-71df-4744-ba1a-a0c78a57e896" />




## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
