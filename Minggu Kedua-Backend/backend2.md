# Database MySQL  Basic
## Database
Database atau basis data adalah kumpulan data yang dikelola sedemikian rupa berdasarkan ketentuan tertentu yang saling berhubungan sehingga mudah dalam pengelolaannya. Melalui pengelolaan tersebut pengguna dapat memperoleh kemudahan dalam mencari informasi, menyimpan informasi dan membuang informasi. Setiap database dikontrol oleh sebuah Database Management System (DBMS)
## DBMS
database management system atau biasa disingkat DBMS adalah sistem software yang digunakan untuk menyimpan, mengatur, dan memastikan data-data tersebut tersimpan dengan aman. Dengan DBMS, user bisa membuat, membaca, memperbarui, dan menghapus data yang ada di database. Intinya, DBMS ini berperan sebagai interface antara database dan end-user atau program aplikasi.
## MySQL
MySQL adalah sistem manajemen database relasional (RDBMS) open-source berbasis SQL yang bekerja dengan model client-server. Kegunaan atau fungsi MySQL adalah untuk data warehousing (gudang data), yaitu pengumpulan data dari berbagai sumber, untuk e-commerce, maupun aplikasi logging.
## Instalasi MySQL
### Windows
1. Download MySQL Installer dari https://dev.mysql.com/downloads/installer/
2. Install MySQL Installer

### MacOS
1. Download MySQL Community Server dari https://dev.mysql.com/downloads/mysql/
2. Install MySQL Community Server

atau dapat menggunakan Homebrew
```
brew install mysql
```

### Linux
```sh
sudo apt-get install mysql-server
mysql -u root -p
```

## Tipe Data SQL
### Tipe Data Numeric
Tipe data ini digunakan untuk menyimpan data angka. Tipe data ini terbagi menjadi 3 yaitu :
1. Integer
   merupakan tipe data yang digunakan untuk menyimpan data angka yang tidak memiliki koma
2. Float
   merupakan tipe data yang digunakan untuk menyimpan data angka yang memiliki koma
3. Decimal
   merupakan tipe data yang digunakan untuk menyimpan data angka yang memiliki koma dengan presisi yang telah ditentukan sebelumnya

### Tipe Data String
Tipe data ini digunakan untuk menyimpan data teks. Tipe data ini terbagi menjadi 4 yaitu :
1. Char
   merupakan tipe data yang digunakan untuk menyimpan data teks dengan jumlah karakter yang telah ditentukan sebelumnya
2. Varchar
   merupakan tipe data yang digunakan untuk menyimpan data teks dengan jumlah karakter yang lebih fleksibel, maksimal 255 karakter
3. Text
   merupakan tipe data yang digunakan untuk menyimpan data teks dengan jumlah karakter yang lebih panjang
4. Enum
   merupakan tipe data yang digunakan untuk menyimpan data teks dengan jumlah karakter yang telah ditentukan sebelumnya, nilai yang dapat disimpan hanya satu dari beberapa nilai yang telah ditentukan sebelumnya

### Tipe Data Boolean
Tipe data ini digunakan untuk menyimpan data boolean. Data boolean hanya memiliki 2 nilai yaitu true atau false.

### Tipe Data Date
Tipe data ini digunakan untuk menyimpan data tanggal. Tipe data ini terbagi menjadi 4 yaitu :
1. Date
   merupakan tipe data yang digunakan untuk menyimpan data tanggal
2. Time
   merupakan tipe data yang digunakan untuk menyimpan data waktu
3. Datetime
   merupakan tipe data yang digunakan untuk menyimpan data tanggal dan waktu
4. Timestamp
   merupakan tipe data yang digunakan untuk menyimpan data tanggal dan waktu beserta dengan timezonenya

### Tipe Data Lainnya
1. Default
   merupakan tipe data yang digunakan untuk menyimpan data yang tidak memiliki tipe data
2. Null
   merupakan tipe data yang digunakan untuk menyimpan data yang tidak memiliki nilai

