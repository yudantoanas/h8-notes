# SQL (Structured Query Language)

*This README is the basics of SQL with some example. Please visit the documentation for more detail.

# Introduction
SQL (Structured Query Language) is a programming language designed for managing relational databases. It allows you to manipulate data in a database and retrieve information in a structured manner. SQL is widely used in industry and is an essential skill for data analysts, database administrators, and software developers.

Type of SQL Commnad:
- DDL (Data Definition Language)
- DQL (Data Query Language)
- DML (Data Manipulation Language)
- DCL (Data Control Language)

# DDL (Data Definition Language)
DDL stands for Data Definition Language and is used to define the structure of a database. With SQL, you can use DDL to create, drop, and modify tables.

## [Creating Table](https://www.postgresqltutorial.com/postgresql-create-table/)

The `CREATE TABLE` statement is used to create a new table in the database. Here is an example:
```sql
CREATE TABLE "Customers" ( 
	"id" INT NOT NULL, 
	"name" VARCHAR(50), 
	"email" VARCHAR(50), 
	"country" VARCHAR(50), 
	PRIMARY KEY ("id") 
);
```
This statement creates a table called `customers` with three columns: `id`, `name`, and `email`. The `id` column is defined as the primary key.

## [Modifying Tables](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-alter-table/)
You can use the `ALTER TABLE` statement to modify an existing table. 
Here are some examples:

### Adding a Column
```sql
ALTER TABLE "Customers" ADD "phone" VARCHAR(15);
```
This statement adds a new column called `phone` to the `customers` table.

### Dropping a Column
```sql
ALTER TABLE "Customers" DROP COLUMN "phone";
```
This statement removes the `phone` column from the `customers` table.

### Modifying a Column
```sql
ALTER TABLE "Customers" MODIFY COLUMN "name" VARCHAR(100);
```
This statement changes the data type of the `name` column from `VARCHAR(50)` to `VARCHAR(100)`.

## [Renaming Tables](https://www.postgresqltutorial.com/postgresql-rename-table/)

To rename a table in SQL, you use the `ALTER TABLE` statement with the `RENAME TO` clause. Here is an example:
```sql
ALTER TABLE "Customers" RENAME TO "Clients";
```
This renames the `Customers` table to `Clients`.

## [Dropping Table](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-alter-table/)

To remove an entire table from a database, you can use the `DROP TABLE` statement followed by the name of the table you want to drop. For example:
```sql
DROP TABLE "Customers";
```
This statement drops the `Customers` table from the database.

You can also use the `IF EXISTS` clause to prevent errors from occurring if the table does not exist:
```sql
DROP TABLE IF EXISTS "Customers";
```
This statement drops the `Customers` table from the database if it exists, and does nothing if it does not exist.

Note that dropping a table permanently deletes all data and metadata associated with that table, so use this command with caution. You should also be aware that some database systems have additional safeguards in place to prevent accidental or unauthorized table drops.

# DQL (Data Query Language)
Data Query Language (DQL) is a subset of SQL that is used to retrieve data from one or more tables in a database. DQL statements typically begin with the `SELECT` keyword and specify the columns to retrieve, the tables to retrieve data from, and any conditions or sorting to apply to the data.

## [Select](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-select/)
Here is an example of a basic `SELECT` statement:
```sql
SELECT column1, column2, ... FROM table1
```
This statement retrieves the specified columns from the `table1` table. When using the `SELECT` statement, you can specify which columns to retrieve from a table by listing them after the `SELECT` keyword, separated by commas. For example, the following statement will retrieves all customer. For example:
```sql
SELECT 
	"name", 
	"age", 
	"email", 
	"country" 
FROM 
	"Customers";
```
This statement retrieves the `name`, `age`, `email`, dan `country` columns from the `Customers` table.

You can also use the `*` wildcard character to retrieve all columns from a table:
```sql
SELECT 
	* 
FROM 
	"Customers";
```
This statement retrieves all columns from the `Customers` table.

## [Filtering](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-where/)
You can also use the `WHERE` clause to filter the data based on a condition, like this:
```sql
SELECT column1, column2, ... FROM table1 WHERE condition
```
For example, the following statement retrieves all customers from the `Customers` table who live in `Indonesia`:
```sql
SELECT 
	* 
FROM 
	"Customers" 
WHERE 
	"country" = 'Indonesia'
```

Another example:
```sql
SELECT 
	"name", 
	"age", 
	"email" 
FROM 
	"Customers" 
WHERE 
	"age" > 30;
```
This statement retrieves the `name`, `age`, and `email` columns from the `Customers` table, but only for `Customers` whose `age` is greater than 30.

You can also use logical operators like `AND` and `OR` to combine multiple conditions:
```sql
SELECT 
	"name", 
	"age", 
	"email" 
FROM 
	"Customers" 
WHERE 
	"age" > 30 
AND 
	email LIKE '%yopmail.com';
```
This statement retrieves the `name`, `age`, and `email` columns from the `Customers` table, but only for Customers whose `age` is greater than 30 **and** whose `email` address contains "yopmail.com".

