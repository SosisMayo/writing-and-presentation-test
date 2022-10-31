# Web Server & RESTFUL API

## Web Server
Web server adalah komputer yang menyimpan, memproses, dan mengirim file website ke web browser. Web server terdiri dari 2 bagian yaitu web server software dan web server hardware. Web server software adalah software yang berfungsi untuk mengatur dan mengelola web server hardware. Web server hardware adalah hardware yang berfungsi untuk menyimpan dan memproses file website. Web server software yang paling populer adalah Apache, Nginx, dan Microsoft IIS. Web server hardware yang paling populer adalah Linux, Windows, dan Mac OS.

## Static Web Server
Static Web Server, atau tumpukan, terdiri dari komputer (perangkat keras) dengan server HTTP (perangkat lunak). Kita dapat  menyebutnya "statis" karena server mengirimkan file yang dihosting apa adanya ke browser Anda.

## Dynamic Web Server
Dynamic Web Server terdiri dari komputer (perangkat keras) dengan server HTTP (perangkat lunak) dan database (perangkat lunak). Kita dapat menyebutnya "dinamis" karena server mengirimkan file yang dihosting ke browser Anda, tetapi juga dapat mengirimkan file yang dihasilkan dari database.

## Server Side Programming
Server-side programming adalah proses menulis kode untuk membuat situs web dinamis. Server-side programming menggunakan bahasa pemrograman tertentu, seperti PHP, Python, Ruby, dan Javascript. Server-side programming memungkinkan Anda untuk membuat situs web yang dapat berinteraksi dengan pengguna, seperti mengirimkan email, mengirimkan pesan, dan mengirimkan data ke database.

## Static Site
Static site adalah situs web yang tidak memiliki server-side programming. Static site hanya berisi file HTML, CSS, dan Javascript. Static site tidak dapat berinteraksi dengan pengguna, seperti mengirimkan email, mengirimkan pesan, dan mengirimkan data ke database.

## Dynamic Site
Dynamic site adalah situs web yang memiliki server-side programming. Dynamic site dapat berinteraksi dengan pengguna, seperti mengirimkan email, mengirimkan pesan, dan mengirimkan data ke database.

## RESTful API
API RESTful adalah antarmuka yang digunakan oleh dua sistem komputer untuk bertukar informasi secara aman melalui internet. Sebagian besar aplikasi bisnis harus berkomunikasi dengan aplikasi internal dan pihak ketiga lainnya untuk melakukan berbagai tugas. Misalnya, untuk menghasilkan slip gaji bulanan, sistem akun internal Anda harus berbagi data dengan sistem perbankan pelanggan Anda untuk mengotomatiskan tagihan dan berkomunikasi dengan aplikasi absensi internal. API RESTful mendukung pertukaran informasi ini karena mengikuti standar komunikasi perangkat lunak yang aman, andal, dan efisien. Representational State Transfer (REST) adalah arsitektur perangkat lunak yang memberlakukan syarat mengenai cara API bekerja. REST pada awalnya dibuat sebagai panduan untuk mengelola komunikasi pada jaringan kompleks seperti internet. Anda dapat menggunakan arsitektur berbasis REST untuk mendukung komunkasi berperforma tinggi dan andal sesuai skala. Anda dapat dengan mudah menerapkan dan memodifikasinya, membawa visibilitas dan portabilitas lintas platform ke semua sistem API.

## Communication Between Client and Server
REST memungkinkan komunikasi antara client dan server. Client adalah aplikasi yang mengirim permintaan ke server. Server adalah aplikasi yang menerima permintaan dari client. Client dan server berkomunikasi dengan menggunakan HTTP. HTTP adalah protokol komunikasi yang digunakan untuk bertukar informasi di internet. HTTP adalah protokol yang aman, andal, dan efisien. HTTP memungkinkan komunikasi antara client dan server. Sebuah request biasanya terdiri dari 4 bagian, yaitu method, header, path, dan body. Method adalah tindakan yang ingin dilakukan oleh client. Header adalah informasi tambahan yang ingin dikirimkan oleh client. Path adalah lokasi yang ingin dikunjungi oleh client. Body adalah data yang ingin dikirimkan oleh client. Sebuah response biasanya terdiri dari 3 bagian, yaitu status code, header, dan body. Status code adalah kode yang menunjukkan status dari response. Header adalah informasi tambahan yang ingin dikirimkan oleh server. Body adalah data yang ingin dikirimkan oleh server.

# Intro and Essential Node.JS

