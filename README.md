# TESTING of the HR Databse using SQL  - 


# Overview

The HR Analytics Dashboard was created using Excel. The aim of this project is to query the database to make sure we have accurate results on the dashboard.

# Dataset Description

The file used in this project is available in this repository as hrdata and the QA documentation as SQL Test Document_Tableau.docx

The dataset used for this project contains HR-related information such as employee details, attrition status, demographics, job satisfaction ratings, and departmental data. The dataset is structured in a table named "hrdata" with various columns representing different attributes of employees.

# SQL Queries and Insights

**Employee Count:** The SQL query "SELECT sum(employee_count) as Employee_Count FROM hrdata;" retrieves the total number of employees in the dataset. This metric helps to understand the size of the workforce.

**Attrition Count:** By executing the SQL query "SELECT count(attrition) FROM hrdata WHERE attrition='Yes';", the number of employees who have left the company (attrition) is obtained. This information provides insights into employee turnover.

**Attrition Rate:** The SQL query "SELECT round(((SELECT count(attrition) FROM hrdata WHERE attrition='Yes')/sum(employee_count)) * 100,2) FROM hrdata;" calculates the attrition rate, which is the percentage of employees who have left the company compared to the total workforce. This metric helps to gauge the stability of the workforce.

**Active Employee Count:** By executing the SQL query "SELECT sum(employee_count) - (SELECT count(attrition) FROM hrdata WHERE attrition='Yes') FROM hrdata;", the number of active employees (those who have not left the company) is determined. This metric indicates the retention rate of employees.

**Average Age:** The SQL query "SELECT round(avg(age),0) FROM hrdata;" calculates the average age of employees in the dataset. This metric provides insights into the age distribution of the workforce.

**Attrition by Gender:** The SQL query "SELECT gender, count(attrition) as attrition_count FROM hrdata WHERE attrition='Yes' GROUP BY gender ORDER BY count(attrition) desc;" retrieves the attrition count categorized by gender. This analysis helps identify any gender-related patterns in employee attrition.

**Department-wise Attrition:** The SQL query "SELECT department, count(attrition), round((cast(count(attrition) as numeric) / (SELECT count(attrition) FROM hrdata WHERE attrition= 'Yes')) * 100, 2) as pct FROM hrdata WHERE attrition='Yes' GROUP BY department ORDER BY count(attrition) desc;" provides insights into attrition rates by department. This information helps HR professionals understand which departments experience higher attrition rates.

**Attrition Rate by Gender for Different Age Groups:** The SQL query "SELECT age_band, gender, count(attrition) as attrition, round((cast(count(attrition) as numeric) / (SELECT count(attrition) FROM hrdata WHERE attrition = 'Yes')) * 100,2) as pct FROM hrdata WHERE attrition = 'Yes' GROUP BY age_band, gender ORDER BY age_band, gender desc;" analyzes attrition rates by gender within different age groups. This analysis helps identify any age and gender-related trends in employee attrition.

**Job Satisfaction Rating:** The SQL query "SELECT * FROM crosstab('SELECT job_role, job_satisfaction, sum(employee_count) FROM hrdata GROUP BY job_role, job_satisfaction ORDER BY job_role, job_satisfaction') AS ct(job_role varchar(50), one numeric, two numeric, three numeric, four numeric) ORDER BY job_role;" retrieves job satisfaction ratings by job roles. This analysis provides insights into employee satisfaction levels within different job roles.

Usage Instructions

To reproduce the analysis or further explore the dataset, follow these steps:


**Database Setup:** Create a database and import the dataset into a table named "hrdata" with appropriate column names and data types.

**SQL Queries:** Execute the provided SQL queries to obtain the desired HR analytics insights. The queries cover employee count, attrition count, attrition rate, active employee count, average age, attrition by gender, department-wise attrition, attrition rate by gender for different age groups, and job satisfaction rating.


# Conclusion

The HR Analytics project showcased the utilization of SQL queries to perform in-depth analysis on a given HR dataset. By executing the provided queries, meaningful insights such as employee count, attrition count, attrition rate, active employee count, average age, attrition by gender, department-wise attrition, attrition rate by gender for different age groups, and job satisfaction rating were obtained. These insights can assist HR professionals in making informed decisions related to talent retention, identifying areas for improvement, and formulating strategies to enhance employee satisfaction and reduce attrition rates.





Regenerate response
