# Recap Week 4

- [In a nutshell](#website-in-a-nutshell)
- [HTML](#object-literal)
- [CSS](#object-array)
- [DOM](#object-array)
- [References for Self-Taught](#references-for-self-taught)

![](https://media2.giphy.com/media/YQitE4YNQNahy/giphy.gif?cid=ecf05e47tky5pfle66d4bgy16lrrrt2qm8o4c6u9ychrn1up&rid=giphy.gif&ct=g)

# Website in a nutshell

![](https://qph.cf2.quoracdn.net/main-qimg-6795e6ef1ca101a38e86eee75ed1189f-lq)

# HTML

- sebuah markup language yang menjadi backbone/kerangka dari sebuah website
- selalu mengandung tag `<html>`
- other tags:
  - `<body>`
  - `<div>`
  - `<h1>` - `<h6>`
  - `<a>`
  - `<table>`
  - and many more...
- setiap tag bisa diberikan global attribute, seperti `id` dan `class`

## Contoh syntax

```html
<!DOCTYPE html>
<html>

<head>
    <!-- head contents -->
    <title>Document</title>
</head>

<body>
    <!-- body contents -->
</body>

</html>
```

# CSS

- sebuah bahasa yang dipakai untuk mendeskripsikan bagaimana sebuah website ditampilkan.
- beberapa cara untuk implement CSS:
  - Inline
  - Internal
  - External

## Contoh syntax css

```css
h1 {
    color:blue;
    font-size:12px;
}
```

# DOM

- sebuah struktur hirarki element HTML.
- DOM is a standard for how to get, change, add, or delete HTML elements.
- pada setiap element di hirarki, kita bisa mendapatkan parent, child, dan sibling dari setiap element.
- cara get element pada HTML

```js
document.getElementById(id)
document.getElementsByTagName(tagName)
document.getElementsByClassName(className)
```

- di DOM ada Event Listener yang berfungsi untuk mendeteksi sebuah event yang terjadi di HTML element.
- di DOM juga ada alert & prompt dimana tiap fungsi ini berguna untuk memberikan interaksi lebih pada HTML kita.

## Contoh syntax DOM

```html
<!DOCTYPE html>
<html>

<head>
    <!-- head contents -->
    <title>Document</title>
</head>

<body>
    <!-- body contents -->

    <!-- JS in html -->
    <script>
      function foo() {
        console.log('hello world')
      }
    </script>

    <!-- if JS in other file, just import it -->
    <script src="script.js"></script>
</body>

</html>
```

# References for Self-Taught

![](https://media1.giphy.com/media/BPJmthQ3YRwD6QqcVD/giphy.gif?cid=ecf05e47050himu4xlfsywq1v18zdaws2wsa7mybkxwxxhna&rid=giphy.gif&ct=g)

- [HTML](https://www.w3schools.com/html/)
- [CSS](https://www.w3schools.com/css/)
- [DOM](https://www.w3schools.com/js/js_htmldom.asp)

## Video References

- [HTML](https://drive.google.com/drive/folders/1F2ug_6SyYz8W-bfiHVA4NFZD6wMN4vMJ)
- [CSS](https://drive.google.com/drive/folders/1vx7WJrN-kGplplj1IjetAQQ7wApVYazC)
- [DOM](https://drive.google.com/drive/folders/16qc3jE0aOtPKwUeMvjImshrR8gz1yDPQ)
