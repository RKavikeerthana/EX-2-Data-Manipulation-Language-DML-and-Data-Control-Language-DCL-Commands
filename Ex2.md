# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
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
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/c070dc52-631a-4ddd-a71b-c82085469719)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/8e2b1070-4690-43af-967c-11334dc54181)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/8219fd87-80d2-4052-8076-89dbfc7dea9c)

### Q4) List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/e91f4fda-a584-47d6-9930-c86bf46850fa)

### Q5)	List the names of employee who are not Managers
### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/9df684d3-6f27-4a17-9711-b0073dfcfc61)


### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/2f1a053f-dd9c-407a-8d77-96727d2296e9)

### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/85258c05-4923-4d81-a84e-b760622be643)

### Q8)	 Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/6eb68eed-8f67-429d-b687-eb4a5f154ec8)


### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/66d86f4b-c93d-4526-aea5-db41a47b13ce)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/428a36ed-d5eb-4327-a419-1c60723e14d5)

### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/9ee0dae5-056b-4498-a693-a28c21967bc7)

### Q12) Find number of rows in the table EMP

### QUERY:
```
select count(*) from manager;
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/2781f451-d56a-41eb-b311-e95657259368)

### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
```
select max(salary) from manager;
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/9340ef6d-0361-4466-992c-bba5d4560a14)

## MINIMUM:
```
select min(salary) from manager;
```
## OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/8b03a9af-754b-4dec-90b8-b0f70b55b4a8)

## AVERAGE:
```
select avg(salary) from manager;
```
## OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/52730cbf-6d0e-4354-8ba0-0d876f46bc17)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![image](https://github.com/RKavikeerthana/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120431120/9cc606ff-896f-4d72-a12f-8fa28db75fc6)

### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
