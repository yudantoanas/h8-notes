# Recap Materi Week 1

- [Supplements](#supplements)
- [OOP](#oop)
- [OOP Characteristics](#oop-characteristics)
- [OOP Relationship](#oop-relationship)
- [Factory Method](#factory-method)
- [MVC](#mvc)
- [Callback](#callback)

![](https://media.tenor.com/Xw9NRtyNMb4AAAAM/simpson.gif)

# Supplements

## process.argv

<https://www.geeksforgeeks.org/node-js-process-argv-property/>

## arrow function

<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions>

## built-in function

<https://www.tutorialspoint.com/javascript/javascript_builtin_functions.htm>

## destructuring

<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment>

## Module Exports

```js
module.exports = /* functions, variables, class, etc that you want to exports */
```

# OOP

OOP adalah sebuah paradigma pemograman yang berorientasi kepada Object. Dimana setiap Object bisa terbentuk dari sebuah Class.

## Class

Sebuah rancangan dari object yang biasanya terdiri dari nama class, attributes, dan methods

## Object

Hasil instance dari sebuah class

## Method

Function(s) yang ada dalam sebuah class, biasanya menggambarkan behavior dari object, seperti: `move()`, `upgrade()`, etc.

>**Method Chaining**
>
> Sebuah cara untuk memanggil beberapa method secara berturut-turut dari satu object yang sama.

## Attribute/Property

Atribut yang dimiliki oleh sebuah object seperti nama, warna, tipe, dsb.

## Reference

- [OOP Slide](https://docs.google.com/presentation/d/1MLDwuf-kCtbzpBt80KKpnCWUCn887CRQ/edit?usp=sharing&ouid=101049111366793104727&rtpof=true&sd=true)
- [Method Chaining](https://docs.google.com/presentation/d/1t966Oo8xQimSw_RvZIWKX1gG7ft9uXkh/edit?usp=sharing&ouid=101049111366793104727&rtpof=true&sd=true)

# OOP Characteristics

## Abstraction

Abstraksi adalah menyembunyikan kompleksitas dari sebuah class.
>Seperti halnya mesin ATM, kita tidak perlu tahu bagaimana proses dibelakang mesin tersebut ketika kita ingin melakukan transaksi.

![abstraction](https://www.sitesbay.com/java/images/real-life-example-of-abstraction.png)

## Encapsulation

Mengelompokkan data (attributes dan/atau methods) dari sebuah class dalam sebuah "kapsul".

![encapsulation](https://media.geeksforgeeks.org/wp-content/uploads/Encapsulation.jpg)

## Inheritance

Parent Class dapat menurunkan atribut/method nya ke Child Class.

![inheritance](https://qph.cf2.quoracdn.net/main-qimg-8199e9ee4e43b3f08c4def77081841a0-pjlq)

## Polymorphism

Sebuah class dapat menjadi berbagai macam "bentuk" (polymorph). Biasanya didalam polymorph terdapat:

- Overiding: Membuat method dengan nama yang sama dengan method parent nya, namun isi di dalamnya berbeda.
- Overloading: Membuat **beberapa** method dengan nama yang sama dengan method parent nya, namun memiliki parameter yang berbeda2.

> Seperti Ben Ten, dia bisa berubah bentuk menjadi apa saja sehingga pastinya memiliki atribut dan behavior yang berbeda2.

![polymorph](https://3.bp.blogspot.com/-EMw9SNXIH5U/VvgISHLh3VI/AAAAAAAADyY/YEKepM-DVHIGjUKf-fgDFg-QcUb4MwVoQ/s1600/polymorphism%2Bex1.png)

## Reference

- [OOP Characteristics](https://docs.google.com/presentation/d/1eWHTo8qYsjkH5Ve405CP6IWFSMe3wrFu/edit?usp=sharing&ouid=101049111366793104727&rtpof=true&sd=true)

# OOP Relationship

- Composition

>Contoh: Smartphone & Aplikasi, kita tidak dapat menginstall/membuka Aplikasi jika tidak memiliki Smartphone

- Aggregation

>Contoh: Smartphone & Orang, tiap orang bisa memiliki 1 atau lebih smartphone.

## Reference

- [Common OOP Relationships](https://dev.to/tommyc/common-types-of-oop-relationships-and-their-uml-representation-5b27)
- [Difference Between Composition & Aggregation](https://softwareengineering.stackexchange.com/questions/61376/aggregation-vs-composition)

# Factory Method

Method yang bisa kita gunakan untuk meng-instantiate sebuah Object.

![contoh factory](https://refactoring.guru/images/patterns/content/factory-method/factory-method-en-2x.png?id=b3961995a4449fb90820a693013511df)
> pada contoh diatas, Factory method **Logistic** akan menghasilkan instance **RoadLogistics** dan **SeaLogistics**

## Reference

- [Factory Method](https://refactoring.guru/design-patterns/factory-method)

# MVC

Sebuah pattern dalam programming yang menerapkan prinsip "Separation of Concerns". Biasanya dalam project aplikasi MVC terdapat 3 folder, yakni Models, View, dan Controller.

- Model: Me-manage data dan business logic. Biasanya seluruh kegiatan yang berhubungan dengan pengolahan data terjadi disini.
- View: Bertugas menampilkan data agar bisa dilihat oleh user
- Controller: Menghubungkan View dengan Model. Misal, jika View ingin menampilkan data yang berkaitan dengan **User** maka Controller akan menghubungkan nya dengan Model **User**.

![MVC](https://developer.mozilla.org/en-US/docs/Glossary/MVC/model-view-controller-light-blue.png)

## Reference

- [What is MVC](https://developer.mozilla.org/en-US/docs/Glossary/MVC)

# Callback

Secara sederhana, Callback adalah sebuah function yang dapat digunakan oleh function lain sebagai argument/parameter, seperti variable.

## Beware of Callback Hell

![](https://res.cloudinary.com/practicaldev/image/fetch/s--c0aEZX7m--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/b8euo2n7twvgh3dbuatd.jpeg)

## Reference

- [Panduan Callback](https://medium.com/coderupa/panduan-komplit-asynchronous-programming-pada-javascript-part-2-callback-3a717df6cfdf)
- [Understanding Callback](https://dev.to/nena/understanding-callbacks-2m57)
- [Asynchronous Javascript](https://nodejs.dev/en/learn/javascript-asynchronous-programming-and-callbacks/)
- [Simple Guide to Asynchronous - Difference between Synchronous & Asynchronous](https://dev.to/koladev/a-simple-guide-to-asynchronous-javascript-callbacks-promises-async-await-4m03#1-synchronous-vs-asynchronous)
