# Javascript Scope dan Function

## **Scope**

Scope adalah tempat dimana sebuah variabel dapat diakses. Di Javascript sendiri, scope dapat dibagi menjadi 2 yaitu **Global Scope** dan **Local Scope**. Namun, sebelum mengetahui scope, kita haruslah mengetahui apa itu blok kode.

## **Blok Kode**
Blok kode adalah kode yang berada diantara kurung kurawal `{}`. Contoh:
 ```javascript
    {
        var a = 1;
        let b = 2;
        const c = 3;
    }
```

## **Global Scope**
Global Scope adalah scope yang dapat diakses dimana saja. Variabel yang berada di dalam Global Scope dapat diakses di dalam blok kode maupun di luar blok kode. Contoh:
```javascript
    var a = 1;
    let b = 2;
    const c = 3;

    function test() {
        console.log(a);
        // Output: 1
        console.log(b);
        // Output: 2
        console.log(c);
        // Output: 3
    }

    console.log(a);
    // Output: 1
```

## **Local Scope**
Local Scope adalah scope yang hanya dapat diakses di dalam blok kode. Variabel yang berada di dalam Local Scope tidak dapat diakses di luar blok kode. Contoh:
```javascript
    {
        var a = 1;
        let b = 2;
        const c = 3;

        function test() {
            let a = 10;
            let d = 4;
            console.log(a);
            // Output: 10
            console.log(b);
            // Output: 2
            console.log(c);
            // Output: 3
        }

        console.log(a);
        // Output: 1
        console.log(d);
        // Output: ReferenceError: d is not defined
    }
```

## **Function**
Function adalah sebuah blok kode yang dapat dipanggil kapan saja. Function dapat menerima parameter dan mengembalikan nilai. Contoh:
```javascript
    function test(a, b) {
        return a + b;
    }

    console.log(test(1, 2));
    // Output: 3
```
Untuk memanggil function, kita dapat menggunakan keyword `function-name()`. Struktur dari function dapat dilihat pada gambar berikut ini :

![Function](./image/function.png)
> Sumber : https://s3.ap-south-1.amazonaws.com/s3.studytonight.com/tutorials/uploads/pictures/1587882057-1.png
<br>

## **Parameter dan Argumen**
Parameter adalah variabel yang digunakan untuk menerima nilai dari function. Parameter dapat memiliki nilai default. Contoh:
```javascript

    function test(a, b = 2) {
    // a dan b adalah parameter dari fungsi test
    // Nilai default dari b adalah 2
        return a + b;
    }

    console.log(test(1));
    // Output: 3
```
Sedangkan argumen adalah nilai yang diberikan ke function. Contoh:
```javascript
    function test(a, b) {
        return a + b;
    }

    console.log(test(1, 2));
    // 1 dan 2 adalah argumen yang dikirim ke fungsi test
    // Output: 3
```

## **Function Helper**
Kita dapat menggunakan function yang telah kita buat di dalam function lain. Contoh:
```javascript
    function test(a, b) {
        return a + b;
    }

    function test2(a, b) {
        return test(a, b) * 2;
    }

    console.log(test2(1, 2));
    // Output: 6
```

## **Arrow Function**
Arrow function adalah function yang ditulis dengan menggunakan tanda panah `=>`. Syntax ini adalah fitur baru di ES6. Contoh:
```javascript
    const test = (a, b) => {
        return a + b;
    }

    console.log(test(1, 2));
    // Output: 3
```
Kita juga dapat menyingkat arrow function dengan menghilangkan kurung kurawal dan kata kunci `return` jika statement dapat dituliskan menjadi 1 line. Contoh:
```javascript
    const test = (a, b) => a + b;

    console.log(test(1, 2));
    // Output: 3
```
Ketika kita memiliki 1 parameter, kita dapat menghilangkan kurung buka tutup. Contoh:
```javascript
    const test = a => a + 1;

    console.log(test(1));
    // Output: 2
```
Dan ketika fungsi tidak memiliki parameter, kita dapat menggantikan dengan kurung buka dan kurung tutup tanpa parameter. Contoh:
```javascript
    const test = () => 1 + 1;

    console.log(test());
    // Output: 2
```

