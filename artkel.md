# DBDSQL Praktikum
## Buat Schema "kampus"
```
create database kampus
```
```
## Buat use agar database dapat diakses
use kampus
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/use.png)
## Buat Table "FAKULTAS"
```
create table FAKULTAS (
ID_FAKULTAS smallint primary key not null,
FAKULTAS VARCHAR(45) not null
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/fakultas.png)
## Buat Table "STRATA"
```
create table STRATA (
ID_STRATA smallint primary key not null,
SINGKAT VARCHAR(10) not null,
STRATA VARCHAR(45) not null
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/strata.png)
## Buat Table "SELEKSI_MASUK"
```
create table SELEKSI_MASUK (
ID_SELEKSI_MASUK smallint primary key not null,
SINGKAT VARCHAR(12) not null,
SELEKSI_MASUK VARCHAR(45) not null
)
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/selma.png)
## Buat table "JURUSAN"
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
