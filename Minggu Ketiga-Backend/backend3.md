# MongoDB
## Apa Itu MongoDB?
MongoDB adalah salah satu database open source NoSQL yang cukup populer digunakan. MongoDB sering dipakai untuk aplikasi berbasis Cloud, Big Data maupun Grid Computing. Jika SQL menyimpan data menggunakan relasi tabel, MongoDB menggunakan dokumen dengan format JSON.

## Apa Itu NoSQL?
NoSQL adalah akronim dari Not Only SQL. NoSQL adalah sebuah database yang tidak menggunakan SQL. Maksud dari tidak menggunakan SQL adalah artinya data-data dalam database ini tidak disimpan dalam bentuk relasi tabular layaknya SQL. NoSQL menyimpan data dalam bentuk dokumen, key-value, graph, atau wide-column. MongoDB adalah salah satu contoh dari NoSQL dengan bentuk dokumen.

## Kelebihan NoSQL
- Sistem tidak membutuhkan tabel
- Data yang disimpan tidak harus memiliki struktur yang sama
- Secara default sudah menggunakan JSON, sehingga mempermudah integrasi dengan JavaScript
- Performa lebih cepat dengan kemampuan menampung data dengan beragam variasi

## Kekurangan NoSQL
- Tidak mendukung transaksi
- Menimbulkan masalah pada konsistensi data
- Menggunakan banyak memory
- Hanya bisa menampung sebanyak 16MB data dalam satu dokumen
  
## Anatomi Komponen MongoDB
MongoDB terdiri dari beberapa komponen, yaitu:
- **MongoDB Server** adalah komponen utama dari MongoDB. Komponen ini bertugas untuk menyimpan data dan menjalankan operasi-operasi CRUD.
- Pada sebuah MongoDB Server, terdapat beberapa **Database**. Database adalah sebuah container untuk menyimpan data. Database dapat berisi satu atau lebih **Collection**.
- **Collection** adalah sebuah container untuk menyimpan dokumen. Collection dapat juga diartikan sebagai tabel pada database SQL. Collection dapat berisi satu atau lebih **Document**.
- **Document** adalah sebuah unit penyimpanan data. Document memiliki format JSON. Document dapat juga diartikan sebagai record (row) pada database SQL. Document dapat berisi satu atau lebih **Field**.
- **Field** adalah sebuah unit penyimpanan data. Field memiliki nama dan nilai. Field sama seperti Column pada database SQL. Field dapat berisi satu atau lebih **Subfield**.
- **Subfield** adalah sebuah unit penyimpanan data. Subfield memiliki nama dan nilai. Subfield tidak dapat memiliki subfield lagi.

## Instalasi MongoDB
- Untuk instalasi MongoDB, silahkan download terlebih dahulu MongoDB Community Server di https://www.mongodb.com/download-center/community
- Setelah selesai download, silahkan install MongoDB Community Server dengan cara double click pada file yang sudah di download.
- Setelah selesai install, silahkan buka MongoDB Compass untuk memastikan instalasi MongoDB berhasil.

## MongoDB Compass
MongoDB Compass adalah GUI untuk MongoDB. MongoDB Compass dapat digunakan untuk membuat database, collection, dan document. MongoDB Compass juga dapat digunakan untuk melakukan operasi CRUD.

## Basic CRUD MongoDB
MongoDB dapat diakses pada terminal dengan mengetikkan command mongo. Setelah masuk ke MongoDB, secara default database yang digunakan bernama test, sehingga jika kita tidak membuat database baru, maka data yang kita buat akan disimpan pada database test.

Untuk menampiklan database yang ada, silahkan ketikkan command:
```
show dbs
```

Untuk membuat database baru dapat dilakukan dengan cara:
```
use <nama_database>
```

Untuk membuat collection baru, silahkan ketikkan command:
```
db.createCollection("<nama_collection>")
```

Untuk menampilkan collection yang ada, silahkan ketikkan command:
```
show collections
```

Untuk melakukan insert data, silahkan ketikkan command:
```
db.<nama_collection>.insert({
    <nama_field>: <nilai_field>
})
```

Untuk melihat data yang ada, silahkan ketikkan command:
```
db.<nama_collection>.find()
```

Untuk melakukan update data, silahkan ketikkan command:
```
db.<nama_collection>.update(
    {<nama_field>: <nilai_field>},
    {$set: {<nama_field>: <nilai_field>}}
)
```

Untuk melakukan delete data, silahkan ketikkan command:
```
db.<nama_collection>.remove(
    {<nama_field>: <nilai_field>}
)
```