## Key
### Primary Key
Primary key adalah sebuah kolom atau gabungan kolom yang dapat mengidentifikasi setiap baris pada sebuah tabel. Primary key harus memiliki nilai yang unik dan tidak boleh bernilai NULL. Primary key juga dapat digunakan sebagai foreign key pada tabel lainnya.

### Foreign Key
Foreign key adalah sebuah kolom atau gabungan kolom yang merupakan primary key dari tabel lain. Foreign key dapat memiliki nilai NULL. Foreign key digunakan untuk menghubungkan antara tabel dengan tabel lainnya.

## SQL Command
### Database Command
1. CREATE DATABASE\
   digunakan untuk membuat database baru
   ```sql
    CREATE DATABASE <nama_database>;
    ```
2. DROP DATABASE\
   digunakan untuk menghapus database
    ```sql
     DROP DATABASE <nama_database>;
     ```
3. USE\
    digunakan untuk memilih database yang akan digunakan
     ```sql
      USE <nama_database>;
      ```
4. SHOW DATABASES\
    digunakan untuk menampilkan database yang ada
     ```sql
      SHOW DATABASES;
      ```

### Table Command
1. CREATE TABLE\
   digunakan untuk membuat tabel baru
   ```sql
    CREATE TABLE <nama_tabel> (
        <nama_kolom> <tipe_data> <constraint>,
        <nama_kolom> <tipe_data> <constraint>,
        ...
    );
    ```
2. DROP TABLE\
    digunakan untuk menghapus tabel
     ```sql
      DROP TABLE <nama_tabel>;
      ```
3. SHOW TABLES\
    digunakan untuk menampilkan tabel yang ada
     ```sql
      SHOW TABLES;
      ```
4. ALTER TABLE\
    digunakan untuk mengubah tabel
     ```sql
      ALTER TABLE <nama_tabel> <aksi>;
      ```
5. ADD\
    digunakan untuk menambah kolom pada tabel
     ```sql
      ALTER TABLE <nama_tabel> ADD <nama_kolom> <tipe_data> <constraint>;
      ```
6. DROP\
    digunakan untuk menghapus kolom pada tabel
     ```sql
      ALTER TABLE <nama_tabel> DROP <nama_kolom>;
      ```

### Data Command
1. INSERT\
    digunakan untuk menambah data pada tabel
     ```sql
      INSERT INTO <nama_tabel> VALUES (<nilai_kolom_1>, <nilai_kolom_2>, ...);
      ```
2. UPDATE\
    digunakan untuk mengubah data pada tabel
     ```sql
      UPDATE <nama_tabel> SET <nama_kolom> = <nilai_kolom> WHERE <kondisi>;
      ```
3. SELECT\
    digunakan untuk menampilkan data pada tabel
     ```sql
      SELECT <nama_kolom> FROM <nama_tabel> WHERE <kondisi>;
      ```
4. SELECT ALIAS\
    digunakan untuk menampilkan data pada tabel dengan alias
     ```sql
      SELECT <nama_kolom> AS <alias> FROM <nama_tabel> WHERE <kondisi>;
      ```
5. WHERE\
    digunakan untuk menampilkan data pada tabel dengan kondisi
     ```sql
      SELECT <nama_kolom> FROM <nama_tabel> WHERE <kondisi>;
      ```
    jika parameter kondisi lebih dari satu, maka gunakan operator IN, AND, OR, NOT
     ```sql
      SELECT <nama_kolom> FROM <nama_tabel> WHERE <kondisi_1> AND <kondisi_2>;
      ```
6. ORDER BY\
    digunakan untuk menampilkan data pada tabel dengan urutan tertentu
     ```sql
      SELECT <nama_kolom> FROM <nama_tabel> ORDER BY <nama_kolom> ASC/DESC;
      ```
7. GROUP BY\
    digunakan untuk menampilkan data pada tabel dengan mengelompokkan data
     ```sql
      SELECT <nama_kolom> FROM <nama_tabel> GROUP BY <nama_kolom>;
      ```
8. LIMIT\
    digunakan untuk menampilkan data pada tabel dengan batasan jumlah data
     ```sql
      SELECT <nama_kolom> FROM <nama_tabel> LIMIT <jumlah_data>;
      ```
