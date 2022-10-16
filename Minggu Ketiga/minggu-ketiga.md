# Array & Multi Dimensional Array

## **Array**
Array adalah suatu tipe data yang dapat menyimpan sekumpulan tipe data lainnya. Array dapat menyimpan tipe data apapun, baik tipe data primitif maupun tipe data objek. Array juga dapat menyimpan tipe data yang berbeda-beda. Contoh Array adalah sebagai berikut :
```javascript
 let contohArray = [1,'dua',true];
```
Untuk membuat suatu array di javascript, kita dapat menggunakan tanda kurung siku `[]` dan di dalamnya kita dapat menuliskan tipe data apa saja yang kita inginkan. Untuk mengakses suatu elemen di dalam array, kita dapat menggunakan tanda kurung siku `[]` dan di dalamnya kita dapat menuliskan index dari elemen yang kita inginkan. Index pada array dimulai dari 0. Contoh pengaksesan elemen array adalah sebagai berikut :
```javascript
 let contohArray = [1,'dua',true];
 console.log(contohArray[0]); // 1
 console.log(contohArray[1]); // dua
 console.log(contohArray[2]); // true
```
Seperti tipe data lainnya, kita juga dapat mengubah nilai dari suatu array. Untuk mengubah nilai dari suatu array kita dapat mengakses lewat indexnya. Contohnya adalah sebagai berikut :
```javascript
 let contohArray = [1,'dua',true];
 contohArray[0] = 2;
 console.log(contohArray[0]); // 2
```

