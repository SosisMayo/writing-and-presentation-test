# Asynchronous Javascript

## **Async - Await**
Async adalah sebuah syntax dalam javascript yang menjadikan sebuah fungsi yang kita buat mengembalikan sebuah promise. contohnya :
 ```javascript
    async function getData() {
        return 1;
    }
    getData().then(console.log); // 1
```
Kita bisa melihat bahwa fungsi getData mengembalikan sebuah promise yang mengembalikan nilai 1. Nilai 1 dianggap sebagai nilai resolve, kita juga bisa menulisnya dengan lebih jelas sebagai berikut :
```javascript
    async function getData() {
        return Promise.resolve(1);
    }
    getData().then(console.log); // 1
```
Await adalah sebuah syntax yang digunakan untuk menunggu sebuah promise selesai dijalankan. contohnya :
```javascript
    async function getData() {
        return 1;
    }
    async function main() {
        const data = await getData();
        console.log(data);
    }
    main(); // 1
```

## Fetch
Fetch adalah sebuah Native Web API yang digunakan untuk melakukan HTTP calls dari externall network. contohnya :
```javascript
    fetch('https://jsonplaceholder.typicode.com/todos/1')
        .then(response => response.json())
        .then(json => console.log(json));
```
fetch() memiliki parameter utama yaitu URL/endpoint API, dan parameter kedua yaitu options, options ini berisi method, headers dan body. contohnya :
```javascript
    fetch('https://jsonplaceholder.typicode.com/todos/1', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({
            title: 'foo',
            body: 'bar',
            userId: 1
        })
    })
        .then(response => response.json())
        .then(json => console.log(json));
```
Kita juga bisa menggabungkannya dengan async await, contohnya :
```javascript
    async function getData() {
        const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
        const json = await response.json();
        console.log(json);
    }
    getData();
```
# Git dan Github Lanjutan

## **Git Branch**
Branch adalah sebuah fitur yang ada di git yang digunakan untuk membuat sebuah timeline yang berbeda dari timeline utama. Branch ini berguna untuk mengembangkan sebuah fitur tanpa harus mengganggu timeline utama. Untuk membuat branch baru kita dapat menggunakan command branch diikuti nama branchnya. contohnya :
```bash
    git branch fitur-1
```
Untuk melihat branch yang ada kita dapat menggunakan command branch tanpa parameter. contohnya :
```bash
    git branch
```
Untuk berpindah branch kita dapat menggunakan command checkout diikuti nama branch yang ingin kita pindah. contohnya :
```bash
    git checkout fitur-1
```
Untuk menggabungkan branch kita dapat menggunakan command merge diikuti nama branch yang ingin kita gabungkan. contohnya :
```bash
    git merge fitur-1
```
Untuk menghapus branch kita dapat menggunakan command branch diikuti parameter -d diikuti nama branch yang ingin kita hapus. contohnya :
```bash
    git branch -d fitur-1
```
## **Git Remote**
Remote adalah sebuah fitur yang ada di git yang digunakan untuk menghubungkan git kita dengan git lainnya. Untuk menambahkan remote kita dapat menggunakan command remote diikuti parameter add diikuti nama remote dan url remote. contohnya :
```bash
    git remote add origin https://github.com/SosisMayo/writing-and-presentation-test.git
```
Untuk melihat remote yang ada kita dapat menggunakan command remote tanpa parameter. contohnya :
```bash
    git remote
```
Untuk menghapus remote kita dapat menggunakan command remote diikuti parameter remove diikuti nama remote. contohnya :
```bash
    git remote remove origin
```
Untuk mengubah remote kita dapat menggunakan command remote diikuti parameter set-url diikuti nama remote dan url remote. contohnya :
```bash
    git remote set-url origin https://github.com/SosisMayo/writing-and-presentation-test.git
```
## **Git Pull**
Pull adalah sebuah fitur yang ada di git yang digunakan untuk mengambil perubahan dari remote ke local. Untuk melakukan pull kita dapat menggunakan command pull diikuti nama remote dan nama branch. contohnya :
```bash
    git pull origin master
```
## **Git Push**
Push adalah sebuah fitur yang ada di git yang digunakan untuk mengirim perubahan dari local ke remote. Untuk melakukan push kita dapat menggunakan command push diikuti nama remote dan nama branch. contohnya :
```bash
    git push origin master
```
## **Git Clone**
Clone adalah sebuah fitur yang ada di git yang digunakan untuk mengambil sebuah repository dari remote ke local. Untuk melakukan clone kita dapat menggunakan command clone diikuti url repository. contohnya :
```bash
    git clone https://github.com/SosisMayo/writing-and-presentation-test.git
```
## **Git Stash**
Stash adalah sebuah fitur yang ada di git yang digunakan untuk menyimpan perubahan yang belum di commit. Untuk melakukan stash kita dapat menggunakan command stash. contohnya :
```bash
    git stash
```
Untuk melihat stash kita dapat menggunakan command stash diikuti parameter list. contohnya :
```bash
    git stash list
```
Untuk menghapus stash kita dapat menggunakan command stash diikuti parameter drop diikuti nama stash. contohnya :
```bash
    git stash drop stash@{0}
```
Untuk mengembalikan stash kita dapat menggunakan command stash diikuti parameter apply diikuti nama stash. contohnya :
```bash
    git stash apply stash@{0}
```
## **Git Reset**
Reset adalah sebuah fitur yang ada di git yang digunakan untuk mengembalikan perubahan yang sudah di commit. Untuk melakukan reset kita dapat menggunakan command reset diikuti parameter hard diikuti nama commit. contohnya :
```bash
    git reset --hard 1a2b3c4d5e6f7g8h9i0j
```
Untuk melihat commit kita dapat menggunakan command log. contohnya :
```bash
    git log
```

