# Recap Week 2

- [Functions](#functions)
  - [Modular Functions](#modular-functions)
- [Array](#array)
  - [Multi-dimentional Array](#multi-dimentional-array)
- [References for Self-Taught](#references-for-self-taught)

![](https://media1.giphy.com/media/lzz3B3xLZluuY/giphy.gif?cid=ecf05e472v17qjebjeg8yz8t25ux5rp6p7n5xmnh8hhy065w&rid=giphy.gif&ct=g)

# Functions

- Functions adalah sebuah code block yang disusun untuk menjalankan suatu proses.
- Setelah menyelesaikan suatu proses, functions dapat mengembalikan `value` dengan menggunakan syntax `return`.

Bentuk functions

```js
// Functions dengan return
function nameFunc(param1, param2, ..., paramN) {
  /* Isi dari function berupa tindakan */
  // ...
  return [expression];
}

// Functions dengan tanpa return
function nameFunc2(param1, param2, ..., paramN) {
  /* Isi dari function berupa tindakan */
  // ...
}
```

## Modular Functions

- Kita dapat membuat sebuah program yang terdiri dari beberapa functions, dimana setiap functions tersebut dapat saling terhubung.

Contoh modular function:

```js
function funcA(param1, param2, ..., paramN) {
  /* Isi dari function berupa tindakan */
  // ...
  return [expression];
}

function funcB(param1, param2, ..., paramN) {
  // funcB memanggil funcA untuk dapat menyelesaikan proses
  // ...
  return [expression]
}

console.log(funcB)
```

# Array

- Sebuah tipe data yang terstruktur, yang berguna untuk menyimpan kumpulan data yang sejenis. Contoh: array of strings, array of numbers, array of objects, etc.
- Kita dapat memanipulasi isi dari array dengan menggunakan beberapa built-in functions, seperti `push`, `pop`, `unshift`, `shift`, dsb.

Contoh array

```js
// create an array
let arrA = [data1, data2, ..., dataN]

// accessing one element/item in array
arrA[0] // data in index 0
arrA[3] // data in index 3
arrA[N] // data in index N

// push new value to array
arrA.push(value)

// pop value from array
arrA.pop(value)

// get length of an array
arrA.length
```

## Multi-dimentional Array

- Sebuah array yang terdiri dari array (nested array)
![](https://media0.giphy.com/media/lXu72d4iKwqek/giphy.gif?cid=ecf05e47cqktbb7eabmkvuggvlflafdl59ubb4zdhcilz2bj&rid=giphy.gif&ct=g)

Contoh array multi-dimensi

```js
// create multi-dimentional array
let arrA = [[dataA1, dataA2], [dataB1, dataB2], ..., [dataN1, dataN2]]
```

# References for Self-Taught

![](https://media2.giphy.com/media/j1Xyt3DHfJcmk/200.webp?cid=ecf05e47212x7wjpd6cexz5ccj1hmfvpym003js8cwknf6vl&rid=200.webp&ct=g)

- [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
- [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- [Default Parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)
- [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [Multi-dimentional Array](https://www.geeksforgeeks.org/javascript-multidimensional-array/)

## Video References

- [Array](https://drive.google.com/drive/folders/1t_7rAu9Nt4ZJBJjXftglIZJQZET2D-vi)
- [Functions](https://www.youtube.com/watch?v=gigtS_5KOqo)