## **Error dan Bug**
Dalam javascript terdapat beberapa jenis error yang dapat terjadi, diantaranya :
1.  ReferenceError
    Terjadi ketika kita mencoba mengakses variabel yang belum dideklarasikan.
    ```javascript
        console.log(a);
        // Output: ReferenceError: a is not defined
    ```
2. SyntaxError
    Terjadi ketika kita menulis kode yang tidak sesuai dengan sintaks javascript.
    ```javascript
        console.log(1 + );
        // Output: SyntaxError: Unexpected token ;
    ```

3. RangeError
    Terjadi ketika kita mencoba mengakses nilai yang berada di luar rentang yang ditentukan.
    ```javascript
        var foo= []
        foo.length = foo.length -1 
        // Uncaught RangeError: Invalid array length
    ```

4. TypeError
    Terjadi ketika kita mencoba mengakses nilai dengan tipe yang tidak sesuai.
    ```javascript
        var foo = {}
        foo.bar()
        // Uncaught TypeError: foo.bar is not a function
    ```

# Data Type Built in Prototype & Method
Dalam setiap bahasa pemrograman tentunya memiliki berbagai jenis tipe data. Pun begitu pada Javascript. Tipe data dalam javascript secara garis besar dibedakan menjadi 2, yaitu primitive dan non-primitive. Yang dimaksud tipe data primitive adalah adalah tipe data sederhana yang hanya memiliki sebuah value dan tidak memiliki property maupun method. Sedangkan tipe data non-primitive selain memiliki value juga memilikiproperty maupun method bawaan. Tipe data primitive disimpan dalam komputer berdasarkan nilainya. Sedangkan data bertipe non-primitive disimpan berdasarkan alamat reference. 

## **Primitive Data Type**
Javascript memiliki 7 tipe data dengan jenis primitive, yaitu :
1. String\
    Merupakan tipe data yang berupa teks. String dapat ditulis dengan menggunakan tanda kutip 1 atau 2. Contoh:

    ```javascript
        const a = "Hello World";
        const b = 'Hello World';
    ```
2. Number\
    Merupakan tipe data yang berupa angka. Number dapat berupa bilangan bulat, bilangan desimal, bilangan negatif, bilangan desimal negatif, bilangan desimal dengan notasi ilmiah, dan bilangan desimal negatif dengan notasi ilmiah. Contoh:

    ```javascript
        const a = 1;
        const b = 1.1;
        const c = -1;
        const d = -1.1;
        const e = 1e2;
        const f = -1e2;
    ```
3. Boolean\
    Merupakan tipe data yang berupa nilai true atau false. Contoh:

    ```javascript
        const a = true;
        const b = false;
    ```
4. Null\
    Merupakan tipe data yang berupa nilai kosong. Contoh:

    ```javascript
        const a = null;
    ```
5. Undefined\
    Merupakan tipe data yang berupa nilai yang belum didefinisikan. Contoh:

    ```javascript
        let a;
        console.log(a);
        // Output: undefined
    ```
6. Symbol\
    Merupakan tipe data yang berupa nilai unik. Contoh:

    ```javascript
        const a = Symbol("a");
        const b = Symbol("a");
        console.log(a === b);
        // Output: false
    ```

7. BigInt\
    Merupakan tipe data yang berupa bilangan bulat dengan nilai yang lebih besar dari Number.MAX_SAFE_INTEGER. Contoh:

    ```javascript
        const a = 9007199254740991n;
        const b = 9007199254740992n;
        console.log(a === b);
        // Output: false
    ```

Selain 7 tipe data diatas, ada satu tipe data yang muncul akibat adanya tipe data number, yaitu tipe data `NaN` atau Not a Number. 

## **Non-Primitive Data Type**
Javascript memiliki 1 tipe data dengan jenis non-primitive yaitu object. Object adalah tipe data yang dapat menyimpan lebih dari satu nilai. Object juga dapat menyimpan berbagai jenis tipe data, baik primitive maupun non-primitive. Object juga dapat menyimpan berbagai jenis method. Object dapat dibuat dengan menggunakan tanda kurung buka dan kurung tutup. Contoh:

```javascript
    const a = {};
    const b = {
        name: "John Doe",
        age: 20,
        isMarried: false,
        address: {
            street: "Jl. ABC",
            city: "Jakarta",
            country: "Indonesia"
        }
    };
```
## **Built in Prototype & Method**
Built in prototype dan method adalah prototype dan method yang sudah disediakan oleh javascript. Built in prototype dapat digunakan untuk memanipulasi tipe data. Built in prototype dapat dilihat pada [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects). Built in prototype memiliki berbagai macam method. Method-method tersebut dapat digunakan untuk memanipulasi tipe data. Berikut adalah beberapa method yang sering digunakan :
1. String
    - `charAt()`\
        Method ini digunakan untuk mengambil karakter pada index tertentu. Contoh:

        ```javascript
            const a = "Hello World";
            console.log(a.charAt(0));
            // Output: H
        ```
    - `concat()`\
        Method ini digunakan untuk menggabungkan string. Contoh:

        ```javascript
            const a = "Hello";
            const b = "World";
            console.log(a.concat(b));
            // Output: HelloWorld
        ```
    - `includes()`\
        Method ini digunakan untuk mengecek apakah string tersebut mengandung karakter tertentu. Contoh:

        ```javascript
            const a = "Hello World";
            console.log(a.includes("Hello"));
            // Output: true
        ```

2. Number
    - `toFixed()`\
        Method ini digunakan untuk memformat angka menjadi bilangan desimal. Contoh:

        ```javascript
            const a = 1.23456789;
            console.log(a.toFixed(2));
            // Output: 1.23
        ```
    - `toPrecision()`\
        Method ini digunakan untuk memformat angka menjadi bilangan desimal dengan jumlah angka sesuai dengan parameter yang diberikan. Contoh:

        ```javascript
            const a = 1.23456789;
            console.log(a.toPrecision(2));
            // Output: 1.2
        ```
    - `toString()`\
        Method ini digunakan untuk mengubah angka menjadi string. Contoh:

        ```javascript
            const a = 1;
            console.log(a.toString());
            // Output: "1"
        ```
3. Array
    - `push()`\
        Method ini digunakan untuk menambahkan item pada akhir array. Contoh:

        ```javascript
            const a = [1, 2, 3];
            a.push(4);
            console.log(a);
            // Output: [1, 2, 3, 4]
        ```
    - `pop()`\
        Method ini digunakan untuk menghapus item pada akhir array. Contoh:

        ```javascript
            const a = [1, 2, 3];
            a.pop();
            console.log(a);
            // Output: [1, 2]
        ```
    - `shift()`\
        Method ini digunakan untuk menghapus item pada awal array. Contoh:

        ```javascript
            const a = [1, 2, 3];
            a.shift();
            console.log(a);
            // Output: [2, 3]
        ```
    - `unshift()`\
        Method ini digunakan untuk menambahkan item pada awal array. Contoh:

        ```javascript
            const a = [1, 2, 3];
            a.unshift(0);
            console.log(a);
            // Output: [0, 1, 2, 3]
        ```
    - `splice()`\
        Method ini digunakan untuk menghapus item pada array. Contoh:

        ```javascript
            const a = [1, 2, 3];
            a.splice(1, 1);
            console.log(a);
            // Output: [1, 3]
        ```
    - `slice()`\
        Method ini digunakan untuk mengambil item pada array. Contoh:

        ```javascript
            const a = [1, 2, 3];
            console.log(a.slice(1, 2));
            // Output: [2]
        ```
    - `map()`\
        Method ini digunakan untuk mengubah item pada array. Contoh:

        ```javascript
            const a = [1, 2, 3];
            const b = a.map((item) => item * 2);
            console.log(b);
            // Output: [2, 4, 6]
        ```
    - `filter()`\
        Method ini digunakan untuk memfilter item pada array. Contoh:

        ```javascript
            const a = [1, 2, 3];
            const b = a.filter((item) => item > 1);
            console.log(b);
            // Output: [2, 3]
        ```

