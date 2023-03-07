# Recap Materi Week 3 & Sequelize

- [Express-MVC-Postgres](#express-mvc-postgres)
  - [Validation](#validation)
  - [Partial EJS](#partial-ejs)
- [Promise](#promise)
- [Sequelize](#sequelize-orm)
  - [MVC](#express-mvc-postgres)
  - [Association](#association)
  - [Validations & Constraints](#validations-and-constraints)
- [Helper Functions](#helper-functions)

![](https://media.tenor.com/I7QkHH-wak4AAAAC/rumble-wwf.gif)

# Express-MVC-Postgres

Setelah kita belajar Express, MVC, dan PostgreSQL dari W1-2. Sekarang setiap kita memulai project baru, kita **Wajib** menginstall beberapa package berikut:

- express
- pg
- ejs

> untuk `nodemon` bisa di install secara opsional menggunakan flag `--save-dev` atau secara global dengan `--location=global`

with MVC architecture, our folder structure should look like this:

- AppProject
  - models
    - models.js
  - controllers
    - controllers.js
  - views
    - home.ejs
    - formAdd.ejs
    - ...
  - app.js
  - .gitignore
  - package.json

> don't forget to ignore `node_modules` directory in `.gitignore` file yes!

## Validation

Membuat 1 static method di model untuk melakukan validasi input dimana di method ini akan men-check setiap value yang diberikan dari controller (req.body) dan akan me-retrun sebuah array of errors

```js
static validation(value1, value2, value3,...) {
  let err = []

  // check tiap value-nya
  if (!value1) { // kondisional menyesuaikan requirement dari study case

    // push err message ketika ketemu
    err.push('value1 harus diisi')
  }

  return err
}
```

Selanjutnya, method validation ini akan di-invoke setiap sebelum melakukan query insert/update

## Partial EJS

> Partials are basically just views that are designed to be used from within other views. This approach is the implementation of a component.

```html
// komponen navbar.html
<nav class=”menu”>
    <ul>
        <li>Home</li>
    </ul>
</nav>

// untuk implement nav.html ke dalam file html utama kita menggunakan ejs
<%- include(‘partials/navbar’) %>
```

# Promise

- A Javascript object used for deferred an asynchronous processes.

> JS Promises represent operations that haven't completed just yet, but they're expected to be completed in the future.

- Promise States:
  - Pending, operasi async belum selesai
  - Fulfilled, promise sudah selesai dan ada result
  - Rejected, promise gagal diselesaikan

![](https://www.alexlintu.com/content/images/2021/04/Group-74.png)

# Sequelize (ORM)

> ORM is an acronym for Object Relational Mapping which is an idea of being able to write queries (Native SQL Query) using the object oriented paradigm of your preferred language.

- Sequelize is a **promise-based** ORM for Node.js. It supports the dialects PostgreSQL, MySQL, MariaDB, SQLite and MSSQL and features solid transaction support, relations, read replication and more.
- Required packages:
  - `npm i sequelize`
  - `npm i sequelize-cli` -> this is used for creating Models, Migrations, and Seeders
- Most used commands when using sequelize
  - `npx sequelize-cli init`
  - `npx sequelize-cli db:create`
  - `npx sequelize-cli db:drop`
  - `npx sequelize-cli db:migrate`
  - `npx sequelize-cli db:seed:all`
  - `npx sequelize-cli model:generate`
  - `npx sequelize-cli seed:generate`

## MVC

with MVC architecture, our folder structure should look like this:

- SequelizeAppProject
  - config
    - config.json
  - migrations
  - seeders
  - models
    - index.js
    - modelA.js
    - modelB.js
    - ...
  - controllers
    - controllers.js
  - views
    - home.ejs
    - formAdd.ejs
    - ...
  - app.js
  - .gitignore
  - package.json

## Association

- we can defined relationship between tables like 1:1, 1:N, M:N in sequelize
- in sequelize model, there is a static method that can be used to define our table relations

```js
// in model A
static associate(models) {
  // define relationship here
  A.hasOne(models.B)
  A.hasMany(models.C)
}

// in model B
static associate(models) {
  // define relationship here
  B.belongsTo(models.A)
}

// and so on...
```

## Validations and Constraints

- Validation -> pengecekan input di level application -> implemented on Model class
  - examples: `notEmpty, isEmail, etc`
- Constraint -> pengecekan di level database -> implemented on Migration file(s).
  - examples: `allowNull, unique, etc`

# Helper Functions

> is a function that performs part of the computation of another function. Helper functions are used to make the programs easier to read by giving descriptive names to computations. They also emphasize to reuse computations, just as with functions in general.

- usually, helper functions are located in `helpers/` directory.

# References

![](https://media.tenor.com/415n58OZ9CYAAAAM/cat-reads-reading.gif)

- [Express MVC](https://docs.google.com/a/hacktiv8.com/presentation/d/15k-0JHxTGVB2OFQGhvPoQ8e9MoVgT-yXW8UvNttWpdg)
- [Separation of Concerns (Component & Server Validation)](https://docs.google.com/a/hacktiv8.com/presentation/d/1rL-VCnd2EedfT4IT4rqmbO-KwwepzESYDDT0ARAGpEQ)
- [Promise](https://docs.google.com/presentation/u/4/d/1PzajCHoIkTwGShoj8yUF7IkKXxux4nO8DJJU3zP6YAw)
- [What is Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [Medium - What is Promise](https://www.alexlintu.com/what-is-a-promise/)
- [Sequelize](https://sequelize.org/)
- [Basic Query Sequelize](https://sequelize.org/master/manual/model-querying-basics.html)
- [Sequelize Association](https://docs.google.com/a/hacktiv8.com/presentation/d/1J0wBlbaJGJskuOK1bKWHSHUcGb9ef0AIyuoOUlIarME)
- [Sequelize Hooks](https://docs.google.com/a/hacktiv8.com/presentation/d/1AarVoWsz-dLxKRMyUbCCTEPUZfSpH217xLoV93tfzhQ)
- [Sequelize Validation](https://docs.google.com/a/hacktiv8.com/presentation/d/1mU4cM2AKlboTzpYVmmxdueB3wzXJlC5QR5XTqsp5IJo)
- [Helper Function](https://docs.google.com/a/hacktiv8.com/presentation/d/12TaX37UJU_IFf7JPxGKXqWYe3Exe6zAH0_AoB1QZdhE)