## What is Node.js
Node.js adalah runtime environment untuk JavaScript yang bersifat open-source dan cross-platform. Dengan Node.js kita dapat menjalankan kode JavaScript di mana pun, tidak hanya terbatas pada lingkungan browser. Node.js menjalankan V8 JavaScript engine (yang juga merupakan inti dari Google Chrome) di luar browser. Ini memungkinkan Node.js memiliki performa yang tinggi. Node.js juga menyediakan banyak library/module JavaScript yang membantu menyederhanakan pengembangan aplikasi web.

## Node.js Architecture
### Single Thread
Node.js menggunakan satu thread untuk menjalankan kode JavaScript. Node.js menggunakan event loop untuk menjalankan kode JavaScript. Event loop memungkinkan Node.js untuk menjalankan kode JavaScript secara non-blocking. Non-blocking berarti kode JavaScript akan tetap berjalan meskipun ada kode JavaScript yang berjalan secara blocking. Blocking berarti kode JavaScript akan berhenti sampai kode JavaScript yang berjalan secara blocking selesai berjalan. Javascript menggunakan call stack untuk melakukan manajemen single thread. Ketika terdapat perintah baru maka akan ditambahkan (push) dan akan di keluarkan ketika perintahnya sudah selasai (pop)

### Event Loop
Dengan menggunakan konsep arsitektur javascript, walaupun menggunakan single thread tetapi kita dapat melihat javascript seperti menggunakan multi thread. Terdapat event queue yang berguna sebagai penampung ketika terdapat perintah baru yang akan dieksekusi. Event loop akan memfasilitasi kondisi ini, event loop akan memeriksa terus menerus, ketika antrian kosong di call stack maka akan menambah antrian baru dari event queue sampai semua perintah selesai di eksekusi.

### Server Side Scripting
Sejatinya javascript merupakan bahasa pemrograman yang digunakan di front end side. Sehingga kita hanya bisa mengerjakan javascript dengan menggunakan browser untuk menampilkan hasil eksekusinya. 
Tetapi dengan menggunakan NodeJS kita dapat menjalankan javascript di server side menggunakan terminal command line menggunakan perintah “node”.

## Javascript For Node.js
### Arrow Function
Arrow expression merupakan fitur terbaru dari javascript, yaitu mempermudah membuat sintaks function menggunakan “=>” 
```javascript
const add = (a, b) => a + b;
```

### Asynchronous
Asynchronous merupakan konsep yang paling penting dari javascript. Pada dasarnya, javascript mengeksekusi code secara single thread dan berurutan baris per baris yang disebut dengan synchronous. Sedangkan asynchronous memungkinkan mengeksekusi code tanpa berurutan dengan cara “skip” code dan melanjutkan eksekusi code selanjutnya. Konsep ini menungkinkan code kita tidak terjadi blocking dan lebih efisien.

### JSON
JSON atau Javascript Object Notation merupakan format yang digunakan untuk menyimpan dan mengirim data menggunakan konsep object di javascript. JSON dapat digunakan di hampir semua bahasa pemrograman sehingga sangat cocok untuk dipelajari
```javascript
const person = {
  name: "John",
  age: 30,
  city: "New York"
};
```
## Instalasi Node.js
Untuk menginstall Node.js, pertama-tama Download Node.js dari https://nodejs.org/en/download/. Kemudian install Node.js sesuai dengan sistem operasi yang digunakan. Setelah selesai menginstall Node.js, buka terminal/command prompt dan ketik perintah berikut untuk memastikan Node.js sudah terinstall dengan benar.
```bash
node -v
```

Jika berhasil, maka akan muncul versi Node.js yang terinstall. NodeJS ini juga dilengkapi dengan NPM (node package manager) dan dapat mengeceknya juga menggunakan “npm -v”

Untuk dapat menggunakan node di terminal kita dapat mengetikkan kata kunci "node" di terminal. Setelah itu kita dapat mengetikkan kode javascript yang akan dieksekusi. Untuk keluar dari node kita dapat mengetikkan “.exit” atau “ctrl + c”

