# Recap Materi Week 2

- [Database Schema](#database-schema-diagram)
- [SQL](#sql)
  - [DDL](#ddl-data-definition-language)
  - [DQL](#dql-data-query-language)
  - [DML](#dml-data-manipulation-language)
  - [Writing Order](#writing-order)
- [Node Postgres](#node-postgres)
- [Express](#express)
  - [Express Middleware](#express-middleware)
  - [EJS](#ejs)

![](https://media.tenor.com/yfRbDajBsC8AAAAC/spongebob-database.gif)

# Database Schema Diagram

- Database adalah tempat menyimpan data
- Sebelum merancang sebuah database untuk aplikasi kita, diperlukan untuk membuat schema diagram terlebih dahulu.
- Tools yang dipakai:
  - draw.io / creately -> for creating schema
- Saat membuat schema diagram, kita harus menentukan table apa saja yang dibutuhkan, beserta property dan relasi nya
- Macam-macam relasi:
  - 1 to 1
  - 1 to many
  - many to many
  ![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/04/Entity_Relationship_Diagram_Examples.png/464px-Entity_Relationship_Diagram_Examples.png)
- Relationship Symbol in Schema
![](https://uploads-us-west-2.insided.com/miro-us/attachment/a9877a9b-d306-4e9b-8274-18810c1faecb.png)

## References

- [Lecture Slide](https://docs.google.com/presentation/d/1th5tA99mBOAlo5dPUZzIkBdaFJgddieSXgUIK5-EWsk/edit)

# SQL

> SQL (Structured Query Language) is a programming language designed for managing relational databases. It allows you to manipulate data in a database and retrieve information in a structured manner. SQL is widely used in industry and is an essential skill for data analysts, database administrators, and software developers.

- Tools yang dipakai:
  - DBeaver
  - PostgreSQL (DBMS)

- Type of SQL Commnad:

  - DDL (Data Definition Language)
  - DQL (Data Query Language)
  - DML (Data Manipulation Language)
  - Other types: DCL, and TCL

    ![](https://media.geeksforgeeks.org/wp-content/uploads/20210920153429/new.png)

## DDL (Data Definition Language)

> DDL stands for Data Definition Language and is used to define the structure of a database. With SQL, you can use DDL to create, drop, and modify tables.

- Create Table ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-create-table/))

```sql
CREATE TABLE accounts (
 user_id serial PRIMARY KEY,
 username VARCHAR ( 50 ) UNIQUE NOT NULL,
 password VARCHAR ( 50 ) NOT NULL,
 email VARCHAR ( 255 ) UNIQUE NOT NULL,
 created_on TIMESTAMP NOT NULL,
        last_login TIMESTAMP 
);
```

- Alter/Modify Table ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-alter-table/))
- Drop Table ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-drop-table/))

## DQL (Data Query Language)

> Data Query Language (DQL) is a subset of SQL that is used to retrieve data from one or more tables in a database.

- DQL statements typically begin with the `SELECT` keyword and specify the columns to retrieve, the tables to retrieve data from, and any conditions or sorting to apply to the data.

  - Select ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-select/))
  - Select Distinct ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-select-distinct/))
  - Join ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-joins/))
  - Where ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-where/))
  - Group By ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-group-by/))
  - Having ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-having/))
  - Order By ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-order-by/))
  - Limit ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-limit/))

    ```sql
    SELECT * FROM Employees e;
    JOIN Departments d on d.id = e."DepartmentsId"
    WHERE d.id = 10
    ORDER BY e.name DESC
    LIMIT 100;

    SELECT
    customer_id,
    SUM (amount)
    FROM
    payment
    GROUP BY
    customer_id
    HAVING
    SUM (amount) > 200;
    ```

## DML (Data Manipulation Language)

> DML statements in SQL are used to manipulate data within a table. There are three main types of DML statements: `INSERT`, `UPDATE`, and `DELETE`.

- Insert ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-insert-multiple-rows/))

```sql
INSERT INTO "Users" ("name", "email", "age") VALUES ('John Smith', 'john@example.com', 35);
```

- Update ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-update/))

```sql
UPDATE "Users"
SET "age" = 40
WHERE "name" = 'John Smith';
```

