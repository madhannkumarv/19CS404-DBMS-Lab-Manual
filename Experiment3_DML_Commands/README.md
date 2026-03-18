# Experiment 3: DML Commands
# Register Number : 212224040176
# Developed By : MADHANN KUMAR V

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
<img width="1147" height="267" alt="Screenshot 2026-02-24 093909" src="https://github.com/user-attachments/assets/0e272727-0b64-4c0b-8642-484091cb714a" />


```sql
``````

**Output:**

<img width="754" height="801" alt="Screenshot 2026-02-24 093922" src="https://github.com/user-attachments/assets/732d25c5-1beb-4295-94e7-da93ea11ae1a" />

**Question 2**
---
<img width="711" height="331" alt="Screenshot 2026-02-24 093927" src="https://github.com/user-attachments/assets/9fc4589e-e33f-42d4-b7fe-1cb9fcfdbc79" />

```sql
select date(AppointmentDateTime) as AppointmentDate , count(AppointmentID) as TotalAppointments from Appointments group by date(AppointmentDateTime) order by AppointmentDate;

```

**Output:**

<img width="839" height="690" alt="Screenshot 2026-02-24 093934" src="https://github.com/user-attachments/assets/2f5024a9-d15d-4c25-99b3-4bc907642dc7" />

**Question 3**
---
<img width="1059" height="245" alt="Screenshot 2026-02-24 093941" src="https://github.com/user-attachments/assets/abe76d05-0c09-439a-b4e0-a27b5a119145" />

```sql
select DoctorID , count(PrescriptionID) as TotalPrescriptions from Prescriptions group by DoctorID;
```

**Output:**

<img width="770" height="792" alt="Screenshot 2026-02-24 094014" src="https://github.com/user-attachments/assets/81767591-1891-4826-bedd-9e608dab0127" />


**Question 4**
---

<img width="992" height="313" alt="Screenshot 2026-02-24 094019" src="https://github.com/user-attachments/assets/0c640c6c-bba0-4312-a81b-72e8251dc7b3" />

```sql
select avg(purch_amt) as AVERAGE from orders;
```

**Output:**

<img width="361" height="311" alt="Screenshot 2026-02-24 094024" src="https://github.com/user-attachments/assets/43500f26-715c-4f56-a448-9a315edeeddf" />

**Question 5**
---
<img width="951" height="294" alt="Screenshot 2026-02-24 094029" src="https://github.com/user-attachments/assets/95fdd1ad-007f-46be-ad7c-8e320b18c32f" />

```sql
select count(distinct salesman_id) as COUNT from orders;
```

**Output:**

<img width="383" height="317" alt="Screenshot 2026-02-24 094034" src="https://github.com/user-attachments/assets/81394095-a898-44d1-9e9a-d7bcbadd08be" />

**Question 6**
---
<img width="812" height="328" alt="Screenshot 2026-02-24 094039" src="https://github.com/user-attachments/assets/eca648a1-6b20-4dbe-b41e-141891710a1b" />

```sql
select sum(inventory) as total from fruits where unit = 'LB';
```

**Output:**
<img width="372" height="316" alt="Screenshot 2026-02-24 094044" src="https://github.com/user-attachments/assets/ae18f71f-ef5f-40b7-9317-2ad8f6255a25" />


**Question 7**
---
<img width="844" height="290" alt="Screenshot 2026-02-24 094048" src="https://github.com/user-attachments/assets/372b1bad-ebb2-4d2b-88c8-305bf823c849" />

```sql
select count(id) as employees_count from employee where income > 50000;
```

**Output:**

<img width="456" height="309" alt="Screenshot 2026-02-24 094053" src="https://github.com/user-attachments/assets/6cd7fa01-c41a-4255-980d-fad2d7507427" />

**Question 8**
---
<img width="1111" height="301" alt="Screenshot 2026-02-24 094059" src="https://github.com/user-attachments/assets/260443c9-9db5-477e-ba0b-e145d795aa0c" />

```sql
select occupation , AVG(workhour) from employee1 group by occupation having avg(workhour) >= 10 and avg(workhour) <= 12;
```

**Output:**

<img width="671" height="402" alt="Screenshot 2026-02-24 094105" src="https://github.com/user-attachments/assets/9857f4e9-b4c3-45d2-817d-c4a555872883" />


**Question 9**
---
<img width="1192" height="311" alt="Screenshot 2026-02-24 094111" src="https://github.com/user-attachments/assets/fa4c9ee8-a6c0-4c0b-9319-5de758c2b34b" />

```sql
select city , AVG(income) from employee group by city having avg(income) > 500000;
```

**Output:**

<img width="607" height="441" alt="Screenshot 2026-02-24 094116" src="https://github.com/user-attachments/assets/8c787dce-893f-493e-8e42-cfaa193f6265" />

**Question 10**
---
<img width="1171" height="308" alt="Screenshot 2026-02-24 094123" src="https://github.com/user-attachments/assets/fc6e942f-515b-4899-b66f-49656f43c141" />

```sql
select age , AVG(income) from employee group by age having avg(income) >= 300000 and avg(income) <= 500000;
```

**Output:**

<img width="629" height="338" alt="Screenshot 2026-02-24 094129" src="https://github.com/user-attachments/assets/9b80eb9b-5db3-48f8-98aa-4bdf3089a2ce" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
