# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL

## DATE:

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
```sql
UPDATE manager
SET SALARY = SALARY + (SALARY *10/100);
```

### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/215ff7be-5b1c-422c-b3ae-6c5577305d57)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```sql
 delete from manager
 where salary<2750;
```

### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/bb075f8f-b447-40e3-8cea-9e31c50dc7a2)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```sql
 select ename as "Name",salary*12 as "Annual Salary" from manager;
```
### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/06a4cee6-a302-43a1-ae02-d769dbec90ec)

### Q5)	List the names of Clerks from emp table.


### QUERY:
```sql
select ename from manager where designation='clerk';
```

### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/89ef7eac-2bc0-446b-9605-44ce857d79ac)

### Q6)	List the names of employee who are not Managers.


### QUERY:
```sql
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/69e7c51e-2102-4e0b-a198-67977e978032)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```sql
select ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/aa080e74-4a84-4b2d-8dba-7f314969cd05)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```sql
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/8704e1b9-83bd-4443-9419-745b43a40a71)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```sql
 select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/b5ba3d72-6c64-4512-843b-0488acf6eb82)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```sql
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/4c5f7157-62c3-4fa6-97ef-586f5a49c4d5)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```sql
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/dc743cf2-c4cb-42d3-bc30-7cd3985ed2af)

### Q12) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```sql
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/deeac1aa-5149-418d-92da-2620437c383d)

### Q13) Find number of rows in the table EMP

### QUERY:
```sql
select count(*) from manager;
```
### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/c6cd2eb6-550d-4db4-8101-3fbfef72102e)

### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```sql
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;
```
### OUTPUT:

![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/edb79012-360c-4406-91e3-7c960aaead53)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
 SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![image](https://github.com/ShanmathiShanmugam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121243595/6950cded-6eb8-47c0-a7d7-68dfec90d3e8)