9. UPDATE\
    digunakan untuk mengubah data pada tabel
     ```sql
      UPDATE <nama_tabel> SET <nama_kolom> = <nilai_kolom> WHERE <kondisi>;
      ```
10. DELETE\
    digunakan untuk menghapus data pada tabel
     ```sql
      DELETE FROM <nama_tabel> WHERE <kondisi>;
      ```

# Database MySQL Lanjutan
## Relasi
Relasi adalah hubungan antara dua buah tabel. Relasi dapat berupa relasi 1:1, 1:N, N:N.
1. Relasi 1:1\
   Relasi 1:1 adalah relasi antara dua buah tabel yang memiliki hubungan 1 baris pada tabel A hanya memiliki 1 baris pada tabel B dan 1 baris pada tabel B hanya memiliki 1 baris pada tabel A.
2. Relasi 1:N\
    Relasi 1:N adalah relasi antara dua buah tabel yang memiliki hubungan 1 baris pada tabel A hanya memiliki N baris pada tabel B dan N baris pada tabel B hanya memiliki 1 baris pada tabel A.
3. Relasi N:N\
    Relasi N:N adalah relasi antara dua buah tabel yang memiliki hubungan N baris pada tabel A hanya memiliki N baris pada tabel B dan N baris pada tabel B hanya memiliki N baris pada tabel A.

## Database Normalization
### Pengertian
Database normalization adalah proses untuk memperbaiki struktur database yang tidak efisien. Proses ini dilakukan dengan membagi tabel menjadi beberapa tabel yang lebih kecil.
### Tujuan
Proses ini dilakukan untuk menghindari duplikasi data dan memperbaiki struktur database yang tidak efisien.
### Efek Jika Tidak Dilakukan
1. Insert Anomaly\
    Situasi dimana tidak memungkinkan memasukkan beberapa jenis data secara langsung di database.
2. Delete Anomaly\
    Penghapusan data yang tidak sesuai dengan yang diharapkan, artinya data yang harusnya tidak terhapus mungkin ikut terhapus.
3. Update Anomaly\
    Situasi dimana nilai yang diubah menyebabkan inkonsistensi database, dalam artian data yang diubah tidak sesuai dengan yang diperintahkan atau yang diinginkan.
### Bentuk Normalisasi
1. 1NF\
    Menghilangkan multiple value pada sebuah kolom tabel database. Multiple value adalah data yang terdapat pada kolom tabel yang memiliki lebih dari satu nilai.
2. 2NF\
    Menghilangkan partial dependency pada tabel database dan menempatkannya pada tabel terpisah. Partial dependency adalah data yang terdapat pada tabel yang memiliki ketergantungan terhadap kolom lain.
3. 3NF\
    Menghilangkan seluruh atribut atau field yang tidak berhubungan dengan primary key. Dengan demikian tidak ada ketergantungan transitif pada setiap kandidat key.

## Keys di SQL
### Super Key
Super key adalah kumpulan dari satu atau lebih kolom yang dapat mengidentifikasi setiap baris pada tabel. Super key dapat berupa primary key, foreign key, atau candidate key.
### Candidate Key
Candidate key adalah kumpulan dari satu atau lebih kolom yang dapat mengidentifikasi setiap baris pada tabel. Candidate key tidak boleh memiliki nilai NULL dan tidak boleh memiliki duplikat. Setiap candidate key harus dapat digunakan sebagai primary key.
### Primary Key
Primary key adalah kumpulan dari satu atau lebih kolom yang dapat mengidentifikasi setiap baris pada tabel. Primary key tidak boleh memiliki nilai NULL dan tidak boleh memiliki duplikat. Setiap tabel hanya boleh memiliki satu primary key.
### Alternate Key
Alternate key adalah kumpulan dari satu atau lebih kolom yang dapat mengidentifikasi setiap baris pada tabel. Alternate key adalah candidate key yang bukan primary key.
### Unique Key
Unique key adalah kumpulan dari satu atau lebih kolom yang dapat mengidentifikasi setiap baris pada tabel. Berbeda dengan primary key, unique key boleh memiliki nilai NULL.
### Foreign Key
Foreign key adalah kumpulan dari satu atau lebih kolom yang dapat mengidentifikasi setiap baris pada tabel. Foreign key adalah primary key dari tabel lain.

