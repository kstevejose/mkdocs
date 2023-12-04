FULL JOIN combines rows from both tables and creates a result set irrespective of matching values. 

FULL JOINS are used when you need rows from both tables even if there are no matching records.

**FULL JOIN** Syntax:

```sql
SELECT table_1.column_1, table_2.column_1 FROM table 1 FULL JOIN table 2 ON table_1.column_2 = table_2.column_2;
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

In this example, if we would like to find all the departments and all the employees, we can execute a **FULL JOIN** as follows:

```sql
SELECT e.employee_name, d.department_name FROM employees e FULL JOIN departments d ON e.department_id = d.department_id
```

**Output**:

|  employee_name | department_name | 
|----------|----------|
| Tony | Boss | 
| Silvio| Consigliere | 
| Paulie| Under Boss | 
| Bobby| NULL|
| NULL | Soldier|