Untuk penggunaan `const` pada array, kita dapat mengubah nilai dari suatu elemen array, namun kita tidak dapat mengubah array tersebut dengan array yang lain. Contoh penggunaan `const` pada array adalah sebagai berikut :
```javascript
 const contohArray = [1,'dua',true];
 contohArray[0] = 2;
 console.log(contohArray[0]); // 2
 contohArray = [1,2,3]; // TypeError : Assignment to constant variable.
```
Array adalah tipe data yang cukup spesial, pasalnya tipe data ini memiliki beberapa properti dan method yang telah disediakan. Properti dan method tersebut dapat kita gunakan untuk memanipulasi array. Beberapa properrti bawaan dari Array adalah sebagai berikut :
- `length` : properti ini digunakan untuk mengetahui panjang dari array. Contohnya :
```javascript
 let contohArray = [1,'dua',true];
 console.log(contohArray.length); // 3
```
- `constructor` : properti ini digunakan untuk mengetahui tipe data dari array. Contohnya :
```javascript
 let contohArray = [1,'dua',true];
 console.log(contohArray.constructor); // [Function: Array]
```
- `prototype` : properti ini digunakan untuk menambahkan properti maupun method baru terhadap array. Contohnya :
```javascript
    Array.prototype.methodBaru = function() {
  for (let i = 0; i < this.length; i++) {
    this[i] = this[i].toUpperCase();
  }
}
    let contohArray = ['satu','dua','tiga'];
    contohArray.methodBaru();
    console.log(contohArray); // [ 'SATU', 'DUA', 'TIGA' ]
```
lalu ada juga beberapa method bawaan yang telah dimiliki oleh setiap array. Beberapa method tersebut adalah sebagai berikut :
- `push()` : method ini digunakan untuk menambahkan elemen baru di akhir array. Contohnya :
```javascript
 let contohArray = [1,'dua',true];
 contohArray.push('empat');
 console.log(contohArray); // [ 1, 'dua', true, 'empat' ]
```
- `pop()` : method ini digunakan untuk menghapus elemen terakhir dari array. Contohnya :
```javascript
 let contohArray = [1,'dua',true];
 contohArray.pop();
 console.log(contohArray); // [ 1, 'dua' ]
```
- `shift()` : method ini digunakan untuk menghapus elemen pertama dari array. Contohnya :
```javascript
 let contohArray = [1,'dua',true];
 contohArray.shift();
 console.log(contohArray); // [ 'dua', true ]
```
- `unshift()` : method ini digunakan untuk menambahkan elemen baru di awal array. Contohnya :
```javascript
 let contohArray = [1,'dua',true];
 contohArray.unshift('nol');
 console.log(contohArray); // [ 'nol', 1, 'dua', true ]
```
- `sort()` : method ini digunakan untuk mengurutkan elemen array. Contohnya :
```javascript
 let contohArray = [1,3,2];
 contohArray.sort();
 console.log(contohArray); // [ 1, 2, 3 ]
```
Selanjutnya, untuk melakukan looping pada setiap elemen dari array, kita bisa menggunakan method bawaan yaitu `forEach()` dan `map()`.
- `forEach()` : method ini digunakan untuk melakukan looping pada setiap elemen dari array. Method ini menerima 2 parameter, yaitu function yang akan dijalankan untuk setiap elemennya dan `this`. Untuk function yang akan dijalankan juga dapat menerima 3 parameter, yaitu value elemen, index elemen, dan array saat ini. Contohnya :
```javascript
 let contohArray = [1,2,3];
 contohArray.forEach((nilai,index,arr) => {
    contohArray[index] = nilai * 2;
    console.log(arr);
 });
 // [2,2,3]
 // [2,4,3]
 // [2,4,6]
```
- `map()` : method ini digunakan untuk melakukan looping pada setiap elemen dari array sama seperti forEach, hanya saja method `map()` dapat mengembalikan array baru. Contohnya :
```javascript
 let contohArray = [1,2,3];
 let contohArrayBaru = contohArray.map((elemen) => {
  return elemen * 2;
 });
 console.log(contohArrayBaru); // [ 2, 4, 6 ]
``` 
## **Multi Dimensional Array**
Array juga dapat memiliki dimensi lebih dari satu. Contohnya adalah sebagai berikut :
```javascript
 let contohArray = [[1,2,3],[4,5,6],[7,8,9]];
 console.log(contohArray[0][0]); // 1
 console.log(contohArray[0][1]); // 2
 console.log(contohArray[0][2]); // 3
 console.log(contohArray[1][0]); // 4
 console.log(contohArray[1][1]); // 5
 console.log(contohArray[1][2]); // 6
 console.log(contohArray[2][0]); // 7
 console.log(contohArray[2][1]); // 8
 console.log(contohArray[2][2]); // 9
```
Untuk melakukan perulangan juga sama seperti array satu dimensional, hanya saja kita perlu melakukan perulangan lagi untuk setiap elemen dari array satu dimensional. Contohnya :
```javascript
 let contohArray = [[1,2,3],[4,5,6],[7,8,9]];
 for (let i = 0; i < contohArray.length; i++) {
  for (let j = 0; j < contohArray[i].length; j++) {
    console.log(contohArray[i][j]);
  }
 }
```

# Object and Array of Object

