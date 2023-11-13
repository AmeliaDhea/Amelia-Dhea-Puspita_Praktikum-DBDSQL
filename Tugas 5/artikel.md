### Fungsi Skalar
## A. String Function
# Concat
```
select concat_ws(' ',ID, name) as PROFIL
from student;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20concat.png)
Penjelasan : Query tersebut menggabungkan kolom ID dan name dari tabel student dengan spasi di antara keduanya, dan memberikan alias PROFIL pada hasilnya.
# Substring_Index
```
select substring_index(dept_name,' ',1) as JURUSAN_INDEX
from department;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/substr%20index.png)
Penjelasan : Query tersebut mengambil bagian awal dari nilai dalam kolom dept_name sebelum karakter spasi pertama dan memberikan alias JURUSAN_INDEX pada hasilnya.
# Substr
```
select substr(dept_name, 1, 3) as KARAKTER
from department;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20substr.png)
Penjelasan : Query tersebut mengambil tiga karakter pertama dari nilai dalam kolom dept_name dan memberikan alias KARAKTER pada hasilnya.
# Length
```
select dept_name,length (dept_name) as TOTAL_CHAR
from department;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20length.png)
Penjelasan : Query tersebut menampilkan kolom dept_name dan panjang (jumlah karakter) dari setiap nilai dalam kolom tersebut, dengan memberikan alias TOTAL_CHAR pada hasilnya.
# Replace
```
select name, replace (name,'JONO','BUDI') as NAMA_BARU
from student ;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20replace.png)
Penjelasan : Query tersebut menampilkan kolom name dari tabel student, sambil mengganti setiap kemunculan string 'JONO' dengan 'BUDI' dan memberikan alias NAMA_BARU pada hasilnya.
## B. Numeric Function
# ABS
```
SELECT ABS(credits)
FROM course;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20abs.png)
Penjelasan : Query tersebut menampilkan nilai absolut (absolute value) dari setiap nilai dalam kolom credits dari tabel course.
# Ceiling
```
SELECT CEILING(salary)
FROM instructor;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20ceiling.png)
Penjelasan : Query tersebut menampilkan nilai plafon (ceiling) dari setiap nilai dalam kolom salary dari tabel instructor, yaitu pembulatan ke atas ke bilangan bulat terdekat.
# Floor
```
SELECT FLOOR(salary)
FROM instructor;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20floor.png)
Penjelasan : Query tersebut menampilkan nilai dasar (floor) dari setiap nilai dalam kolom salary dari tabel instructor, yaitu pembulatan ke bawah ke bilangan bulat terdekat.
# Round
```
SELECT ROUND(salary)
FROM instructor;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20round.png)
Penjelasan : Query tersebut menampilkan nilai dari setiap nilai dalam kolom salary dari tabel instructor setelah dilakukan pembulatan (rounding) ke bilangan bulat terdekat.
# SQRT
```
SELECT SQRT(salary)
FROM instructor;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20sqrt.png)
Penjelasan : Query tersebut menampilkan akar kuadrat dari setiap nilai dalam kolom salary dari tabel instructor.
## C. Date Function
# Curdate
```
select curdate();
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20curdate.png)
Penjelasan : Query tersebut mengembalikan tanggal saat ini (current date) dalam format YYYY-MM-DD.
# Curtime
```
select curtime();
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20curtime.png)
Penjelasan : Query tersebut mengembalikan waktu saat ini (current time) dalam format HH:MM:SS.
# Timestamp
```
select TIMESTAMP("2017-07-23");
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20timestamp.png)
Penjelasan : Query tersebut menghasilkan nilai timestamp untuk tanggal yang ditentukan ("2017-07-23") dengan waktu default pada tengah malam (00:00:00).
### Fungsi Agregasi
# SUM
```
SELECT SUM(salary)
FROM instructor;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20sum.png)
Penjelasan : Query tersebut menghitung dan menampilkan jumlah total gaji (salary) dari semua baris dalam kolom salary pada tabel instructor.
# AVG
```
SELECT AVG(salary)
FROM instructor;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20avg.png)
Penjelasan : Query tersebut menghitung dan menampilkan nilai rata-rata (average) dari kolom salary pada tabel instructor.
# Count
```
SELECT COUNT (*) FROM student;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/select%20bintang%20avg.png)
Penjelasan : Query tersebut menghitung dan menampilkan jumlah total baris (jumlah mahasiswa) dalam tabel student.
# Klausa Group and Klausa Having
```
select avg(budget) as RATA2_BUDGET, dept_name as NAMA_DEPARTMEN from department
group by dept_name having avg (budget) > 2;
```
![alt text](https://github.com/AmeliaDhea/Amelia-Dhea-Puspita_Praktikum-DBDSQL/blob/main/Tugas%205/Screnshoot%20Tugas%205/klausa%20group%20and%20klausa%20having.png)
Penjelasan : Query tersebut menghitung rata-rata budget untuk setiap departemen dari tabel department, kemudian hanya menampilkan hasilnya jika rata-rata budget departemen tersebut lebih besar dari 2, dengan memberikan alias RATA2_BUDGET pada hasilnya.
