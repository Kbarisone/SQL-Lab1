------------------------------------------
Table Creation
--------------------------------------------

CREATE TABLE EMPLOYEES (
                            EMP_ID CHAR(9) NOT NULL, 
                            F_NAME VARCHAR(15) NOT NULL,
                            L_NAME VARCHAR(15) NOT NULL,
                            SSN CHAR(9),
                            B_DATE DATE,
                            SEX CHAR,
                            ADDRESS VARCHAR(30),
                            JOB_ID CHAR(9),
                            SALARY DECIMAL(10,2),
                            MANAGER_ID CHAR(9),
                            DEP_ID CHAR(9) NOT NULL,
                            PRIMARY KEY (EMP_ID));
                            
  CREATE TABLE JOB_HISTORY (
                            EMPL_ID CHAR(9) NOT NULL, 
                            START_DATE DATE,
                            JOBS_ID CHAR(9) NOT NULL,
                            DEPT_ID CHAR(9),
                            PRIMARY KEY (EMPL_ID,JOBS_ID));
 
 CREATE TABLE JOBS (
                            JOB_IDENT CHAR(9) NOT NULL, 
                            JOB_TITLE VARCHAR(15) ,
                            MIN_SALARY DECIMAL(10,2),
                            MAX_SALARY DECIMAL(10,2),
                            PRIMARY KEY (JOB_IDENT));

CREATE TABLE DEPARTMENTS (
                            DEPT_ID_DEP CHAR(9) NOT NULL, 
                            DEP_NAME VARCHAR(15) ,
                            MANAGER_ID CHAR(9),
                            LOC_ID CHAR(9),
                            PRIMARY KEY (DEPT_ID_DEP));

CREATE TABLE LOCATIONS (
                            LOCT_ID CHAR(9) NOT NULL,
                            DEP_ID_LOC CHAR(9) NOT NULL,
                            PRIMARY KEY (LOCT_ID,DEP_ID_LOC));
                            

------------------------------------------
Queries
------------------------------------------
               
## Employees who live in Elgin
Select F_Name, L_Name from employees where address like '%Elgin,IL%';

## Employees born in the 1970's
Select F_Name, L_Name, B_DATE from employees where B_DATE like '%197%';

## All employees in department 5 whose salary is between 60000 and 70000
Select F_Name, L_Name, SALARY, DEP_ID from employees where DEP_ID = 5 and Salary between 60000 and 70000;

## Selects all employees and orders them by department
SELECT F_NAME, L_NAME, DEP_ID FROM `employees` ORDER BY DEP_ID;

## Retrieves a list of employees ordered in descending order by department ID and within each department ordered alphabetically in descending order by last name.
SELECT F_NAME, L_NAME, DEP_ID FROM employees ORDER BY DEP_ID desc, L_NAME desc;

## Retrieves a count of employees from each department
SELECT DEP_ID, count(DEP_ID) FROM `employees` GROUP BY DEP_ID;

## Retrieves count and avg salary for each department
SELECT DEP_ID, count(DEP_ID), avg(SALARY) FROM `employees` GROUP BY DEP_ID;

##Retrieves Count of employees per department and average salary for departments with less than 4 people and orders by average salary
SELECT DEP_ID, count(DEP_ID) as NUM_Employees, avg(SALARY) as AVG_SALARY FROM `employees` 
GROUP BY DEP_ID 
Having count(DEP_ID) < 4 
ORDER BY AVG_SALARY;

##Retrieves Department name and first and last name ordered by department name and employee last name in descending order
SELECT D.Dep_Name, E.F_Name, E.L_Name
From employees as E, Departments as D
Where E.Dep_ID = D.DEPT_ID_DEP
ORDER BY D.DEP_Name, E.L_NAME desc;


