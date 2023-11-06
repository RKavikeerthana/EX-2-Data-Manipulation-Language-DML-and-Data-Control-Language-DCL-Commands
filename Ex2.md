# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
# DATE:22.8.23
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),
commission number(4),annualsalary number(7),Hiredate date,designation char(10),
deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);

```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![Screenshot 2023-10-08 095437](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/ff56706c-6c12-4d4a-ad6f-c1bc49131a1e)


### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![Screenshot 2023-10-08 095457](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/aee832ee-b347-43e1-b214-4291dded3b7b)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![Screenshot 2023-10-08 095525](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/959a0fb1-c3e2-4d6f-8de6-0a21f41f02a0)

### Q4) List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![Screenshot 2023-10-08 095542](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/65b579f7-360e-4e66-a5ed-3cf450bdc6ab)

### Q5)	List the names of employee who are not Managers
### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![Screenshot 2023-10-08 095600](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/8fae9545-494e-4f25-89e6-3bd5247e41f0)



### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![Screenshot 2023-10-08 095617](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/2e2c1ec0-a713-43dc-8e5e-4cf1047b65a8)

### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/2459dd14-23bf-4aa7-b495-185c24967515)

### Q8)	 Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:

![Screenshot 2023-10-08 095646](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/ff2cc88c-71e2-4b5e-b7f9-5822390fe10e)


### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![Screenshot 2023-10-08 095700](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/f01d0f1b-19d2-4813-842d-169c32d54bcd)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![Screenshot 2023-10-08 095718](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/d02ce6de-12ec-45f5-9b72-2456d8746af4)

### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![Screenshot 2023-10-08 095729](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/cff88048-4f89-400e-a27f-22968a63ed2c)

### Q12) Find number of rows in the table EMP

### QUERY:
```
select count(*) from manager;
```
### OUTPUT:

![Screenshot 2023-10-08 095738](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/57163866-66e4-415a-a80a-72be019e354e)

### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
```
select max(salary) from manager;
```
### OUTPUT:
![Screenshot 2023-10-08 095748](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/9b85dacf-2943-4fcf-95f6-daddaee9508c)

## MINIMUM:
```
select min(salary) from manager;
```
## OUTPUT:
![Screenshot 2023-10-08 095758](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/1192cd8d-0b83-4f9c-9a79-4e3e31a5b330)


## AVERAGE:
```
select avg(salary) from manager;
```
## OUTPUT:
![Screenshot 2023-10-08 095807](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/93a562b2-1163-423b-9a25-990ade96c9a3)


### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:

![Screenshot 2023-10-08 095828](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/97821bb5-4dfe-466d-98ef-59f27dd5481a)

### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