## **Object**
Object adalah tipe data yang dapat menyimpan banyak data dengan tipe data yang berbeda. Object juga dapat disebut sebagai sebuah kumpulan dari properti dan method. Ya, tipe data object sebenarnya hampir sama dengan tipe data array, hanya saja ada beberapa perbedaan diantara keduanya. Jika nilai dari elemen array diakses melalui indexnya, sedangkan nilai dari elemen objek diambil melalui keynya. Jika elemen pada array hanya berupa nilai, maka elemen pada object bisa berupa nilai (property) ataupun fungsi (method) Contohnya :
```javascript
 let contohObject = {
  nama: 'John',
  umur: 20,
  pekerjaan: 'Programmer',
  status: 'Belum Menikah',
  alamat: {
    jalan: 'Jl. ABC',
    kota: 'Jakarta',
    provinsi: 'DKI Jakarta'
  },
  hobi: ['Membaca','Menulis','Menggambar'],
  namaLengkap: function() {
    return this.nama + ' ' + this.umur;
  }
};
```
Untuk mengakses object kita bisa langsung panggil namanya seperti biasa, sedangkan untuk mengakses properti maupun method didalamnya, kita bisa gunakan notasi titik (.) atau notasi kurung siku ([]). Kurung siku digunakan untuk penulisan key yang terdapat spasi di dalamnya, seperti berikut :
```javascript
let contohObject = {
    namaDepan: 'John',
    'nama Belakang': 'Doe',
    umur: 20,
    pekerjaan: 'Programmer',
    'nama lengkap': function() {
        return `${this.namaDepan} + ' ' + ${this['nama belakang']}`;
    }
};
console.log(contohObject.namaDepan); // John
console.log(contohObject['nama belakang']); // Doe
console.log(contohObject.namaLengkap()); // John Doe
```
Seperti tipe data lainnya, kita juga bisa mengubah nilai dari properti atau method didalam object. Contohnya :
```javascript
let contohObject = {
    namaDepan: 'John',
    'nama Belakang': 'Doe',
    umur: 20,
    pekerjaan: 'Programmer',
    'nama lengkap': function() {
        return `${this.namaDepan} + ' ' + ${this['nama belakang']}`;
    }
};
contohObject.namaDepan = 'Jane';
contohObject['nama belakang'] = 'Doe';

// Bisa untuk menambah properti atau method baru
contohObject.isMenikah = false;
```
Namun berbeda dengan array, ketika suatu object dideklarasikan dengan `const`, kita tidak bisa mengubah nilai dari properti atau method didalamnya. Contohnya :
```javascript
const contohObject = {
    namaDepan: 'John',
    'nama Belakang': 'Doe'
};
contohObject.namaDepan = 'Jane'; // Error
```
Selain itu, kita juga bisa mengubah property atau method didalam object dengan mengirimkan object sebagai argumen dari suatu fungsi. Contohnya :
```javascript
function ubahObject(obj) {
    obj.namaDepan = 'Jane';
}
let contohObject = {
    namaDepan: 'John',
    'nama Belakang': 'Doe'
};
ubahObject(contohObject);
console.log(contohObject.namaDepan); // Jane
```
Kita juga bisa menghapus properti atau method didalam object dengan menggunakan `delete`. Contohnya :
```javascript
let contohObject = {
    namaDepan: 'John',
    'nama Belakang': 'Doe'
};
delete contohObject.namaDepan;
```
Untuk melakukan perulangan pada object, kita bisa menggunakan `for...in` atau `Object.keys()`. Contohnya :
```javascript
let contohObject = {
    namaDepan: 'John',
    'nama Belakang': 'Doe',
    umur: 20,
    pekerjaan: 'Programmer'
};
for (let key in contohObject) {
    console.log(contohObject[key]);
}
// John
// Doe
// 20
// Programmer
```
atau dapat juga seperti ini :

```javascript
let contohObject = {
    namaDepan: 'John',
    'nama Belakang': 'Doe',
    umur: 20,
    pekerjaan: 'Programmer'
};
let keys = Object.keys(contohObject);
for (let i = 0; i < keys.length; i++) {
    console.log(contohObject[keys[i]]);
}
// John
// Doe
// 20
// Programmer
```
## **Array of Object**
Jika kita ingin menyimpan banyak object, kita bisa menggunakan array of object. Contohnya :
```javascript
let contohArray = [
    {
        namaDepan: 'John',
        'nama Belakang': 'Doe',
        umur: 20,
        pekerjaan: 'Programmer'
    },
    {
        namaDepan: 'Jane',
        'nama Belakang': 'Doe',
        umur: 20,
        pekerjaan: 'Desainer'
    }
];
console.log(contohArray[0].namaDepan); // John
```

# Recursive
Recursive adalah sebuah fungsi yang memanggil dirinya sendiri. Paradigma ini biasa digunakan dalam perhitungan matematis dan hal lain yang berhubungan dengan kalkulasi. Contohnya :
```javascript
function faktorial(n) {
    if (n === 0) {
        return 1;
    } else {
        return n * faktorial(n - 1);
    }
}
console.log(faktorial(5)); // 120
```
Setiap fungsi rekursif haruslah memiliki nilai kondisi akhir. Jika tidak, maka fungsi tersebut akan terus memanggil dirinya sendiri tanpa henti. Contohnya :
```javascript
function faktorial(n) {
    return n * faktorial(n - 1);
}
console.log(faktorial(5)); // Infinity
```