4. Math
    - `abs()`\
        Method ini digunakan untuk mengambil nilai absolut dari sebuah angka. Contoh:

        ```javascript
            const a = -1;
            console.log(Math.abs(a));
            // Output: 1
        ```
    - `ceil()`\
        Method ini digunakan untuk membulatkan angka ke atas. Contoh:

        ```javascript
            const a = 1.1;
            console.log(Math.ceil(a));
            // Output: 2
        ```
    - `floor()`\
        Method ini digunakan untuk membulatkan angka ke bawah. Contoh:

        ```javascript
            const a = 1.9;
            console.log(Math.floor(a));
            // Output: 1
        ```
    - `round()`\
        Method ini digunakan untuk membulatkan angka. Contoh:

        ```javascript
            const a = 1.5;
            console.log(Math.round(a));
            // Output: 2
        ```
    - `max()`\
        Method ini digunakan untuk mengambil nilai terbesar dari beberapa angka. Contoh:

        ```javascript
            const a = 1;
            const b = 2;
            const c = 3;
            console.log(Math.max(a, b, c));
            // Output: 3
        ```
    - `min()`\
        Method ini digunakan untuk mengambil nilai terkecil dari beberapa angka. Contoh:

        ```javascript
            const a = 1;
            const b = 2;
            const c = 3;
            console.log(Math.min(a, b, c));
            // Output: 1
        ```
    - `random()`\
        Method ini digunakan untuk mengambil angka random. Contoh:

        ```javascript
            console.log(Math.random());
            // Output: 0.123456789
        ```

# Document Object Model (DOM)
DOM (Document Object Model) adalah sebuah interface yang digunakan untuk mengakses dan memanipulasi elemen HTML. DOM merupakan bagian dari browser yang digunakan untuk mengakses dan memanipulasi elemen HTML. DOM juga merupakan bagian dari W3C DOM (Document Object Model) yang merupakan standar untuk memanipulasi HTML dan XML. DOM merupakan sebuah tree yang terdiri dari node-node yang saling berhubungan. Setiap node memiliki tipe yang berbeda-beda. Tipe node yang paling umum adalah element node, text node, dan attribute node. Element node merupakan node yang merepresentasikan elemen HTML. Text node merupakan node yang merepresentasikan teks. Attribute node merupakan node yang merepresentasikan atribut HTML.

![DOM Tree](./image/DOM-tree.png)
> Sumber : https://i.stack.imgur.com/IERlg.png

## **DOM Selection**
DOM Selection merupakan proses untuk memilih elemen HTML yang akan dimanipulasi. DOM Selection dapat dilakukan dengan menggunakan beberapa cara, yaitu :
1. Menggunakan ID\
    Cara ini digunakan untuk memilih elemen HTML yang memiliki atribut id. Cara ini dapat dilakukan dengan menggunakan method `getElementById()`. Contoh:

    ```javascript
        const a = document.getElementById("a");
    ```
2. Menggunakan Class\
    Cara ini digunakan untuk memilih elemen HTML yang memiliki atribut class. Cara ini dapat dilakukan dengan menggunakan method `getElementsByClassName()`. Contoh:

    ```javascript
        const a = document.getElementsByClassName("a");
    ```
3. Menggunakan Tag\
    Cara ini digunakan untuk memilih elemen HTML yang memiliki tag tertentu. Cara ini dapat dilakukan dengan menggunakan method `getElementsByTagName()`. Contoh:

    ```javascript
        const a = document.getElementsByTagName("a");
    ```
4. Menggunakan Query Selector\
    Cara ini digunakan untuk memilih elemen HTML yang memiliki atribut tertentu. Cara ini dapat dilakukan dengan menggunakan method `querySelector()`. Contoh:

    ```javascript
        const a = document.querySelector("#a");
    ```
5. Menggunakan Query Selector All\
    Cara ini digunakan untuk memilih elemen HTML yang memiliki atribut tertentu. Cara ini dapat dilakukan dengan menggunakan method `querySelectorAll()`. Contoh:

    ```javascript
        const a = document.querySelectorAll(".a");
    ```