## Build in Module Node.js
### Console
Console merupakan module yang digunakan untuk menampilkan output ke terminal/command prompt. Console memiliki beberapa method yang dapat digunakan untuk menampilkan output ke terminal/command prompt. Berikut adalah beberapa method yang dapat digunakan pada console.
```javascript
console.log("Hello World");
console.error("Error");
console.warn("Warning");
```
### Process
Process merupakan module yang digunakan untuk mengakses informasi dari proses yang sedang berjalan. Process memiliki beberapa method yang dapat digunakan untuk mengakses informasi dari proses yang sedang berjalan. Berikut adalah beberapa method yang dapat digunakan pada process.
```javascript
console.log(process.pid);
console.log(process.versions.node);
```
### OS
OS merupakan module yang digunakan untuk mengakses informasi dari sistem operasi yang digunakan. OS memiliki beberapa method yang dapat digunakan untuk mengakses informasi dari sistem operasi yang digunakan. Berikut adalah beberapa method yang dapat digunakan pada OS.
```javascript
console.log(os.platform());
console.log(os.homedir());
```
### Util
Util merupakan module yang digunakan untuk mengakses informasi dari utilitas yang digunakan. Util memiliki beberapa method yang dapat digunakan untuk mengakses informasi dari utilitas yang digunakan. Berikut adalah beberapa method yang dapat digunakan pada util.
```javascript
console.log(util.types.isDate(new Date()));
console.log(util.types.isRegExp(/foo/));
```
### Events
Events merupakan module yang digunakan untuk mengakses informasi dari event yang terjadi. Events memiliki beberapa method yang dapat digunakan untuk mengakses informasi dari event yang terjadi. Berikut adalah beberapa method yang dapat digunakan pada events.
```javascript
const EventEmitter = require('events');
class MyEmitter extends EventEmitter {}
const myEmitter = new MyEmitter();
myEmitter.on('event', () => {
  console.log('an event occurred!');
});
myEmitter.emit('event');
```
### Errors
Errors merupakan module yang digunakan untuk mengakses informasi dari error yang terjadi. Errors memiliki beberapa method yang dapat digunakan untuk mengakses informasi dari error yang terjadi. Berikut adalah beberapa method yang dapat digunakan pada errors.
```javascript
const err = new Error('invalid email');
console.log(err.message);
```
### Buffer
Buffer merupakan module yang digunakan untuk mengakses informasi dari buffer yang digunakan. Buffer memiliki beberapa method yang dapat digunakan untuk mengakses informasi dari buffer yang digunakan. Berikut adalah beberapa method yang dapat digunakan pada buffer.
```javascript
const buf = Buffer.from('Hello', 'utf8');
console.log(buf);
console.log(buf.toString());
console.log(buf.toJSON());
console.log(buf[2]);
buf.write('wo');
console.log(buf.toString());
```
### File System
File System merupakan module yang digunakan untuk mengakses informasi dari file yang digunakan. File System memiliki beberapa method yang dapat digunakan untuk mengakses informasi dari file yang digunakan. Berikut adalah beberapa method yang dapat digunakan pada file system.
```javascript
const fs = require('fs');
fs.readFile('./docs/blog1.txt', (err, data) => {
  if (err) {
    console.log(err);
  }
  console.log(data.toString());
});
console.log('last line');
```
### Timers
Timers merupakan module yang digunakan untuk mengakses informasi dari timer yang digunakan. Timers memiliki beberapa method yang dapat digunakan untuk mengakses informasi dari timer yang digunakan. Berikut adalah beberapa method yang dapat digunakan pada timers.
```javascript
import { setTimeout } from 'timers/promises';
const res = await setTimeout(1000, 'foo');
console.log(res);
```

## Web Server With Node JS
Untuk membuat web server kita dapat menggunakan built-in modul yang disebut HTTP, built-in modul ini dapat digunakan untuk membuat web server. Berikut adalah contoh kode untuk membuat web server menggunakan built-in modul HTTP.
```javascript
const http = require('http');
const server = http.createServer((req, res) => {
  if (req.url === '/') {
    res.end('Home Page');
  }
  if (req.url === '/about') {
    res.end('About Page');
  }
  res.end(`
    <h1>Oops!</h1>
    <p>We can't seem to find the page you're looking for.</p>
    <a href="/">back home</a>
  `);
});
server.listen(5000);
```

# Express.JS
## Apa itu Express.JS
Express.js adalah framework web app untuk Node.js yang ditulis dengan bahasa pemrograman JavaScript. Framework open source ini dibuat oleh TJ Holowaychuk pada tahun 2010 lalu.

Express.js adalah framework back end. Artinya, ia bertanggung jawab untuk mengatur fungsionalitas website, seperti pengelolaan routing dan session, permintaan HTTP, penanganan error, serta pertukaran data di server.

## Apa itu Back End
Back end app adalah aplikasi yang berjalan di server-side yang bekerja untuk memberikan informasi berupa data sesuai request dari client / browser / front end app. Umumnya server-side app membuat REST API