# Responsive Web Design
Responsive Web Design adalah sebuah teknik yang digunakan untuk membuat sebuah website yang dapat menyesuaikan dengan ukuran layar yang digunakan. Kita dapat melihat apakah website kita responsive atau tidak dengan menggunakan developer tools pada browser. contohnya :

![Responsive Web Design](responsive.jpg)

atau dengan menekan kombinasi tombol Ctrl + Shift + M pada keyboard.
Untuk menerapkan responsive web design pada website kita, pertama-tama kita harus menambahkan viewport pada tag head. contohnya :
```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Lalu kita dapat mengatur resposivitas dari suatu elemen dengan menggunakan property max-width dan min-width. contohnya :
```css
    .container {
        max-width: 100%;
        min-width: 300px;
    }
```
Kita juga dapat mengatur resposivitas dari suatu elemen dengan menggunakan property media query. penerapan media query juga dibagi menjadi 2, yaitu dengan menggunakan file css yang berbeda untuk setiap media query, dan dengan menggunakan media query pada file css yang sama. contohnya :
```html
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" media="screen and (max-width: 600px)" href="style-mobile.css">
```
```css
    /* file css yang berbeda */
    @media screen and (max-width: 600px) {
        .container {
            max-width: 300px;
        }
    }
```
```css
    /* file css yang sama */
    .container {
        max-width: 100%;
    }
    @media screen and (max-width: 600px) {
        .container {
            max-width: 300px;
        }
    }
```

## **Breakpoints**
Breakpoints adalah ukuran layar yang digunakan untuk menentukan resposivitas dari suatu elemen. contohnya :
```css
    @media screen and (max-width: 600px) {
        .container {
            max-width: 300px;
        }
    }
    @media screen and (min-width: 601px) and (max-width: 900px) {
        .container {
            max-width: 600px;
        }
    }
    @media screen and (min-width: 901px) {
        .container {
            max-width: 900px;
        }
    }
```
dari CSS tersebut kita dapat melihat bahwa elemen dengan class container akan memiliki max-width 300px jika ukuran layar kurang dari 600px, max-width 600px jika ukuran layar lebih dari 600px dan kurang dari 900px, dan max-width 900px jika ukuran layar lebih dari 900px. Artinya kita memiliki 3 breakpoints, yaitu dibawah 600px, antara 600px dan 900px, dan diatas 900px.

# **Bootstrap**
Bootstrap adalah sebuah framework CSS yang digunakan untuk mempermudah kita dalam membuat website yang responsive. Bootstrap dapat kita gunakan ketika kita menginginkan untuk membuat tampilan website dengan cepat tanpa harus terlalu banyak mengatur styling pada CSS. Hal tersebut karena Bootstrap telah menyediakan berbagai macam styling yang dapat kita gunakan hanya dengan menambahkannya pada kelas dari element yang kita miliki. Untuk menggunakan bootstrap, pertama-tama kita harus menambahkan link bootstrap pada tag head. contohnya :
```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">
```
Kita juga dapat menggunakan bootstrap dengan menggunakan menambahkannya secara lokal. contohnya :
```html
    <link rel="stylesheet" href="css/bootstrap.min.css">