## **DOM Traversing**
DOM Traversing merupakan proses untuk bergerak dari satu elemen ke elemen DOM yang lain. DOM Traversing dapat dilakukan secara 3 arah, yaitu :
1. Upward\
    Upward merupakan proses untuk bergerak dari elemen yang dipilih ke elemen yang memiliki parent. Cara ini dapat dilakukan dengan menggunakan method `parentNode`, `parentElement`, dan `closest`. Contoh:

    ```html
        <ul class="list">
            <li><a href="#">Link 1</a></li>
            <li><a href="#">Link 2</a></li>
            <li><a href="#">Link 3</a></li>
            <li><a href="#">Link 4</a></li>
            <li><a href="#">Link 5</a></li>
        </ul>
    ```

    ```javascript
        const a = document.querySelector("a");
        const b = a.parentNode;
        const c = a.parentElement;
        const d = a.closest('li');
    ```

2. Downward\
    Downward merupakan proses untuk bergerak dari elemen yang dipilih ke elemen yang memiliki child. Cara ini dapat dilakukan dengan menggunakan method `childNodes`, `children`, dan `firstElementChild`. Contoh:

    ```html
        <ul class="list">
            <li><a href="#">Link 1</a></li>
            <li><a href="#">Link 2</a></li>
            <li><a href="#">Link 3</a></li>
            <li><a href="#">Link 4</a></li>
            <li><a href="#">Link 5</a></li>
        </ul>
    ```

    ```javascript
        const a = document.querySelector("ul");
        const b = a.childNodes;
        const c = a.children;
        const d = a.firstElementChild;
    ```
    Kita juga bisa melakukan traverse downward dengan menggunakan query selector. Karena pergerakan query selector adalah ke bawah Contoh:

    ```html
        <ul class="list">
            <li><a href="#">Link 1</a></li>
            <li><a href="#">Link 2</a></li>
            <li><a href="#">Link 3</a></li>
            <li><a href="#">Link 4</a></li>
            <li><a href="#">Link 5</a></li>
        </ul>
    ```

    ```javascript
        const a = document.querySelector("ul");
        const b = a.querySelector("a");
    ```
3. Sideways\
    Sideways merupakan proses untuk bergerak dari elemen yang dipilih ke elemen yang memiliki sibling. Cara ini dapat dilakukan dengan menggunakan method `nextSibling`, `nextElementSibling`, `previousSibling`, dan `previousElementSibling`. Contoh:

    ```html
        <ul class="list">
            <li><a href="#">Link 1</a></li>
            <li><a href="#">Link 2</a></li>
            <li><a href="#">Link 3</a></li>
            <li><a href="#">Link 4</a></li>
            <li><a href="#">Link 5</a></li>
        </ul>
    ```

    ```javascript
        const a = document.querySelector("a");
        const b = a.nextSibling;
        const c = a.nextElementSibling;
        const d = a.previousSibling;
        const e = a.previousElementSibling;
    ```

## **DOM Manipulation**
DOM Manipulation merupakan proses untuk memanipulasi elemen HTML yang telah dipilih. DOM Manipulation dapat dilakukan untuk tujuan 2 hal, yaitu :
1. Manipulasi Elemen\
Beberapa manipulasi elemen yang dapat kita lakukan pada DOM antara lain :
    - Membuat elemen baru\
    Cara ini digunakan untuk membuat elemen baru. Cara ini dapat dilakukan dengan menggunakan method `createElement()`. Contoh:

    ```javascript
        const a = document.createElement("a");
    ```

    - Menghapus elemen\
    Cara ini digunakan untuk menghapus elemen. Cara ini dapat dilakukan dengan menggunakan method `remove()`. Contoh:

    ```javascript
        const a = document.querySelector("a");
        a.remove();
    ```

    - Mengganti elemen\
    Cara ini digunakan untuk mengganti elemen. Cara ini dapat dilakukan dengan menggunakan method `replaceWith()`. Contoh:

    ```javascript
        const a = document.querySelector("a");
        const b = document.createElement("p");
        a.replaceWith(b);
    ```

    - Menambahkan elemen\
    Cara ini digunakan untuk menambahkan elemen. Cara ini dapat dilakukan dengan menggunakan method `appendChild()`. Contoh:

    ```javascript
        const a = document.querySelector("a");
        const b = document.createElement("p");
        a.appendChild(b);
    ```

    - Menambahkan elemen sebelum elemen yang dipilih\
    Cara ini digunakan untuk menambahkan elemen sebelum elemen yang dipilih. Cara ini dapat dilakukan dengan menggunakan method `insertBefore()`. Contoh:

    ```javascript
        const a = document.querySelector("ul");
        let b = document.createElement("li");
        const c = document.createElement("a");
        b = b.appendChild(c);
        a.insertBefore(b, a.firstElementChild);
    ```

