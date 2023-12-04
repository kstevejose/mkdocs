LEFT JOIN selects all the rows from the left table and matches them with all the rows in the right table. If there are matching records, it displays the output. If no matching records are found, it displays NULL.

LEFT JOINS are used when you need all the rows in the left table even if there are no matching records in the right table.

**LEFT JOIN** syntax:

```sql
SELECT table_1.column_1, table_2.column_1 FROM table 1 LEFT JOIN table 2 ON table_1.column_2 = table_2.column_2;
```

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

In this example, if we would like to find all the employees and their departments even for those employees who do not have a department assigned to them, we can execute a **LEFT JOIN** as follows:

```sql
SELECT e.employee_name, d.department_name
FROM employees e
LEFT JOIN departments d ON e.department_id = d.department_id;
```
**Output**:

|  employee_name | department_name | 
|----------|----------|
| Tony | Boss | 
| Silvio| Consigliere | 
| Paulie| Under Boss | 
| Bobby| NULL|