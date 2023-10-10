# Ex. No: 6 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table:
```
CREATE TABLE employee4 (empid NUMBER,empname VARCHAR(10),dept VARCHAR(10),salary NUMBER);
INSERT INTO employee4 VALUES (1, 'rk', 'IT', 70000);
INSERT INTO employee4 VALUES (2, 'dk', 'HR', 000);
INSERT INTO employee4 VALUES (3, 'jk', 'Marketing', 90000);
select * from employee4;
```
### PLSQL Cursor code:
```
set serveroutput on;
declare
cursor employee4_cursor is
select empid,empname,dept,salary
from employee4;
emp_id number;
emp_name varchar(20);
emp_dept varchar(20);
emp_salary number;
begin
open employee4_cursor;
loop
fetch employee4_cursor into emp_id,emp_name,emp_dept,emp_salary;
exit when employee4_cursor%NOTFOUND;
DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
end loop;
close employee4_cursor;
end;
/
```
### Output:
![image](https://github.com/rathishc12/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/120539398/9e25470b-601c-4cbe-8920-8e3f8f257b86)

### Result:
Thus this program executed successfully.