2. Manipulasi Style\
Beberapa manipulasi style yang dapat kita lakukan pada DOM antara lain :
    - Mengubah style\
    Cara ini digunakan untuk mengubah style. Cara ini dapat dilakukan dengan menggunakan method `style`. Contoh:

    ```javascript
        const a = document.querySelector("a");
        a.style.color = "red";
    ```

    - Menghapus style\
    Cara ini digunakan untuk menghapus style. Cara ini dapat dilakukan dengan menggunakan method `removeAttribute()`. Contoh:

    ```javascript
        const a = document.querySelector("a");
        a.removeAttribute("style");
    ```

    - Menambahkan class\
    Cara ini digunakan untuk menambahkan class. Cara ini dapat dilakukan dengan menggunakan method `classList.add()`. Contoh:

    ```javascript
        const a = document.querySelector("a");
        a.classList.add("active");
    ```

    - Menghapus class\
    Cara ini digunakan untuk menghapus class. Cara ini dapat dilakukan dengan menggunakan method `classList.remove()`. Contoh:

    ```javascript
        const a = document.querySelector("a");
        a.classList.remove("active");
    ```

    - Mengganti class\
    Cara ini digunakan untuk mengganti class. Cara ini dapat dilakukan dengan menggunakan method `classList.replace()`. Contoh:

    ```javascript
        const a = document.querySelector("a");
        a.classList.replace("active", "inactive");
    ```
## **DOM Events**
Events merupakan sebuah kejadian yang terjadi pada elemen HTML. Events dapat berupa klik, mouseover, mouseout, dll. Events dapat ditangani dengan menggunakan dua cara, yakni dengan menggunakan method `addEventListener()` ataupun dengan menggunakan attribute `onevent`. Contoh:

```html
    <button onclick="alert('Hello World!')">Click Me!</button>
```
    

```javascript
    const a = document.querySelector("button");
    a.addEventListener("click", function() {
        alert("Hello World!");
    });
```
beberapa attribute `onevent` yang dapat digunakan antara lain :
- `onclick`
- `onmouseover`
- `onmouseout`
- `onkeydown`
- `onkeyup`
- `onkeypress`
- `onload`
- `onunload`
- `onfocus`
- `onblur`
- `onchange`
- `onsubmit`
- `onreset`\
dan masih banyak lagi.

Sedangkan beberapa method `addEventListener()` yang dapat digunakan antara lain :
- `click`
- `mouseover`
- `mouseout`
- `mouseenter`
- `keydown`
- `keyup`
- `keypress`
- `load`\
dan masih banyak lagi.

## **DOM Form**
Form merupakan elemen HTML yang digunakan untuk mengambil inputan dari pengguna. Form dapat digunakan untuk mengambil inputan berupa text, checkbox, radio, dll. Form dapat ditangani dengan menggunakan dua cara, yakni dengan menggunakan method `addEventListener()` ataupun  attribute `onsubmit` dan mengambil value masing masing input satu persatu ataupun mengambil value dengan menggunakan `FormData`. Contoh pertama :
```html
    <form>
        <input id="nama" type="text" name="name" placeholder="Name">
        <input id="email" type="text" name="email" placeholder="Email">
        <input type="submit" value="Submit">
    </form>
```
```javascript
    const nama = document.querySelector("#nama").value;
    const email = document.querySelector("#email").value;
    const form = document.querySelector("form");
    form.addEventListener("submit", function(e) {
        e.preventDefault();
        console.log(nama);
        console.log(email);
    });

```
Dan contoh kedua :
```html
    <form>
        <input id="nama" type="text" name="name" placeholder="Name">
        <input id="email" type="text" name="email" placeholder="Email">
        <input type="submit" value="Submit">
    </form>
```

```javascript
    const form = document.getElementById(“form”)

    form.addEventListener(“submit”, function(event) {
	event.preventDefault()
	const formData = new FormData(form)
	const values = Object.fromEntries(formData)
```