## Join
Join adalah proses penggabungan data dari dua buah tabel. Join dapat berupa inner join, left join, dan right join.

### Inner Join
Semua baris yang memiliki nilai yang cocok dengan kondisi yang ditentukan akan diambil. Penentuan kondisi dapat dilakukan dengan menggunakan keyword ON.
```sql
SELECT <nama_kolom>
FROM <nama_tabel_1>
INNER JOIN <nama_tabel_2>
ON <nama_tabel_1>.<nama_kolom> = <nama_tabel_2>.<nama_kolom>;
```

### Left Join
Semua baris pada tabel pertama akan diambil, dan baris yang tidak memiliki record yang cocok dengan baris pada tabel kedua akan diisi null. Penentuan kondisi dapat dilakukan dengan menggunakan keyword ON.
```sql
SELECT <nama_kolom>
FROM <nama_tabel_1>
LEFT JOIN <nama_tabel_2>
ON <nama_tabel_1>.<nama_kolom> = <nama_tabel_2>.<nama_kolom>;
```

### Right Join
Semua baris pada tabel kedua akan diambil, dan baris yang tidak memiliki record yang cocok dengan baris pada tabel pertama akan diisi null. Penentuan kondisi dapat dilakukan dengan menggunakan keyword ON.
```sql
SELECT <nama_kolom>
FROM <nama_tabel_1>
RIGHT JOIN <nama_tabel_2>
ON <nama_tabel_1>.<nama_kolom> = <nama_tabel_2>.<nama_kolom>;
```

## Aggregate Function
1. Max\
   mengembalikan nilai maksimum dari kolom yang ditentukan.
2. Min\
   mengembalikan nilai minimum dari kolom yang ditentukan.
3. Sum\
   mengembalikan jumlah dari kolom yang ditentukan.
4. Count\
   mengembalikan jumlah baris yang tidak kosong dari kolom yang ditentukan.
5. Avg\
   mengembalikan rata-rata dari kolom yang ditentukan.

## Union
Union adalah proses penggabungan data dari dua buah tabel. Jumlah kolom pada kedua tabel harus sama. 
```sql
SELECT <nama_kolom>
FROM <nama_tabel_1>
UNION
SELECT <nama_kolom>
FROM <nama_tabel_2>;
```

## Group By
Group by adalah proses pengelompokan data berdasarkan kolom yang ditentukan. Group by dapat digunakan untuk mengelompokan data berdasarkan kategori, dan menghitung jumlah data pada setiap kategori.
```sql
SELECT <nama_kolom>, COUNT(<nama_kolom>)
FROM <nama_tabel>
GROUP BY <nama_kolom>;
```

## Having
Having digunakan layaknya where, namun having dapat digunakan bersamaan dengan aggregate function. Having dapat digunakan untuk memfilter data yang telah di-group by.
```sql
SELECT <nama_kolom>, COUNT(<nama_kolom>)
FROM <nama_tabel>
GROUP BY <nama_kolom>
HAVING COUNT(<nama_kolom>) > 1;
```

## Like
Like digunakan untuk mencari data yang memiliki pola tertentu. Like dapat digunakan untuk mencari data yang dimulai dengan suatu karakter, atau data yang diakhiri dengan suatu karakter, atau data yang berisi suatu karakter. Karakter Wildcard yang digunakan adalah % (persen) dan _ (underscore). % mewakili nol atau lebih karakter, sedangkan _ mewakili satu karakter.
```sql
SELECT <nama_kolom>
FROM <nama_tabel>
WHERE <nama_kolom> LIKE 'a%';
```

# Authentication & Authorization
## Authentication
Authentication adalah proses verifikasi identitas pengguna. Authentication dilakukan dengan membandingkan data yang dimasukkan pengguna dengan data yang tersimpan di database. Authentication dapat dilakukan dengan menggunakan username dan password, atau dengan menggunakan email dan password.