# Modules
Modul adalah sebuah fungsi yang dapat digunakan kembali di berbagai tempat. Dalam JavaScript, modul dapat didefinisikan dengan menggunakan `export` dan `import`. Contohnya :
```javascript
// file: myModule.js
export function myFunction() {
    console.log('Hello World');
}
```
```javascript
// file: index.js
import { myFunction } from './myModule.js';
myFunction(); // Hello World
```
Kita juga bisa mengimpor semua modul dengan menggunakan `*`. Contohnya :
```javascript
// file: myModule.js
export function myFunction() {
    console.log('Hello World');
}
export function myFunction2() {
    console.log('Hello World 2');
}
```
```javascript
// file: index.js
import * as myModule from './myModule.js';
myModule.myFunction(); // Hello World
myModule.myFunction2(); // Hello World 2
```
Kita juga bisa mengimpor modul secara default. Contohnya :
```javascript
// file: myModule.js
export default function myFunction() {
    console.log('Hello World');
}
```
```javascript
// file: index.js
import myFunction from './myModule.js';
myFunction(); // Hello World
```
Kita juga bisa mengimpor modul dengan menggunakan `require()`. Contohnya :
```javascript
// file: myModule.js
module.exports = function myFunction() {
    console.log('Hello World');
}
```
```javascript
// file: index.js
const myFunction = require('./myModule.js');
myFunction(); // Hello World
```
# Web Storage
Web Storage adalah sebuah API yang digunakan untuk menyimpan data di browser. Web Storage terdiri dari 2 jenis, yaitu `localStorage` dan `sessionStorage`. `localStorage` adalah sebuah objek yang menyimpan data tanpa batas waktu. Sedangkan `sessionStorage` adalah sebuah objek yang menyimpan data selama sesi browser. Kedua jenis web storage tersebut menyimpan data berupa pasangan key dan value. Contohnya :
```javascript
localStorage.setItem('nama', 'John');
sessionStorage.setItem('nama', 'Doe');
```
Untuk menghapus data, kita bisa menggunakan `removeItem()`. Contohnya :
```javascript
localStorage.removeItem('nama');
sessionStorage.removeItem('nama');
```
Untuk menghapus semua data, kita bisa menggunakan `clear()`. Contohnya :
```javascript
localStorage.clear();
sessionStorage.clear();
```
Untuk mengambil data, kita bisa menggunakan `getItem()`. Contohnya :
```javascript
const nama1 = localStorage.getItem('nama');
const nama2 = sessionStorage.getItem('nama');
console.log(nama1); // John
console.log(nama2); // Doe
```
Data-data yang disimpan pada localStorage maupun sessionStorage bersifat local, artinya data-data tersebut hanya ada di browser saja, dan tidak dapat diakses melalui server. Beberapa perbedaan antara localStorage dan sessionStorage adalah sebagai berikut :
- localStorage menyimpan data tanpa batas waktu, sedangkan sessionStorage menyimpan data selama sesi browser (selama browser terbuka).
- localStorage dapat diakses melalui semua tab browser, sedangkan sessionStorage hanya dapat diakses melalui tab yang sama.
- localStorage dapat menyimpan data dengan ukuran hingga 10 MB, sedangkan sessionStorage hanya dapat menyimpan data dengan ukuran hingga 5 MB.

Selain localStorage dan sessionStorage, kita juga bisa menggunakan cookies untuk menyimpan data. Cookies adalah sebuah file yang disimpan di browser. Cookies dapat disimpan di browser dengan menggunakan fungsi `document.cookie`. Contohnya :

```javascript
document.cookie = 'nama=John';
```
Untuk mengambil data, kita bisa menggunakan fungsi `document.cookie`. Contohnya :

```javascript
const cookies = document.cookie;
console.log(cookies); // nama=John
```
Beberapa fitur yang dimiliki cookies adalah sebagai berikut :
- expire : menentukan waktu kedaluwarsa cookies.
- secure : menentukan apakah cookies hanya dapat diakses melalui HTTPS.
- domain : menentukan domain mana yang dapat mengakses cookies.
- path : menentukan path mana yang dapat mengakses cookies.
- httpOnly : menentukan apakah cookies hanya dapat diakses melalui HTTP.