```

## **Layouting**
Pada dasarnya, layouting dalam Bootstrap dapat diaplikasikan dengan menggunakan grid system. Grid system adalah sebuah sistem yang digunakan untuk mengatur posisi elemen pada website. Grid system pada Bootstrap dibuat dari CSS Flexbox.  Grid system ini terdiri dari 12 kolom, dan kita dapat mengatur posisi elemen dengan menggunakan class-class yang sudah disediakan oleh bootstrap. contohnya :
```html
    <div class="container">
        <div class="row">
            <div class="col-12 col-md-6 col-lg-4">
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title
                        ">Card title</h5>
                        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                        <a href="#" class="btn btn-primary">Go somewhere</a>
                    </div>
                </div>
            </div>
            <div class="col-12 col-md-6 col-lg-4">
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title
                        ">Card title</h5>
                        <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                        <a href="#" class="btn btn-primary">Go somewhere</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
```
dari kode tersebut kita dapat melihat bahwa elemen dengan class card akan memiliki sebesar 12 kolom jika ukuran layar kurang dari 576px, 6 kolom jika ukuran layar lebih dari 576px dan kurang dari 768px, dan 4 kolom jika ukuran layar lebih dari 768px. Artinya kita memiliki 3 breakpoints, yaitu dibawah 576px, antara 576px dan 768px, dan diatas 768px.

## **Contents**
Bootstrap juga terdiri dari berbagai macam file. Beberapa file diantaranya adalah :
- CSS
  - Bootstrap CSS\
  Di dalamnya terdapat Layout, Content, Component, dan Utilities
  - Bootstrap Grid CSS\
  Di dalamnya hanya terdapat layout berupa grid system dan utilities berupa flex
  - Bootstrap Utilities CSS\
  Di dalamnya terdapat utilities saja
  - Bootstrap Reboot CSS\
  Di dalamnya hanya terdapat reboot, yaitu styling yang digunakan untuk mengatur ulang styling yang sudah ada pada browser, contohnya font, list, form, table, dan lain-lain.
- JS
  - Bootstrap Bundle JS
  Di dalamnya sudah terdapat popper.js
  - Bootstrap JS
  Di dalamnya belum terdapat popper.js

## **Components**
Bootstrap juga menyediakan beberapa komponen yang dapat kita gunakan untuk mempermudah kita dalam membuat website. Untuk menggunakannya kita cukup menambahkan class pada element html yang kita miliki. contohnya :
```html
    <button type="button" class="btn btn-primary">Primary</button>
    <button type="button" class="btn btn-secondary">Secondary</button>
    <button type="button" class="btn btn-success">Success</button>
    <button type="button" class="btn btn-danger">Danger</button>
    <button type="button" class="btn btn-warning">Warning</button>
    <button type="button" class="btn btn-info">Info</button>
    <button type="button" class="btn btn-light">Light</button>
    <button type="button" class="btn btn-dark">Dark</button>
    <button type="button" class="btn btn-link">Link</button>
```
dengan begitu maka kita akan mendapatkan button dengan warna yang berbeda-beda. Begitu juga dengan elemen yang lain.
## **Responsive**
Bootstrap juga mendukung responsive web design dengan menyediakan memerapa breakpoint, diantaranya :
- Extra Small : untuk ukuran layar dibawah 576px
- Small (sm) : untuk ukuran layar antara 576px dan 767px
- Medium (md) : untuk ukuran layar antara 768px dan 991px
- Large (lg) : untuk ukuran layar antara 992px dan 1199px
- Extra Large (xl) : untuk ukuran layar antara 1200px dan 1399px
- dan Extra Extra Large (xxl) : untuk ukuran layar diatas 1400px keatas