## [Sorting Data](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-order-by/)
You can use the `ORDER BY` clause to sort the data returned by a `SELECT` statement. For example:
```sql
SELECT 
	"name", 
	"age", 
	"email" 
FROM 
	"Customers" 
ORDER BY 
	"age" DESC;
```
This statement retrieves the `name`, `age`, and `email` columns from the `Customers` table, sorted by `age` in descending order.

You can also sort by multiple columns:
```sql
SELECT 
	"name", 
	"age", 
	"email" 
FROM 
	"Customers" 
ORDER BY 
	"age" DESC, "name" ASC;
```
This statement retrieves the `name`, `age`, and `email` columns from the `Customers` table, sorted first by `age` in descending order, and then by `name` in ascending order.

## [Limiting Results](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-limit/)
You can use the `LIMIT` clause to limit the number of results returned by a `SELECT` statement. For example:
```sql
SELECT 
	"name", 
	"age", 
	"email" 
FROM 
	"Customers" 
LIMIT 10;
```
This statement retrieves the `name`, `age`, and `email` columns from the `Customers` table, but only the first 10 rows.

You can also use the `OFFSET` clause to skip a certain number of rows:
```sql
SELECT 
	"name", 
	"age", 
	"email" 
FROM 
	"Customers" 
LIMIT 10 
OFFSET 20;
```
This statement retrieves the `name`, `age`, and `email` columns from the `Customers` table, starting from the 21st row and returning the next 10 rows.

## [Grouping Data](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-group-by/)
SQL allows you to group data based on one or more columns in a table. You can use the `GROUP BY` clause followed by the name of the column(s) you want to group by. For example:
```sql
SELECT 
	"department", 
	COUNT(*) as "num_employees" 
FROM 
	"Employees" 
GROUP BY 
	"department";
```
This statement groups the employees by department and counts the number of employees in each department.

You can also use the `HAVING` clause to filter the results of a `GROUP BY` query based on a condition. For example:
```sql
SELECT 
	"department", 
	AVG("salary") as avg_salary 
FROM 
	"Employees" 
GROUP BY 
	"department" 
HAVING AVG("salary") > 50000;
```
This statement groups the employees by department and calculates the average salary for each department. It then filters the results to show only the departments where the average salary is greater than 50000.

## What is different where and having?
The `WHERE` and `HAVING` clauses are both used in SQL to filter query results, but they operate on different parts of the query.

The `WHERE` clause is used to filter rows before the aggregation (such as grouping or summary functions) occurs. It is used with the `SELECT`, `UPDATE`, and `DELETE` statements to specify conditions that must be met for the operation to be performed on a particular row.

For example, if you wanted to retrieve all employees with a salary greater than $50,000, you would use the `WHERE` clause like this:
```sql
SELECT 
	* 
FROM 
	"Employees" 
WHERE 
	"salary" > 50000;
```
The `HAVING` clause, on the other hand, is used to filter groups after the aggregation has occurred. It is used with the `GROUP BY` statement to specify conditions that must be met for a group to be included in the query result.

For example, if you wanted to retrieve the average salary for each department, but only for departments with an average salary greater than $50,000, you would use the `HAVING` clause like this:
```sql
SELECT 
	"department", 
	AVG("salary") 
FROM 
	"Employees" 
GROUP BY 
	"department" 
HAVING 
	AVG("salary") > 50000;
```
Note that the `HAVING` clause can only be used in conjunction with the `GROUP BY` clause, while the `WHERE` clause can be used without grouping.

In summary, the `WHERE` clause filters rows based on conditions before aggregation, while the `HAVING` clause filters groups based on conditions after aggregation.

# DML (Data Manipulation Language)
DML statements in SQL are used to manipulate data within a table. There are three main types of DML statements: `INSERT`, `UPDATE`, and `DELETE`.

1.  [Insert](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-insert-multiple-rows/)
This statement is used to add new rows to a table. The basic syntax is as follows:
```sql
INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);
```
Here's an example of how to use the `INSERT` statement to add a new row to a `users` table:
```sql
INSERT INTO "Users" ("name", "email", "age") VALUES ('John Smith', 'john@example.com', 35);
```
This statement inserts a new row into the `users` table with the name "John Smith", email "[john@example.com](mailto:john@example.com)", and age 35.

2.  [Update](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-update/) 
This statement is used to modify existing data within a table. The basic syntax is as follows:
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
Here's an example of how to use the `UPDATE` statement to update the age of a user in the `users` table:
```sql
UPDATE "Users"
SET "age" = 40
WHERE "name" = 'John Smith';
```
This statement updates the age of the user with the name "John Smith" to 40.

3.  [Delete](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-delete/)
This statement is used to remove data from a table. The basic syntax is as follows:
```sql
DELETE FROM table_name
WHERE condition;
```
Here's an example of how to use the `DELETE` statement to remove a user from the `users` table:
```sql
DELETE FROM "Users"
WHERE "name" = 'John Smith';
```
This statement deletes the row from the `users` table where the name is "John Smith".

## [Writing Order Of Select Query](https://dataschool.com/sql-optimization/order-of-a-sql-query/)
```sql
SELECT DISTINCT column, AGGREGATE(column)
FROM table1
JOIN table2
ON table1.column = table2.column
WHERE constraint_expression
GROUP BY column
HAVING constraint_expression
ORDER BY column ASC/DESC
LIMIT count;
```