# Applying-Filters-to-SQL-Queries
## Project Description
I worked with my team toward organizational goals to make sure that systems are more secure. It was my responsibility to ensure that the system is safe, potential security issues are investigated, and to make sure that employee computers are updated as needed. I used SQL filters to perform security related tasks, identifying potential security events and computers that were in need of updates.
## Retrieving after hours failed login attempts
A potential incident occurred after business hours (6:00 pm). I needed to review and investigate all login attempts that happened after close of business.
Using a SQL query, I pulled all columns from the log_in_attempts database, adding conditions to filter for a login time after 6:00 pm and filtering for unsuccessful login attempts.

<img src="https://i.imgur.com/TgIwKqn.png" alt="SQL query with filters"/>

I used `SELECT * FROM log_in_attempts` with * indicating all columns in the database, `log_in_attempts`. To filter the results, I used `WHERE login_time > '18:00' AND success = 0` ensuring that my results would only include data where the `login_time` was after (`>`) 6:00 pm and that only failed attempts were shown (`success = 0`).
## Retrieving login attempts on specific dates
I needed to investigate a suspicious event that occurred on 2022-05-09. I needed to investigate all login attempts that occurred on 2022-05-09 and on the day before.

I used the following code to create a SQL query that filtered for login attempts on those specific dates.

<img src="https://i.imgur.com/YW4Y2wf.png" alt="SQL query with filters"/>

This query returned all login attempts that occurred on `2022-05-08` or `2022-05-09`. I used a `WHERE` clause with an `OR` operator to filter my results from the `log_in_attempts` database to output only login attempts that occurred on either 2022-05-09 or 2022-05-08.
## Retrieving login attempts outside of Mexico
After investigating the organization’s data on login attempts, I believed there might be an issue with login attempts that occurred outside of Mexico. 

<img src="https://i.imgur.com/TveMvBC.png" alt="SQL query with filters"/>

I used the `NOT` and `LIKE` operators to filter my query results to omit login attempts that occurred in `MEX%`. The `%` wildcard, ensured that both MEX and MEXICO will be filtered from my results.
## Retrieving employees in Marketing
My team needed to update the machines for employees in the 'Marketing' department who are located in all offices in the East building. I created a SQL query to filter for employees in the Marketing department that are also in any office in the East building.

<img src="https://i.imgur.com/g0Ar7g6.png" alt="SQL query with filters"/>

I used `LIKE` with `East%` as the pattern to match because the data in the office column reflects both the East building and an office number. The first condition is the `department = 'Marketing'` portion, which filters for employees in the Marketing department. The second condition is the office `LIKE 'East%'` portion, which filters for employees in the East building.
## Retrieving employees in Finance or Sales
A different update needed to be run on the machines for employees in the Finance and Sales departments. I used SQL querying to compile employees from only these departments.

<img src="https://i.imgur.com/cfV919s.png" alt="SQL query with filters"/>

I used a `WHERE` clause with `OR` to filter all (`SELECT *`) columns of data for employees who are in the Finance and Sales departments. I used the `OR` operator instead of `AND` to ensure that results showed employees in either department. `department = 'Finance'` filters for employees in the Finance department. `department = 'Sales'` filters for employees from the Sales department.
## Retrieving all employees not in IT
My team needed to roll out an update that was already made to employee computers in the Information Technology department to the rest of the organization. I needed to identify the employee machines that are not in the IT department.

<img src="https://i.imgur.com/6vrD8m4.png" alt="SQL query with filters"/>

I used a SQL query with the `NOT` filter to omit computers in the `Information Technology` department from my results. 
## Summary
I applied filters to SQL queries to get specific information about login attempts and employee machines. I used the `AND`, `OR`, and `NOT` operators to filter for the specific information needed from two different tables, `log_in_attempts` and `employees`. I also used `LIKE` and the `%` wildcard to filter for patterns.
