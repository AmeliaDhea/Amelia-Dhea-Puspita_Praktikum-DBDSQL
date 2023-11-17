## Union
### 1. Lakukan perintah Insert seperti yang ada pada Perintah 6.7 untuk menambahkandata pada table Mahasiswa
```
INSERT INTO univ.MAHASISWA
VALUES('155150404', 1,212,'JESSY',2016,'1999-2-10','BANDUNG','P'),
('155150405', 2 ,219,'BAMBANG',2014,'1996-9-27','MAKASSAR','L');
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%208/Screenshot%20Tugas%208/1.%20insert%20into%20mahasiswa.png)
Penjelasan : Menambahkan data mahasiswa ke dalam tabel MAHASISWA di skema univ, dengan nilai-nilai kolom seperti NIM, ID_JURUSAN, ID_PRODI, NAMA, ANGKATAN, TGL_LAHIR, TEMPAT_LAHIR, dan JENIS_KELAMIN.
### 2. Lakukan perintah DDL seperti yang ada pada Perintah 6.8 untuk membuat sebuah table baru Mahasiswa_Pindahan
```
CREATE TABLE univ.MAHASISWA_PINDAHAN(
NIM VARCHAR(15) NOT NULL PRIMARY KEY,
ID_SELEKSI_MASUK SMALLINT,
FOREIGN KEY (ID_SELEKSI_MASUK) REFERENCES
univ.SELEKSI_MASUK(ID_SELEKSI_MASUK),
ID_PROGRAM_STUDI SMALLINT,
FOREIGN KEY (ID_PROGRAM_STUDI) REFERENCES
univ.PROGRAM_STUDI(ID_PROGRAM_STUDI),
NAMA VARCHAR(45),
ANGKATAN SMALLINT,
TGL_LAHIR DATE,
KOTA_LAHIR VARCHAR(60),
JENIS_KELAMIN CHAR(1) CHECK (JENIS_KELAMIN IN ('L','P'))
);
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%208/Screenshot%20Tugas%208/2.%20create%20table%20mahasiswa%20pindahan.png)
Penjelasan : Membuat tabel baru bernama Mahasiswa_Pindahan di skema univ, dengan kolom-kolom NIM, ID_SELEKSI_MASUK, ID_PROGRAM_STUDI, NAMA, ANGKATAN, TGL_LAHIR, KOTA_LAHIR, dan JENIS_KELAMIN, serta menetapkan beberapa kendala integritas referensial pada kolom ID_SELEKSI_MASUK dan ID_PROGRAM_STUDI.
### 3. Lakukan perintah Insert seperti yang ada pada Perintah 6.9 untuk menambahkan data pada table Mahasiswa_Pindahan
```
INSERT INTO univ.MAHASISWA_PINDAHAN
VALUES ('155150500', 1 ,211,'BUDI', 2015,'1997-3-3','BANYUWANGI','L'),
('155150501', 2,212,'ANDI',2015,'1997-2-21','JAKARTA','L'),
('155150502', 2 ,211,'DIMAS', 2015,'1998-4-11','SURABAYA','L'),
('155150503', 2 ,211,'DIDIN',2015,'1997-2-26','BANDUNG','L');
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%208/Screenshot%20Tugas%208/3.%20insert%20into%20mahasiswa%20pindahan.png)
Penjelasan : Menambahkan data ke dalam tabel Mahasiswa_Pindahan di skema univ dengan nilai-nilai pada kolom NIM, ID_SELEKSI_MASUK, ID_PROGRAM_STUDI, NAMA, ANGKATAN, TGL_LAHIR, KOTA_LAHIR, dan JENIS_KELAMIN sesuai dengan baris-baris yang disebutkan.
### 4. Tampilkan NIM, NAMA, JENIS_KELAMIN, KOTA LAHIR dan ANGKATAN dari Mahasiswa yang memiliki Kota Lahir dengan inisial B dan dari Mahasiswa_Pindahan yang memiliki Nama dengan inisial D. Urutkan berdasarkan NIM.
```
SELECT NIM, NAMA, JENIS_KELAMIN, KOTA_LAHIR, ANGKATAN
FROM univ.MAHASISWA
WHERE KOTA_LAHIR LIKE 'B%'

UNION all

SELECT NIM, NAMA, JENIS_KELAMIN, KOTA_LAHIR, ANGKATAN
FROM univ.MAHASISWA_PINDAHAN
WHERE NAMA LIKE 'D%'
ORDER BY NIM;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%208/Screenshot%20Tugas%208/4%20select.png)
Penjelasan : Menggabungkan hasil pencarian mahasiswa dari tabel MAHASISWA yang tempat lahirnya dimulai dengan 'B' dengan hasil pencarian mahasiswa dari tabel MAHASISWA_PINDAHAN yang nama mereka dimulai dengan 'D', kemudian hasilnya diurutkan berdasarkan NIM.
### 5. Tampilkan NIM, NAMA, JENIS_KELAMIN, KOTA LAHIR dan ANGKATAN dari Mahasiswa Angkatan 2015 dan dari Mahasiswa_Pindahan tetapi kecuali Mahasiswa_Pindahan yang memiliki Kota Lahir dengan inisial M urutkan berdasarkan NIM.
```
SELECT NIM, NAMA, JENIS_KELAMIN, KOTA_LAHIR, ANGKATAN
FROM univ.MAHASISWA
WHERE ANGKATAN = 2015

UNION all

SELECT NIM, NAMA, JENIS_KELAMIN, KOTA_LAHIR, ANGKATAN
FROM univ.MAHASISWA_PINDAHAN
WHERE KOTA_LAHIR NOT LIKE 'M%'
ORDER BY NIM;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%208/Screenshot%20Tugas%208/5%20select.png)
Penjelasan : Menggabungkan hasil pencarian mahasiswa dari tabel MAHASISWA yang bergabung pada tahun 2015 dengan hasil pencarian mahasiswa dari tabel MAHASISWA_PINDAHAN yang tempat lahirnya tidak dimulai dengan 'M', kemudian hasilnya diurutkan berdasarkan NIM.