## Instalasi Express.JS
Untuk menginstall Express.JS kita dapat menggunakan perintah berikut.
```bash
npm install express
```
## Persiapan Project
Untuk mempersiapkan project kita dapat menggunakan perintah berikut.
```bash
mkdir express-app
cd express-app
npm init -y
npm install express
```
Kita juga harus mempersiapkan beberapa module tambahan yang akan digunakan pada project kita, contohnya adalah nodemon. Nodemon adalah module yang digunakan untuk memonitor perubahan pada file yang kita buat dan akan melakukan restart server ketika terjadi perubahan pada file yang kita buat. Untuk menginstall nodemon kita dapat menggunakan perintah berikut.
```bash
npm install nodemon
```
## Basic Route
Routes adalah sebuah end point yang diapat kita akses menggunakan URL di website. Didalam routes kita perlu menentukan method API, alamat dan response apa saja yang akan dikeluarkan. Kita bisa menjalankan aplikasi sederhana kita dengan cara menggunakan “node”. Dan aplikasi kita akan berjalan di alamat ‘http://localhost:3000'. Kemudian kita dapat mengaksesnya di website dan menambah route yang akan kita akses yaitu “/”

### Method
Method yang digunakan pada routes adalah method HTTP. Method HTTP adalah sebuah method yang digunakan untuk melakukan request ke server. Berikut adalah beberapa method yang sering digunakan pada routes : 
- GET : digunakan untuk mengambil data dari server.
- POST : digunakan untuk mengirim data ke server.
- PUT : digunakan untuk mengubah data yang ada di server.
- PATCH : digunakan untuk mengubah data yang ada di server.
- DELETE : digunakan untuk menghapus data yang ada di server.

### Response
Di dalam route kita dapat mengirim response menggunakan parameter dari route express.js yaitu “res.Send()” untuk mengirim plain text ketika kita mengakses route tersebut. Terdapat banyak response yang bisa kita buat selain yang dicontohkan. Kita dapat mengirim response berupa output json yang biasa dipakai untuk back end application. Dengan menggunakan output json maka kita dapat mengirim data yang mudah diakses 

### Status Code
Status code adalah kode yang digunakan untuk menandakan status dari sebuah request. Berikut adalah beberapa status code yang sering digunakan pada routes :
- 200 : OK
- 300 : Redirect
- 400 : Bad Request
- 500 : Internal Server Error

### Query
Query adalah sebuah parameter yang dikirimkan melalui URL. Query biasanya digunakan untuk melakukan filter pada data yang akan kita ambil. Untuk mengakses query kita dapat menggunakan parameter dari route express.js yaitu “req.query”. Berikut adalah contoh kode untuk mengakses query.
```javascript
app.get('/users', (req, res) => {
  const { name, age } = req.query;
  res.send(`Hello ${name}, your age is ${age}`);
});
```
## Middleware
Middleware adalah sebuah function yang dapat diakses pada route. Middleware dapat digunakan untuk melakukan validasi, menambahkan header, dan lain sebagainya. Berikut adalah contoh kode untuk membuat middleware.
```javascript
const validateUser = (req, res, next) => {
  if (!req.query.name) {
    res.send('Please provide a name');
  } else {
    next();
  }
};
app.get('/users', validateUser, (req, res) => {
  const { name, age } = req.query;
  res.send(`Hello ${name}, your age is ${age}`);
});
```

# Design Database with MySQL
## Apa itu Database
Database adalah sebuah kumpulan data yang disimpan secara terstruktur. Database biasanya digunakan untuk menyimpan data yang akan digunakan pada aplikasi. Database juga dapat digunakan untuk menyimpan data yang akan digunakan pada website. Database dapat digunakan untuk menyimpan data yang bersifat transaksional, data yang bersifat master, dan data yang bersifat history.

## Apa itu MySQL
MySQL adalah sebuah database management system (manajemen basis data) menggunakan perintah dasar SQL (Structured Query Language) yang cukup terkenal. Database management system (DBMS) MySQL multi pengguna dan multi alur ini sudah dipakai lebih dari 6 juta pengguna di seluruh dunia.

## Entity Relationship Diagram
Entity Relationship Diagram (ERD) adalah sebuah diagram yang digunakan untuk menggambarkan hubungan antar entitas. ERD digunakan untuk memvisualisasikan data yang akan disimpan pada database. ERD juga dapat digunakan untuk memvisualisasikan data yang akan ditampilkan pada website. ERD dapat digunakan untuk memvisualisasikan data yang akan disimpan pada database. ERD juga dapat digunakan untuk memvisualisasikan data yang akan ditampilkan pada website.

## Entity
Entity adalah sebuah objek yang akan disimpan pada database. Entity juga dapat disebut sebagai sebuah tabel pada database.

## Attribute
Attribute adalah sebuah data yang akan disimpan pada database. Attribute juga dapat disebut sebagai sebuah kolom pada database.

## Relationship
Relationship adalah sebuah hubungan antar entitas. Relationship juga dapat disebut sebagai sebuah relasi antar tabel pada database.
Relationship dapat dibagi menjadi 3 yaitu :
- One to One
- One to Many
- Many to Many