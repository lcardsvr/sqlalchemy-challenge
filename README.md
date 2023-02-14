# Module 10 Challenge


## Instructions

Congratulations! You've decided to treat yourself to a long holiday vacation in Honolulu, Hawaii. To help with your trip planning, you decide to do a climate analysis about the area. The following sections outline the steps that you need to take to accomplish this task.

## Part 1: Analyse and Explore the Climate Data

The ERD Sketch for this challenge is presented below.

![image](/EmployeeSQL_Sketch_02.png)


## Data Engineering

Following the ERD Sketch above, the tables were created. Summaries are below for reference.

![image](/Table_Summaries.PNG)

![image](/Table_Summaries_01.PNG)

The code for the table creation and the data analysis is available under https://github.com/lcardsvr/sql-challenge/blob/main/SQL_Challenge_code.sql 

## Data Analysis

1. List the employee number, last name, first name, sex, and salary of each employee.

select employees_db.emp_no as "Employee Number", employees_db.last_name as "Last Name", employees_db.first_name as "First Name", employees_db.sex as "Sex", salaries_db.salary as "Salary"
from employees_db
inner join salaries_db
on employees_db.emp_no = salaries_db.emp_no;

![image](/Employee_Info_Salary.PNG)

2. List the first name, last name, and hire date for the employees who were hired in 1986.

select employees_db.first_name as "First Name", employees_db.last_name as "Last Name", employees_db.hire_date as "Hire Date"
from employees_db
where employees_db.hire_date like '%/1986';

![image](/Employee_hired_1986.PNG)

3. List the manager of each department along with their department number, department name, employee number, last name, and first name.

select dept_manager_db.dept_no as "Department Number", departments_db.dept_name as "Department Name", employees_db.emp_no as "Employee Number", employees_db.last_name as "Last Name", employees_db.first_name as "First Name" 
from departments_db
left join dept_manager_db
on dept_manager_db.dept_no = departments_db.dept_no
left join employees_db
on dept_manager_db.emp_no = employees_db.emp_no;

![image](/Managers_Per_Department.PNG)

4. List the department number for each employee along with that employee’s employee number, last name, first name, and department name.

select departments_db.dept_no as "Department Number",  employees_db.emp_no as "Employee Number", employees_db.last_name as "Last Name", employees_db.first_name as "First Name",departments_db.dept_name as "Department Name" 
from departments_db
left join dept_emp_db
on dept_emp_db.dept_no = departments_db.dept_no
left join employees_db
on dept_emp_db.emp_no = employees_db.emp_no;

![image](/Department_Number-Name_Employee_Name.PNG)

5. List the first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B.

select employees_db.first_name as "First Name", employees_db.last_name as "Last Name", employees_db.sex as "Sex"
from employees_db
where employees_db.first_name = 'Hercules' 
and employees_db.last_name like 'B%';

![image](/Employees_Hercules_B.PNG)

6. List each employee in the Sales department, including their employee number, last name, and first name.

select dept_emp_db.dept_no as "Department Number",  employees_db.emp_no as "Employee Number", employees_db.last_name as "Last Name", employees_db.first_name as "First Name"
from employees_db
left join dept_emp_db
on dept_emp_db.emp_no = employees_db.emp_no
where dept_emp_db.dept_no = 'd007';

![image](/Sales_Employees.PNG)

7. List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name.

Create view Dev_Sales as
select *
from departments_db
where dept_name = 'Development'
or dept_name = 'Sales'

Create view Dev_Sales_emp_no as
select dept_emp_db.emp_no, dept_emp_db.dept_no, Dev_Sales.dept_name
from dept_emp_db
inner join Dev_Sales on
Dev_Sales.dept_no = dept_emp_db.dept_no


select employees_db.emp_no as "Employee Number", employees_db.last_name as "Last Name", employees_db.first_name as "First Name", Dev_Sales_emp_no.dept_name as "Department Name"
from employees_db
inner join Dev_Sales_emp_no on
employees_db.emp_no = Dev_Sales_emp_no.emp_no

![image](/Sales_Development_Employees.PNG)

8. List the frequency counts, in descending order, of all the employee last names (that is, how many employees share each last name).

SELECT employees_db.last_name as "Last Name", COUNT(employees_db.last_name) AS "Number of occurences"
FROM employees_db
GROUP BY "Last Name"
ORDER BY "Last Name" DESC;

![image](/Last_Name_Occurences.PNG)

## Submission

1. Submitted and available in GitHub under https://github.com/lcardsvr/sql-challenge

2. SQL Code available under https://github.com/lcardsvr/sql-challenge/blob/main/SQL_Challenge_code.sql