- Delete ([Reference](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-delete/))

```sql
DELETE FROM "Users"
WHERE "name" = 'John Smith';
```

## Writing Order

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

## References

- [Lecture Slide](https://docs.google.com/presentation/d/1repooRTwA-BhvdxIZgOuJFGxbUIc4v4_eTpbLux7hkw/edit#slide=id.g2c45707a0d_0_0)
- [Type of SQL Commands](https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/)
- [Writing Order](https://dataschool.com/sql-optimization/order-of-a-sql-query/)

# Node Postgres

- is a library for connecting NodeJS with PostgreSQL

![](https://media.tenor.com/3eIvVsG3yPYAAAAd/the-universe-tim-and-eric-mind-blown.gif)

## Step-by-Step

- `npm init` or `npm init -y`
- installation:

    ```bash
    npm install pg
    ```

- implementation, recommended using `Pool` instead of `Client`

## References

- [Video Material](https://drive.google.com/file/d/1yoUTQEtTp8i13UwY-y1Ci4OGXd8YxU5w/view?usp=sharing)
- [Installation](https://node-postgres.com/#install)
- [Implemetaion](https://node-postgres.com/features/connecting#programmatic)
- [Why use `Pool` instead of `Client`?](https://node-postgres.com/features/pooling)

# Express

- Lightweight web application framework using MVC architecture
- To install: `npm install express`
- Route Method:
  - GET -> is used to request data
  - POST -> is used to send data to a server to create/update a resource.

>Pro tip...
>
>**GET** requests should never be used when dealing with sensitive data

- `express.Router` -> to create modular route paths/handlers

## Express Middleware
>
>Middleware is a functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.

- Body Parser ([Reference](https://expressjs.com/en/4x/api.html#express.urlencoded))

    is an express.js middleware that parse incoming request bodies in a middleware before your handlers.

    ```js
    app.use(express.urlencoded({extended: true}))
    ```

- Static Files ([Reference](https://expressjs.com/en/starter/static-files.html))

    To serve static files such as images, CSS files, and JavaScript files

    ```js
    // to serve images, CSS files, and JavaScript files in a directory named 'public'
    app.use(express.static('public'))
    ```

## EJS

is one of many template engines that can be used in Express

- to install: `npm install ejs`
- to use:

    ```js
    app.set('view engine', 'ejs')
    ```

## References

![](https://media.tenor.com/e_CaV5Ue1T0AAAAC/cat-reading.gif)

- [Lecture Slide - Express](https://drive.google.com/a/hacktiv8.com/open?id=1MmR249WJ-wpYybt-6CL6yjnhel2slN5Jl1nYVaM2-b4)
- [Lecture Slide - Express Middleware & EJS](https://docs.google.com/a/hacktiv8.com/presentation/d/1i7N5-knu9rkVaDDAwnLjHc5eb3BuOyhVbneDjJR6DFk/edit?usp=drive_web)
- [Express Docs](https://expressjs.com/)

### Videos

- [Express](https://drive.google.com/file/d/1oHS8KB5SWlP8HZ5Q0i86UGBUtDC_kZ-b/view?usp=share_link)
- [Express - Using Template Engines](https://expressjs.com/en/guide/using-template-engines.html)
- [EJS Docs](https://ejs.co/)
- [Route: Get](https://drive.google.com/file/d/1Md0XV2GWy3UGFJVXOeUohuAIgJjSCgtm/view?usp=share_link)
- [Nodemon](https://drive.google.com/file/d/10dE-9ea_ecwGHWI5Odwg7nU4RkbA9SZ8/view?usp=share_link)
- [Params](https://drive.google.com/file/d/1wit1zix_MPzMY11EyzciKKTgju9Hkxwb/view?usp=share_link)
- [Query](https://drive.google.com/file/d/1nXL_CYfwSx3d9gaulFYEzae7b0jNX82e/view?usp=share_link)
- [Read data and using params](https://drive.google.com/file/d/1MZ794IwbowYDzjVzJuaWOR_P1Vv5b971/view?usp=share_link)
- [Sorting w/query string](https://drive.google.com/file/d/1Zy2Lz-iYl6xv6ZfGGnbDcMYWWEDDWNMI/view?usp=share_link)
