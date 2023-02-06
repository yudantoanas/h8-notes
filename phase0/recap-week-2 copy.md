# Recap Week 3

- [Object](#object-literal)
- [Object Array](#object-array)
- [References for Self-Taught](#references-for-self-taught)

![](https://media4.giphy.com/media/wpoLqr5FT1sY0/giphy.gif?cid=ecf05e47hbnc3m5rdrk38ce4wuzg8y6otyy9j5mxr7vyivu1&rid=giphy.gif&ct=g)

# Object Literal

- Setiap object memiliki key/property/attribute yang berbentuk `key:value`
- Nama sebuah key biasanya hanya 1 kata. Namun jika kita ingin membuat key yang terdiri dari 2 kata atau lebih, kita bisa mengggunakan `" "`. Contoh `"angka bagus": 10`.
- Setiap key pada object bersifat unik.
- Contoh:

```js
// define object
let object = {
  prop1: "Hello"
  prop2: "World"
  "user age": 15
}

// get key from object
object.prop1
object["user age"]

// update value of a key
object.prop1 = "Test"
```

# Object Array

- Array yang terdiri dari kumpulan object

![](https://media3.giphy.com/media/l3q2K5jinAlChoCLS/giphy.gif?cid=ecf05e47sr3vwmvjp1lqn8i27gjowoilvkw2rtbewfojv682&rid=giphy.gif&ct=g)

- Contoh:

```js
let person1 = {
  name: "James"
}
let person2 = {
  name: "Bond"
}
let objects = [person1, person2]

// get key from one of the object in array
objects[0].name
```

# References for Self-Taught

![](https://media2.giphy.com/media/3o7abGQa0aRJUurpII/giphy.gif?cid=790b76115496294f1dfb6cb86fa8f73cbc58592664d0284a&rid=giphy.gif&ct=g)

- [Objects](https://www.w3schools.com/js/js_objects.asp)
- [Array of Objects](https://www.freecodecamp.org/news/javascript-array-of-objects-tutorial-how-to-create-update-and-loop-through-objects-using-js-array-methods/)

## Video References

- [An Encounter with JavaScript Objects](https://youtu.be/napDjGFjHR0)
- [Object](https://drive.google.com/drive/folders/1BvYvYJeSwBoNMexPbp7jDCYzRchz0kEp)
