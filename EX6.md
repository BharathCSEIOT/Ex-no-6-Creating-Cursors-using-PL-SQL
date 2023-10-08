# Ex. No: 6 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
```
NAME: BHARATH K
Reg.no: 212222110006
```
## Create employee table
```
create table employee1(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
insert into employee1 values(1,'Chozhan','HR',50000);
insert into employee1 values(2,'Joseph','IT',65000);
insert into employee1 values(3,'Bharath','Finance',55000);
```
### PLSQL Cursor code

```
set serveroutput on 
declare
cursor employee1_cursor is
select empid,empname,dept,salary
from employee1;
empid number;
empname varchar(90);
dept varchar(90);
salary number;
begin
open employee1_cursor;
loop
fetch employee1_cursor into empid,empname,dept,salary;
exit when employee1_cursor%notfound;
dbms_output.put_line('Employee ID: '||empid);
dbms_output.put_line('Employee Name: '||empname);
dbms_output.put_line('Department: '||dept);
dbms_output.put_line('Salary: '||salary);
dbms_output.put_line('------------------------');
end loop;
close employee1_cursor;
end;
/

```
### Output:
![image](https://github.com/BharathCSEIOT/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/122793480/e215ad58-aca1-4682-8215-f57d2edeb2d1)



### Result:
The Program has been implemented successfully.
