# First_question

I have used Hive to solve this question.
Here need to find out the average salary fo each Senior employee.
For this need to find out the all senior employee from available data.
Then perfom action on that all senior employee data, Here in this data we have Senior Staff and Senior Engineer employees.
I have used below query to get this done:

1. To calculate average salary of All Senior staff employee:
hive> select avg(s.salary) from employees e left join titles t on (e.emp_no = t.emp_no) left join salaries s on (e.emp_no = s.emp_no) where t.title like '%Senior Staff%';   

Using this query i got the Average salary of all senior staff employees.

2. To Calculate average salary of all Senior Engineer employee:
hive> select avg(s.salary) from employees e left join titles t on (e.emp_no = t.emp_no) left join salaries s on (e.emp_no = s.emp_no) where t.title like '%Senior Engineer%';

Using above qury I got the average salary of all senior engineer employees.

In this way I got the all senior staff and senior engineer employees and calculated average salary of senior staff and senior engineer employees.

For this question I have used HIVE.
There are following files which describe about the steps followed to get output : 
1) senior_stuff_avg_sal_exection_process: This file shows the AVG salary for the senior_stuff & the output came from the hive query & the output CSV file genrated into seniorStuff->000000_0 ;
2) sernior_engg_avg_sal_execution_process: This file shows the AVG salary for the senior_stuff & the output came from the hive query & the output CSV file genrated into seniorStuff->000000_0 ;
3) seniorStaffList: Contains all the senior staff list details ().
4) seniorEnggList : Contains all the senior Engineer list details.

Following queries used to genrate csv for seniorStaffList & seniorEnggList:
1) seniorEnggList:
INSERT OVERWRITE LOCAL DIRECTORY '/home/vishal/Downloads/seniorEnggList' select e.emp_no,e.first_name,t.title from employees e left join titles t on e.emp_no = t.emp_no where t.title like '%Senior Engineer%';
2) seniorStaffList: 
INSERT OVERWRITE LOCAL DIRECTORY '/home/vishal/Downloads/seniorStaffList' select e.emp_no,e.first_name,t.title from employees e left join titles t on e.emp_no = t.emp_no where t.title like '%Senior staff%';