## MongoDB Schema
Dalam mendesain database, kita perlu memikirkan struktur data yang akan kita gunakan. Struktur data yang kita gunakan akan mempengaruhi performa dari database. Untuk itu, kita perlu memikirkan struktur data yang akan kita gunakan. Struktur data yang baik adalah struktur data yang dapat memenuhi kebutuhan dari aplikasi yang kita buat. Kita dapat menggunakan 2 pendekatan dalam mendesain schema mongodb, yaitu:
- Embedded Document\
  Keuntungan :
  - Bisa mendapatkan seluruh data dalam satu query
  - Bisa mengupdate semua informasi terkait dalam 1 atomic operation
  - bisa menggunakan operator transaksi\
  Kekurangan :
  - Tidak bisa mengakses embedded document secara langsung
  - Memiliki batasan 16MB untuk satu document
<br> <br>

- Referenced Document\
  Keuntungan :
  - Bisa mengakses referenced document secara langsung sebagai satu entity tersendiri
  - Tidak perlu khawatir batasan data, karena data disimpan di collection yang berbeda\
  Kekurangan :
    - Harus melakukan 2 query untuk mendapatkan data
    - Tidak bisa menggunakan operator transaksi
    - Untuk update data, harus melakukan 2 query

## Relasi
- one-to-one\
  cara mendesainnya yang disarankan adalah dengan menggunakan embedded document
- one-to-many\
  cara mendesainnya yang disarankan adalah dengan menggunakan referenced document
- many-to-many\
  cara mendesainnya yang disarankan adalah dengan menggunakan referenced document

# Mongoose
## Apa itu Mongoose?
Mongoose adalah sebuah library yang digunakan untuk mempermudah penggunaan MongoDB pada Node.js. Mongoose menyediakan sebuah API yang dapat digunakan untuk melakukan operasi CRUD pada MongoDB. Mongoose juga menyediakan fitur untuk melakukan validasi data dan membuat schema. Mongoose bisa digunakan untuk mengelola hubungan antara data, menyediakan validasi. Dan juga digunakan untuk menerjemahkan antara objek dalam kode dan representasi Objek tersebut di MongoDB.

## Instalasi Mongoose
Untuk instalasi Mongoose, silahkan ketikkan command:
```
npm install mongoose
```

## Penggunaan Mongoose
Untuk menggunakan Mongoose, silahkan ketikkan command:
```javascript
const mongoose = require('mongoose');
const url = 'mongodb://localhost:27017/<nama_database>';
mongoose.connect(url, {
    useNewUrlParser: true,
    useUnifiedTopology: true,
    useDindAndModify: false
});

const db = mongoose.connection;
db.on('error', console.error.bind(console, 'connection error:'));
db.once('open', function() {
    console.log('Koneksi berhasil');
});
```

## Schema
Schema adalah sebuah blueprint untuk membuat model. Schema digunakan untuk mendefinisikan struktur dari data yang akan disimpan di MongoDB. Schema juga digunakan untuk mendefinisikan validasi data. Schema juga digunakan untuk mendefinisikan hubungan antar data. Untuk membuat schema, silahkan ketikkan command:
```javascript
const mongoose = require('mongoose');
const Schema = mongoose.Schema;
const userSchema = new Schema({
    name: {
        type: String,
        required: true
    },
    age: {
        type: Number,
        required: true
    }
},{timestamps: true});
const User = mongoose.model('User', userSchema);
```

## Basic CRUD
Untuk melakukan insert data (create), silahkan ketikkan command:
```javascript
app.post('/users', async (req, res) => {
    try{
        const user = await User.create({
            name: req.body.name,
            age: req.body.age
        });
        res.status(201).json({
            status: 'success',
            data: user
        });
    }
    catch(err){
        res.status(400).json({message: err.message});
    }
});
```

Untuk melakukan read data, silahkan ketikkan command:
```javascript
app.get('/users', async (req, res) => {
    try{
        const users = await User.find();
        res.status(200).json({
            status: 'success',
            data: users
        });
    }
    catch(err){
        res.status(400).json({message: err.message});
    }
});
```

Untuk melakukan update data, silahkan ketikkan command:
```javascript
app.put('/users/:id', async (req, res) => {
    try{
        const user = await User.findByIdAndUpdate({
            _id: req.params.id
        }, {
            name: req.body.name,
            age: req.body.age
        }, (error, result) => {
            if(error){
                res.status(400).json({message: error.message});
            }
            else{
                res.status(200).json({
                    status: 'success',
                    data: result
                });
            }
        });
    }
    catch(err){
        res.status(400).json({message: err.message});
    }
});
```

Untuk melakukan delete data, silahkan ketikkan command:
```javascript
app.delete('/users/:id', async (req, res) => {
    try{
        const user = await User.deleteOne({
            _id: req.params.id
        }, (error, result) => {
            if(error){
                res.status(404).json({message: error.message});
            }
            else{
                res.status(200).json({
                    status: 'success',
                    data: result
                });
            }
        });
    }
    catch(err){
        res.status(400).json({message: err.message});
    }
});
```

