# Recap Week 1

- [Terminal & Git](#terminal-and-git)
- [Algorithm and Pseudocode](#algorithm-and-pseudocode)
- [Conditional and Primitive Data Types](#conditional-and-primitive-data-types-es6)
- [Advanced Conditional](#advanced-conditional)
- [Iterasi](#iterasi)
- [Nested Loop](#nested-loop)
- [References for Self-Taught](#references-for-self-taught)

![](https://media0.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif?cid=ecf05e47o4oqwdeshc3a4fzg9kk0cg81omx6thxtaz37t8gq&rid=giphy.gif&ct=g)

## Terminal and Git

Terminal

- Sebuah interface berupa command-line yang bisa digunakan untuk mengoperasikan komputer
- beberapa command terminal antara lain, `cd`, `pwd`, `ls`, `touch`, `cp`, `mv`, `rm`, `mkdir`, `rm -rf`

Git

- Version Control System (VCS), sebuah system yang bisa mencatat setiap update dalam sebuah source code
- beberapa command git, `git add`, `git commit -m`, `git status`, `git push`, `git clone`

> Git !== Github

## Algorithm and Pseudocode

- Algoritma adalah kumpulan langkah yang tersusun untuk menyelesaikan masalah
- Pseudocode adalah penjabaran deskriptif dari sebuah algoritma yang terstruktur sesuai dengan konvensi/kesepakatan antara developer.

> References
>
> <https://github.com/ideaspaper/p0-class-notes/blob/master/notes/pseudocode-note-1.md>
>
> <https://github.com/ideaspaper/p0-class-notes/blob/master/notes/pseudocode-note-2.md>
>
> <https://github.com/ideaspaper/p0-class-notes/blob/master/notes/pseudocode-note-3.md>

## Conditional and Primitive Data Types (ES6)

- Data Types
  - Number (integer)
  - String
  - Boolean

- Variables -> menampung sebuah data
  - declaration -> membuat sebuah variable tanpa meng-assign sebuah value
  ```js var x;```
  - assigment -> meng-assign sebuah variable dengan sebuah value (menggunakan `=`)
  ```js x = 10```
  - declaration + assigment
  ```js var z = 666```

- Math Operators (`+`, `-`, `*`, `/`, `%`)

- Comparison Operators (`==`, `>`, `<`, `>=`, dst..)

- Logical Operators (`&&`, `||`)

- Terdapat kondisi didalam if/else if, sedangkan else tidak ada kondisi.

- Truthy & Falsy values adalah values yang bisa menjadi true/false sesuai kondisi

- Truthy adalah value yang tidak false
- Falsy adalah value yang tidak true

contoh bentuk if-else, if-elseif-else

```js
if (condition) {
  statement1
} else {
  statement2
}

if (condition1) {
  statement1
} else if (condition2) {
  statement2
} else {
  statement3
}
```

## Advanced Conditional

- Switch Case

contoh bentuk switch case

```js
switch (expression) {
  case value1:
    //Statements executed when the
    //result of expression matches value1
    [break;]
  case value2:
    //Statements executed when the
    //result of expression matches value2
    [break;]
  ...
  case valueN:
    //Statements executed when the
    //result of expression matches valueN
    [break;]
  [default:
    //Statements executed when none of
    //the values match the value of the expression
    [break;]]
}
```
- `default` dalam switch case adalah opsional, seperti halnya `else` dalam if-else, `default` akan berjalan jika **tidak** ada case yang sesuai dengan ekspresi yang diberikan

- `break` dalam switch case adalah opsional, namun perlu diingat jika dalam sebuah switch case tidak dikasih break, maka statement-statement dari case lain dibawahnya akan tereksekusi juga.

- Nested Conditional -> ada if-else didalam sebuah if-else

contoh bentuk nested conditional

```js
if (condition) {
  if (condition1) {
    statement1
  } else {
    statement3
  }
} else {
  statement2
}
```

## Iterasi

- DRY -> Don't Repeat Yourself.
- Iterasi dipakai agar kita tidak mengulang proses yang sama
- Iterasi akan membuat code menjadi dinamis

- Struktur iterasi

  - inisialisasi
  - batas/kondisi
  - eksekusi (increment/decrement)
  - aksi/statement

- Macam-macam iterasi: For, While, Do-While

contoh bentuk iterasi:

```js
for (initialization; condition; eksekusi) {
  statement
}

while (condition) {
  statement
}

do {
  statement
}
while (condition)
```

> Referensi
>
> Pseudocode: <https://github.com/ideaspaper/p0-class-notes/blob/master/notes/pseudocode-note-2.md>

## Nested Loop

- Ada loop di dalam loop

contoh bentuk nested for-for

```js
for (initialization1; condition1; eksekusi1) {
  for (initialization2; condition2; eksekusi2) {
    statement
  }
}
```

contoh bentuk nested loop while-for

```js
while (condition) {
  for (initialization; condition; eksekusi) {
    statement
  }
}
```

- `break` berfungsi untuk menghentikan proses perulangan yang sedang berjalan

- `continue` berfungsi untuk melewati/skip 1 proses perulangan saja

## References for Self-Taught

![](https://media4.giphy.com/media/uyoXx0qpUWfQs/giphy.gif?cid=ecf05e47ma0utvundogidenxni2ddzpv84rv5m1r6z8shzdo&rid=giphy.gif&ct=g)

Reading Materials

- [What is an algorithm and why should you care?](https://www.khanacademy.org/computing/computer-science/algorithms/intro-to-algorithms/v/what-are-algorithms)
- [A guessing game](https://www.khanacademy.org/computing/computer-science/algorithms/intro-to-algorithms/a/a-guessing-game)
- [Route Finding](https://www.khanacademy.org/computing/computer-science/algorithms/intro-to-algorithms/a/route-finding)

Documentations

- [JS variables, data types, literals, etc.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_Types)
- [assignment operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#assignment_operators)
- [comparison operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#comparison_operators)
- [artihmethic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#arithmetic_operators)
- [logical operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#logical_operators)
- [string operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#string_operators)
- [if...else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling#if...else_statement)
- [switch...case](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling#switch_statement)
- [for loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for_statement)
- [do...while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#do...while_statement)
- [while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#while_statement)
- [break statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#break_statement)
- [continue statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#continue_statement)

Exercises

- [Hello, World!](https://www.learn-js.org/en/Hello%2C_World%21)
- [Variables and Types](https://www.learn-js.org/en/Variables_and_Types)
- [Operartors](https://www.learn-js.org/en/Operators)
- [Conditions](https://www.learn-js.org/en/Conditions)
- [Loops](https://www.learn-js.org/en/Loops)

External Links

- [Programmer Zaman Now](https://www.youtube.com/watch?v=SDROba_M42g)
- [Web Programming Unpas](https://www.youtube.com/watch?v=RUTV_5m4VeI&list=PLFIM0718LjIWXagluzROrA-iBY9eeUt4w&ab_channel=WebProgrammingUNPAS)
- [FreeCodeCamp.org](https://www.freecodecamp.org/)
- [FreeCodeCamp Youtube Channel](https://www.youtube.com/watch?v=PkZNo7MFNFg)