Authentication dapat dilakukan melalui beberapa faktor, yaitu:
1. Knowledge Factor\
   Authentication dilakukan melalui data yang diketahui, seperti username dan password.
2. Possesion\
   Authentication dilakukan melalui data yang dimiliki, seperti handphone.
3. Inherence\
   Authentication dilakukan melalui data bawaan (merujuk pada biometrik), seperti sidik jari.

## Authorization
Authorization adalah proses verifikasi hak akses pengguna. Authorization dilakukan dengan membandingkan hak akses yang dimiliki pengguna dengan hak akses yang dibutuhkan untuk mengakses suatu data. Authorization dapat dilakukan dengan menggunakan role, atau dengan menggunakan permission.

## Encryption
Encryption adalah proses pengubahan data menjadi bentuk yang tidak dapat dibaca. Encryption dilakukan dengan menggunakan algoritma kriptografi. Encryption dapat dilakukan dengan menggunakan algoritma simetris, atau dengan menggunakan algoritma asymetris.

## Session, Cookie, dan Local Storage
Session, cookie, dan local storage adalah teknologi penyimpanan data di browser. Session dan cookie menyimpan data di browser sementara, sedangkan local storage menyimpan data di browser secara permanen.

## JWT
JWT adalah singkatan dari JSON Web Token. JWT adalah sebuah token yang digunakan untuk melakukan authentication dan authorization. JWT terdiri dari 3 bagian, yaitu header, payload, dan signature. Header berisi informasi mengenai algoritma yang digunakan untuk membuat signature. Payload berisi informasi mengenai data yang akan disimpan di JWT. Signature berisi hasil enkripsi dari header, payload, dan secret key.

### JWT Implementation
Untuk menerapkan JWT pada aplikasi, langkah-langkah yang harus dilakukan adalah:
1. Install library jsonwebtoken
   ```bash
    npm install jsonwebtoken
    ```
2. Membuat secret key
    ```javascript
     const secretKey = 'secretKey';
     ```

3. Membuat fungsi untuk membuat JWT
    ```javascript
    const jwt = require('jsonwebtoken');

    const createToken = (payload) => {
        return jwt.sign(payload, secretKey);
    }
    ```
Untuk mengautentikasi pengguna, langkah-langkah yang harus dilakukan adalah:
1. Membuat fungsi untuk mengautentikasi pengguna
    ```javascript
    const jwt = require('jsonwebtoken');

    const authenticate = (req, res, next) => {
        const token = req.headers.authorization;
        if (token) {
            jwt.verify(token, secretKey, (err, decoded) => {
                if (err) {
                    res.status(401).json({
                        message: 'Invalid token'
                    });
                } else {
                    req.decoded = decoded;
                    next();
                }
            });
        } else {
            res.status(401).json({
                message: 'Token not found'
            });
        }
    }
    ```
2. Menerapkan fungsi authenticate pada route yang akan di-protect
    ```javascript
    const { authenticate } = require('../middlewares/auth');
    app.get('/protected', authenticate, (req, res) => {
        res.status(200).json({
            message: 'Protected route'
        });
    });
    ```
Untuk mengautorisasi pengguna, langkah-langkah yang harus dilakukan adalah:
1. Membuat fungsi untuk mengautorisasi pengguna
    ```javascript
    const jwt = require('jsonwebtoken');

    const authorize = (req, res, next) => {
        const token = req.headers.authorization;
        if (token) {
            jwt.verify(token, secretKey, (err, decoded) => {
                if (err) {
                    res.status(401).json({
                        message: 'Invalid token'
                    });
                } else {
                    if (decoded.role === 'admin') {
                        next();
                    } else {
                        res.status(403).json({
                            message: 'Forbidden'
                        });
                    }
                }
            });
        } else {
            res.status(401).json({
                message: 'Token not found'
            });
        }
    }
    ```
## Bcrypt
Bcrypt adalah library yang digunakan untuk melakukan hashing pada password. Bcrypt dapat digunakan untuk melakukan hashing pada password sebelum disimpan di database, dan untuk melakukan pengecekan password yang dimasukkan pengguna dengan password yang tersimpan di database.

