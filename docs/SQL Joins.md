# Introduction

SQL Joins as the name indicates helps join two or more tables and retrieve data based on
common values between tables. Inner join works like an MS Excel formula called
[VLOOKUP/XLOOKUP](https://www.goskills.com/Excel/Resources/Xlookup-vs-vlookup), which allows you to retrieve values from two different tables/sheets
based on common values.

## Advantages

The following are the advantages of using SQL Joins

* **Efficient Data Retrieval** : Querying and retrieving data from multiple tables efficiently.
* **Customized Data Retrieval** : Customized data retrieval based on the requirement.
* **Simplified Data Analysis** : Helps join multiple tables for data analysis that would be
difficult to obtain otherwise.

## Types of Joins

The following are the various types of Joins available with SQL.

* **INNER JOIN** : The **Inner Join** always *returns only matching records between tables*.
*  **LEFT JOIN** : The **LEFT Join** always *returns all records from left table and matching records from right table*.
*  **RIGHT JOIN** : The **RIGHT Join** always *returns all records from right table and matching records from left table*.
*  **FULL JOIN** : The **FULL Join** always *returns returns records from both tables irrespective of matching records.

Let's dive into a bit deep into understanding this:

## INNER JOIN

INNER JOIN only returns rows when there is a common value that exists between two tables.
INNER JOINS are used when data is required from two or more tables and there’s a common
value between these tables and exclude unmatching records.

**INNER JOIN Syntax**:

```sql
SELECT table_1.column1, table_2.column_1 FROM table 1 INNER JOIN table 2 ON
table_1.column_2 = table_2.column_2;
```
![INNER JOIN](images/INNER_JOIN.PNG)

Let’s consider this example in the following table:

Table **Employees**

|  employee_id | employee_name | department_id |
|----------|----------|------|
| 1 | Tony | 100| 
| 2| Silvio | 101| 
| 3 | Paulie | 102 | 
| 4 | Bobby | 103 | 

Table **Departments**

|  department_id | department_name | 
|----------|----------|
| 100 | Boss | 
| 101| Consigliere | 
| 102| Under Boss | 

In this example, we have two tables of a Waste Management company such as Employees and Department with a common column between the two tables(department_id).

In such scenarios, we can execute an SQL Inner join to retrieve data from both tables as:

```sql
SELECT e.employee_name, d.department_name FROM employees e INNER JOIN
departments d ON e.department_id = d.department_id;
```
|  Value | Description | 
|----------|----------|
| e | An alias *(substitute name)* for the employees table. | 
| d| An alias *(substitute name)* for the departments table.  | 
| employee_name| Column from employee table that needs to be retrieved. | 
| department_name| Column from department table that needs to be retrieved. | 
| employees e| Employee table indicated with an alias e. | 
| department d|Department table indicated with an alias d | 
| INNER JOIN| Specified the type of join being performed. | 
| ON e.department_id = d.department_id| A condition that indicates join is taking place between department_id column of employees(e) and department(d) tables. |

**Output**:

|  employee_name | department_name | 
|----------|----------|
| Tony | Boss | 
| Silvio| Consigliere | 
| Paulie| Under Boss | 