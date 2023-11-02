# DBDSQL Praktikum
## Buat Schema "kampus"
Penjelasan :
Membuat databases bernama akademik
```
create database kampus
```
## Buat use kampus agar database bisa digunakan
Penjelasan :
Menggunakan database akademik
```
use kampus
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/use.png)
## Buat Table "FAKULTAS"
Penjelasan :
Membuat table fakultas yang memiliki dua kolom yaitu ID_FAKULTAS dan FAKULTAS. Kolom "ID_FAKULTAS" harus selalu memiliki nilai (not null) dan nilai antar kolom harus berbeda karena merupakan primary key, memiliki tipe data "smallint," sementara kolom "FAKULTAS" menggunakan tipe data "VARCHAR(45)" yang memungkinkan penyimpanan teks hingga 45 karakter.
```
create table FAKULTAS (
ID_FAKULTAS smallint primary key not null,
FAKULTAS VARCHAR(45) not null
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/fakultas.png)
## Buat Table "STRATA"
Penjelasan : 
Membuat table STRATA yang memiliki tiga kolom yaitu ID_STRATA, SINGKAT, STRATA. Kolom "ID_STRATA" harus selalu memiliki nilai (not null) dan nilai antar kolom harus berbeda karena merupakan primary key, memiliki tipe data "smallint," sementara kolom "SINGKAT" menggunakan tipe data "VARCHAR(10)" yang memungkinkan penyimpanan teks hingga 10 karakter dan kolom "STRATA" menggunakan tipe data "VARCHAR(45)" yang memungkinkan penyimpanan teks hingga 45 karakter.
```
create table STRATA (
ID_STRATA smallint primary key not null,
SINGKAT VARCHAR(10) not null,
STRATA VARCHAR(45) not null
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/strata.png)
## Buat Table "SELEKSI_MASUK"
Penjelasan : 
Membuat table SELEKSI_MASUK yang memiliki tiga kolom yaitu ID_SELEKSI_MASUK, SINGKAT, ID_JURUSAN, SELEKSI_MASUK. Kolom
ID_SELEKSI_MASUK harus selalu memiliki nilai (not null) dan nilai antar kolom harus berbeda karena merupakan primary key, memiliki tipe data "smallint," sementara kolom SINGKAT menggunakan tipe data VARCHAR(12), kolom "SELEKSI_MASUK" menggunakan tipe data VARCHAR(45)
```
create table SELEKSI_MASUK (
ID_SELEKSI_MASUK smallint primary key not null,
SINGKAT VARCHAR(12) not null,
SELEKSI_MASUK VARCHAR(45) not null
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/selma.png)
## Buat table "JURUSAN"
Penjelasan : 
Membuat table jurusan yang memiliki tiga kolom yaitu ID_JURUSAN, ID_FAKULTAS, JURUSAN. Kolom "ID_JURUSAN" harus selalu memiliki nilai (not null) dan nilai antar kolom harus berbeda karena merupakan primary key, memiliki tipe data "smallint," sementara kolom "JURUSAN" menggunakan tipe data "VARCHAR(45)" yang memungkinkan penyimpanan teks hingga 45 karakter. Foreign Key (ID_FAKULTAS) references FAKULTAS(ID_FAKULTAS) menghubungkan kolom "ID_FAKULTAS" dalam tabel "JURUSAN" dengan kolom "ID_FAKULTAS" dalam tabel "FAKULTAS." Constraint ini adalah foreign key yang memastikan bahwa nilai yang ada dalam kolom "ID_FAKULTAS" dalam tabel "JURUSAN" harus sesuai dengan nilai yang ada dalam kolom "ID_FAKULTAS" dalam tabel "FAKULTAS," yang mengindikasikan hubungan antara jurusan dan fakultas.
```
create table JURUSAN (
ID_JURUSAN smallint primary key not null,
ID_FAKULTAS smallint,
foreign key (ID_FAKULTAS) references FAKULTAS(ID_FAKULTAS),
JURUSAN VARCHAR(45)
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/jurusan.png)
## Buat table PROGRAM_STUDI
Penjelasan : 
Membuat table PROGRAM_STUDI yang memiliki empat kolom yaitu ID_PROGRAM_STUDI, ID_STRATA, ID_JURUSAN, PROGRAM_STUDI. Kolom ID_PROGRAM_STUDI harus selalu memiliki nilai (not null) dan nilai antar kolom harus berbeda karena merupakan primary key, memiliki tipe data "smallint," sementara kolom ID_STRATA & ID_JURUSAN menggunakan tipe data smallint, kolom "PROGRAM_STUDI" menggunakan tipe data "VARCHAR(45)" yang memungkinkan penyimpanan teks hingga 45 karakter. "foreign key (ID_STRATA) references STRATA(ID_STRATA)" menghubungkan kolom "ID_STRATA" dalam tabel "PROGRAM_STUDI" dengan kolom "ID_STRATA" dalam tabel "STRATA." Ini memastikan bahwa nilai dalam kolom "ID_STRATA" harus sesuai dengan nilai yang ada dalam tabel "STRATA," sehingga program studi terkait dengan tingkat strata pendidikan yang benar. "foreign key (ID_JURUSAN) references JURUSAN(ID_JURUSAN)" menghubungkan kolom "ID_JURUSAN" dalam tabel "PROGRAM_STUDI" dengan kolom "ID_JURUSAN" dalam tabel "JURUSAN." Ini menghubungkan program studi dengan jurusan tertentu, memastikan bahwa nilai dalam kolom "ID_JURUSAN" harussesuai dengan nilai yang ada dalam tabel "JURUSAN."
```
create table PROGRAM_STUDI (
ID_PROGRAM_STUDI smallint primary key not null,
ID_STRATA smallint,
ID_JURUSAN smallint,
foreign key (ID_STRATA) references STRATA(ID_STRATA),
foreign key (ID_JURUSAN) references JURUSAN(ID_JURUSAN),
PROGRAM_STUDI VARCHAR(45) not null
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/prodi.png)
## Buat table MAHASISWA
Penjelasan : 
Membuat table "MAHASISWA" Tabel ini memiliki kolom-kolom yang mencakup NIM sebagai primary key, serta informasi seperti nama, tanggal lahir, jenis kelamin, tahun masuk, dan tempat lahir. Dua constraint kunci asing menghubungkan mahasiswa dengan jenis seleksi masuk dan program studi.
```
create table MAHASISWA (
NIM VARCHAR(15) primary key not null,
ID_SELEKSI_MASUK smallint,
ID_PROGRAM_STUDI smallint,
foreign key (ID_SELEKSI_MASUK) references SELEKSI_MASUK(ID_SELEKSI_MASUK),
foreign key (ID_PROGRAM_STUDI) references PROGRAM_STUDI(ID_PROGRAM_STUDI),
NAMA VARCHAR(45),
ANGKATAN smallint,
TGL_LAHIR DATE,
KOTA_LAHIR VARCHAR(60),
JENIS_KELAMIN CHAR(1) check (JENIS_KELAMIN in ('P', 'L'))
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/mahasiswa.png)
## Pernyataan INSERT INTO digunakan untuk memasukkan record baru ke dalam tabel.
## insert into table FAKULTAS
```
insert into FAKULTAS(ID_FAKULTAS, FAKULTAS)
values 
(1, 'Ekonomi & Bisnis'),
(2, 'Ilmu Komputer');
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/insert%20into%20fakultas.png)
## insert into table JURUSAN
```
insert into JURUSAN(ID_JURUSAN, ID_FAKULTAS, JURUSAN)
values
(21, 2, 'Informatika'),
(22, 2, 'Sistem Informasi'),
(23, 2, 'Teknik Komputer');
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/insert%20into%20jurusan.png)
## insert into table STRATA
```
insert into STRATA(ID_STRATA, SINGKAT, STRATA)
values 
(1, 'D1' , 'Diploma'),
(2, 'S1' , 'Sarjana'),
(3, 'S2' , 'Magister');
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/insert%20into%20strata.png)
## insert into table PROGRAM_STUDI
```
insert into PROGRAM_STUDI(ID_PROGRAM_STUDI, ID_STRATA, ID_JURUSAN, PROGRAM_STUDI)
values 
(211, 2, 21, 'Teknik Informatika'),
(212, 2, 21, 'Teknik Komputer'),
(219, 3, 21, 'Magister Ilmu Komputer');
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/insert%20into%20program_studi.png)
## modify table SELEKSI_MASUK
Penjelasan : 
Perintah "ALTER TABLE SELEKSI_MASUK MODIFY COLUMN SELEKSI_MASUK VARCHAR(100)" digunakan untuk mengubah definisi kolom "SELEKSI_MASUK" dalam tabel "SELEKSI_MASUK." Dalam perintah ini, kolom "SELEKSI_MASUK" yang sebelumnya dideklarasikan sebagai VARCHAR(45) diubah menjadi VARCHAR(100), yang memungkinkan penyimpanan teks hingga 100 karakter. Dengan demikian, perintah ALTER TABLE digunakan untuk memperluas kapasitas kolom "SELEKSI_MASUK" sehingga dapat menampung lebih banyak teks atau deskripsi yang lebih panjang. Ini berguna jika Anda perlu menyimpan informasi yang lebih rinci atau lebih panjang dalam kolom ini setelah tabelnya sudah dibuat sebelumnya.
```
alter table SELEKSI_MASUK 
modify SELEKSI_MASUK VARCHAR(100)
```
## insert into table SELEKSI_MASUK
```
insert into SELEKSI_MASUK(ID_SELEKSI_MASUK, SINGKAT, SELEKSI_MASUK)
values 
(1, 'SNMPTN', 'SELEKSI NASIONAL MAHASISWA PERGURUAN TINGGI NEGERI'),
(2, 'SBMPTN', 'SELEKSI NASIONAL MAHASISWA PERGURUAN TINGGI NEGERI');
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/insert%20into%20seleksi_masuk.png)
## insert into table Mahasiswa
```
insert into MAHASISWA(NIM, ID_SELEKSI_MASUK, ID_PROGRAM_STUDI, NAMA, ANGKATAN, TGL_LAHIR, KOTA_LAHIR, JENIS_KELAMIN)
values
('155150400', 1, 211, 'JONI', 2015, 1/1/1997, 'MALANG', 'P'),
('155150401', 2, 212, 'JONO', 2015, 2/10/1997, 'SITUBONDO', 'L');
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/insert%20into%20mahasiswa.png)
## Kesimpulan
DML (Data Manipulation Language) adalah subset dari SQL yang digunakan untuk mengelola, memanipulasi, dan mengambil data dalam basis data. Perintah-perintah DML, seperti INSERT, UPDATE, DELETE, dan SELECT, memungkinkan pengguna untuk menambahkan, mengubah, menghapus, dan mengambil data dari tabel dalam sistem manajemen basis data (DBMS) sesuai dengan kebutuhan aplikasi mereka. DML sangat penting dalam pengelolaan dan interaksi dengan data dalam lingkungan basis data.