# Sequelize
## Pengertian
Sequelize adalah ORM (Object Relational Mapping) Node JS yang berbasis promise. Sequelize mendukung sebagian besar relational Database seperti MySQL, PostgresQL, MariaDB, SQLite dan Miscrosoft SQL Server.

Dengan fitur fitur di Sequelize, kita bisa mengelola dan mengatur data di database kita dengan cepat, dan efisien.

## ORM
ORM adalah suatu metode/teknik pemrograman yang digunakan untuk mengkonversi data dari lingkungan bahasa pemrograman berorientasi objek (OOP) dengan lingkungan database relational.

## Instalasi
1. Install sequelize-cli
    ```bash
    npm install -g sequelize-cli
    ```
2. Install sequelize
    ```bash
    npm install --save sequelize
    ```
3. Install driver database yang akan digunakan
    ```bash
    npm install --save mysql
    ```

## Inisialisasi Project
Inisialisasi dapat dilakukan dengan cara berikut:
```bash
npx sequelize-cli init
```

## Setting Database
Setting database dapat dilakukan dengan cara berikut:
```javascript
const Sequelize = require('sequelize');
const sequelize = new Sequelize('database', 'username', 'password', {
    host: 'localhost',
    dialect: 'mysql'
});
```

## Generate Model 
Untuk membuat model dapat dilakukan dengan cara berikut:
```bash
npx sequelize-cli model:generate --name User --attributes firstName:string,lastName:string,email:string
```
Untuk membuat tabelnya, lakukan migrasi dengan cara berikut:
```bash
npx sequelize-cli db:migrate
```
Jika ingin menghapus tabelnya, lakukan migrasi dengan cara berikut:
```bash
npx sequelize-cli db:migrate:undo
```

## Generate Seeder
Untuk membuat seeder dapat dilakukan dengan cara berikut:
```bash
npx sequelize-cli seed:generate --name demo-user
```
Untuk menjalankan seeder dapat dilakukan dengan cara berikut:
```bash
npx sequelize-cli db:seed:all
```
Untuk menghapus seeder dapat dilakukan dengan cara berikut:
```bash
npx sequelize-cli db:seed:undo
```

## Implementasi CRUD Menggunakan Sequelize
### Create
```javascript
const { User } = require('../models');
const bcrypt = require('bcrypt');

app.post('/users', async (req, res) => {
    const { firstName, lastName, email, password } = req.body;
    const hashedPassword = await bcrypt.hash(password, 10);
    try {
        const user = await User.create({
            firstName,
            lastName,
            email,
            password: hashedPassword
        });
        res.status(201).json({
            message: 'User created',
            data: user
        });
    } catch (error) {
        res.status(500).json({
            message: 'Internal server error'
        });
    }
});
```

### Read
```javascript
const { User } = require('../models');

app.get('/users', async (req, res) => {
    try {
        const users = await User.findAll();
        res.status(200).json({
            message: 'Success',
            data: users
        });
    } catch (error) {
        res.status(500).json({
            message: 'Internal server error'
        });
    }
});
```

### Update
```javascript
const { User } = require('../models');

app.put('/users/:id', async (req, res) => {
    const { id } = req.params;
    const { firstName, lastName, email } = req.body;
    try {
        const user = await User.findOne({
            where: {
                id : id
            }
        });
        if (user) {
            user.firstName = firstName;
            user.lastName = lastName;
            user.email = email;
            await user.save();
            res.status(200).json({
                message: 'User updated',
                data: user
            });
        } else {
            res.status(404).json({
                message: 'User not found'
            });
        }
    } catch (error) {
        res.status(500).json({
            message: 'Internal server error'
        });
    }
});
```

### Delete
```javascript
const { User } = require('../models');

app.delete('/users/:id', async (req, res) => {
    const { id } = req.params;
    try {
        const user = await User.findOne({
            where: {
                id : id
            }
        });
        if (user) {
            await user.destroy();
            res.status(200).json({
                message: 'User deleted'
            });
        } else {
            res.status(404).json({
                message: 'User not found'
            });
        }
    } catch (error) {
        res.status(500).json({
            message: 'Internal server error'
        });
    }
});
```