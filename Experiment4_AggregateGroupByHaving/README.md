# Experiment 4: Aggregate Functions, Group By and Having Clause

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
Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the total salary sum for each group, and excludes groups where the total salary sum is not greater than 5000.

```sql
SELECT (age/5)*5 AS age_group,SUM(salary) AS 'SUM(salary)' FROM customer1
GROUP BY (age/5)*5
HAVING SUM(salary)>5000;
```

**Output:**
![image](https://github.com/user-attachments/assets/a4d1a8e3-90ff-4171-9aad-eb9edd89568b)


**Question 2**
---
Write the SQL query to find how many patients have more than 3 medical records?.
```sql
SELECT PatientID,COUNT(*) AS TotalRecords FROM MedicalRecords
GROUP BY PatientID
HAVING COUNT(*)>3;
```

**Output:**
![image](https://github.com/user-attachments/assets/a56ab19c-f3c1-48c7-82b2-594346ef172a)


**Question 3**
---
Write the SQL query that accomplishes the selection of product which has lowest price in each category from the "products" table and includes only those products where the minimum price is less than 10.
```sql
SELECT category_id,MIN(price) AS Price FROM products
WHERE price<10
GROUP BY category_id;
```

**Output:**
![image](https://github.com/user-attachments/assets/7ee7fff4-61a4-4844-b879-0e4da88a0038)

**Question 4**
---

Write a SQL query to find the Fruit with the lowest available quantity.
```sql
SELECT name AS 'fruit_name',MIN(inventory) AS lowest_quantity FROM fruits;
```

**Output:**

![image](https://github.com/user-attachments/assets/6aa9b199-1da9-4af4-9c29-b2237e96dad7)


**Question 5**
---
Write a SQL query to find the number of employees whose age is greater than 32.
```sql
SELECT COUNT(id) AS 'COUNT' FROM employee
WHERE age>32;
```

**Output:**
![image](https://github.com/user-attachments/assets/a6b75732-2c2e-4749-9c18-bf06286c8b74)

**Question 6**
---
Write a SQL query to count the number of customers. Return number of customers.
```sql
SELECT COUNT(customer_id) AS 'COUNT' FROM customer;
```

**Output:**
![image](https://github.com/user-attachments/assets/9f2fc8b3-2cc4-405c-9eea-781337dace52)

**Question 7**
---
Write a SQL query to find the maximum purchase amount.
```sql
SELECT MAX(purch_amt) AS MAXIMUM FROM orders;
```

**Output:**
![image](https://github.com/user-attachments/assets/547b9414-e6d9-41a8-8349-7e9ad5b61f9b)


**Question 8**
---
How many appointments are scheduled for each doctor?

```sql
SELECT DoctorID,COUNT(*) AS TotalAppointments FROM Appointments
GROUP BY DoctorID;
```

**Output:**
![image](https://github.com/user-attachments/assets/34dc1aa6-4710-43a2-81ce-4eb8a3cc4123)


**Question 9**
---
How many patients are covered by each insurance company?

```sql
SELECT InsuranceCompany,COUNT(*) AS TotalPatients FROM Insurance
GROUP BY InsuranceCompany;
```

**Output:**
![image](https://github.com/user-attachments/assets/372fb8c4-b609-4011-bc9a-7e6ba48d583f)

**Question 10**
---
What is the count of male and female patients?
```sql
SELECT GENDER,COUNT(*) AS TotalPatients FROM Patients
GROUP BY GENDER;
```

**Output:**
![image](https://github.com/user-attachments/assets/068e89c9-a7e8-4205-844c-fa1b4a83a201)




## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