Berbeda dengan localStorage dan sessionStorage, cookies dapat diakses melalui server dan dapat dikirimkan melalui request HTTP. Selain itu, cookies juga hanya dapat menyimpan data dengan ukuran hingga 4 KB.

# Asynchronous Javascript
Pada dasarnya, JavaScript adalah bahasa pemrograman yang bersifat synchronous. Artinya, kode JavaScript akan dieksekusi secara berurutan. Contohnya :
```javascript
console.log('Hello');
console.log('World');
```
Kode di atas akan menampilkan output `Hello` dan `World` secara berurutan. Namun, apa jadinya jika perintah `console.log('Hello')` membutuhkan waktu eksekusi yang lama? Tentunya kode JavaScript akan terhenti (blocking) sampai perintah `console.log('Hello')` selesai dieksekusi. Untuk mengatasi hal tersebut lah Asynchronous Javascript muncul.  

## **Pengenalan**
Asynchronous JavaScript adalah sebuah teknik yang digunakan untuk menjalankan kode JavaScript secara asynchronous (bersamaan). Dengan menggunakan asynchronous JavaScript, kita bisa menjalankan kode JavaScript secara asynchronous tanpa harus menunggu kode sebelumnya selesai dieksekusi. Contohnya :
```javascript
setTimeout(() => {
    console.log('Hello');
}, 1000);
console.log('World');
```
Kode di atas akan menampilkan output `World` dan `Hello` secara berurutan. Karena kode `console.log('Hello')` dieksekusi secara asynchronous, maka kode `console.log('World')` akan dieksekusi terlebih dahulu. Ada beberapa cara untuk menjalankan kode JavaScript secara asynchronous, yaitu :
- Callback
- Promise
- Async/Await

## **Callback**
Callback adalah sebuah fungsi yang digunakan sebagai argumen pada fungsi lain. Fungsi ini dieksekusi setelah fungsi utamanya selesai dieksekusi. Contohnya :
```javascript
function myFunction(callback) {
    setTimeout(() => {
        console.log('Hello');
        callback();
    }, 1000);
}
myFunction(() => {
    console.log('World');
});
```
Kode di atas akan menampilkan output `Hello` dan `World` secara berurutan. Karena fungsi `myFunction()` dieksekusi secara asynchronous, maka fungsi `console.log('World')` akan dieksekusi setelah fungsi `myFunction()` selesai dieksekusi.

## **Promise**
Promise adalah sebuah objek yang digunakan untuk menangani hasil dari sebuah operasi yang asynchronous. Promise memiliki 3 state, yaitu :
- Pending : state awal dari Promise.
- Fulfilled : state ketika Promise berhasil.
- Rejected : state ketika Promise gagal.

Promise menerima dua parameter, yaitu :
- resolve : parameter yang digunakan ketika Promise berhasil.
- reject : parameter yang digunakan ketika Promise gagal.

Untuk membuat Promise, kita bisa menggunakan `new Promise()`. Dan untuk menangani hasil dari Promise, kita bisa menggunakan `then()` dan `catch()`. `then()` digunakan ketika Promise berhasil, sedangkan `catch()` digunakan ketika Promise gagal. Kita juga bisa menggunakan `finally()` untuk menangani hasil dari Promise, baik berhasil maupun gagal.

contoh :
```javascript
const myPromise = new Promise((resolve, reject, finally) => {
    const berhasilKah = true;
    if (berhasilKah) {
        resolve('Berhasil Bro');
    } else {
        reject('Error Bro');
    }
});
myPromise
.then((result) => {
    console.log(result);
});
.catch((error) => {
    console.log(error);
});
.finally(() => {
    console.log('Akhirnya Selesai Bro');
});
```
Kode di atas akan menampilkan output `Berhasil Bro` dan `Akhirnya Selesai Bro` secara berurutan. Karena Promise berhasil, maka fungsi `then()` akan dieksekusi. Namun, jika Promise gagal, maka fungsi `catch()` akan dieksekusi.
