# First_question

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