## Populate
Populate digunakan untuk mengakses data yang terdapat pada referenced document. Populate digunakan layaknya join pada SQL. Untuk menggunakan populate, silahkan ketikkan command:
```javascript
app.get('/users/:id', async (req, res) => {
    try{
        const user = await User.findById(req.params.id).populate('posts');
        res.status(200).json({
            status: 'success',
            data: user
        });
    }
    catch(err){
        res.status(400).json({message: err.message});
    }
});
```

# Docker
## Latar Belakang
Kemunculan Docker dilatarbelakangi oleh adanya perbedaan antara lingkungan pengembangan dan lingkungan produksi. Perbedaan library, dependency, OS, hingga perbedaan hardware dapat menyebabkan terjadinya error pada saat aplikasi dijalankan di lingkungan produksi. Docker dapat digunakan untuk memecah permasalahan tersebut. Docker dapat digunakan untuk membangun container yang dapat dijalankan di berbagai platform. Docker juga dapat digunakan untuk membangun container yang dapat dijalankan di lingkungan produksi.

## Apa itu Docker?
Dockers adalah sebuah platform yang dapat digunakan untuk membangun, menjalankan, dan mengelola container. Docker dapat digunakan untuk membangun container yang dapat dijalankan di berbagai platform. Docker digunakan untuk men-sharing kernel dari OS dan meng-containerkan sesuatu aplikasi agar dapat berjalan di mana saja dan kapan saja tanpa adanya pengaruh dari faktor luar seperti OS, library, dependency, dan hardware.

Docker bekerja sebagai virtual service provider yang menyediakan hal-hal yang diperlukan untuk aplikasi mulai dari akses file, koneksi internet, hingga port agar aplikasi dapat berjalan dengan mulus.

## Docker vs Virtual Machine
- Virtual Machine\
  VM memakan banyak resource dan waktu ketika booting karena virtualisasi dilakukan pada host hardwarenya.

- Docker\
  Docker membutuhkan resource yang lebih sedikit dan lebih cepat ketika booting karena docker tidak melakukan virtualisasi pada host hardwarenya, melainkan pada host OSnya.

## Docker Fundamental
- Docker File\
  Docker file adalah sebuah file yang berisi instruksi untuk membuat sebuah image. Docker file dapat dibuat dengan menggunakan text editor.
- Docker Image\
  Docker image adalah sebuah file yang berisi instruksi untuk membuat sebuah container.
- Docker Container\
  Docker container adalah sebuah instance dari docker image.
- Docker Registry\
  Docker registry adalah sebuah tempat untuk menyimpan docker image.

## Instalasi Docker
Langkah-langkah instalasi docker telah dijelaskan pada dokumentasi resmi docker. Silahkan kunjungi link berikut: https://docs.docker.com/get-docker/

## Docker Command
- Docker Pull\
  Docker pull digunakan untuk mengunduh docker image dari docker registry. Docker pull dapat digunakan dengan command:
  ```bash
  docker pull <image_name>
  ```

- Docker Images\
  Docker images digunakan untuk melihat docker image yang telah diunduh. Docker images dapat digunakan dengan command:
  ```bash
  docker images
  ```

- Docker Run\
    Docker run digunakan untuk menjalankan docker image. Docker run dapat digunakan dengan command:
    ```bash
    docker run <image_name>
    ```
    Docker run juga dapat digunakan dengan command:
    ```bash
    docker run -d -p <host_port>:<container_port> -e <environment_variable> --name <nama_container> <image_name>
    ```

- Docker PS\
    Docker ps digunakan untuk melihat docker container yang sedang berjalan. Docker ps dapat digunakan dengan command:
    ```bash
    docker ps
    ```

## Docker File
Docker file adalah sebuah file yang berisi instruksi untuk membuat sebuah image. Docker file dapat dibuat dengan menggunakan text editor. Cara untuk membuat dockerfile yaitu :
- Buat file dengan nama Dockerfile pada folder yang akan digunakan untuk membuat docker image.
- tulis command pada dockerfile sesuai dengan kebutuhan.
- jalankan command docker build untuk membuat docker image.

## Docker Compose
Docker Compose adalah cara untuk menjalankan lebih dari satu container secara bersamaan dan saling terhubung. Sebagai contoh ketika kita ingin menjalankan aplikasi web yang terdiri dari web server, database server, dan reverse proxy. Docker compose dapat digunakan untuk menjalankan semua container tersebut secara bersamaan dan saling terhubung. Cara untuk menggunakan docker compose yaitu :
- Buat file dengan nama docker-compose.yml pada folder yang akan digunakan untuk membuat docker image.
- Tulis command pada docker-compose.yml sesuai dengan kebutuhan.
- jalankan command docker-compose up untuk menjalankan docker container.

