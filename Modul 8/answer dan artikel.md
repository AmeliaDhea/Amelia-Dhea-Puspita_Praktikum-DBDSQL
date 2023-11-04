## Soal
Mengacu pada data berikut https://drive.google.com/drive/folders/1PP6tSH-XIAokt00jeOhxXxTc3rQ26Ra2?usp=sharing
Silakan download dan jalankan, kemudian lakukan perintah soal berikut :
1. Tampilkan semua nama Mahasiswa beserta nama department.
2. Tampilkan semua nama student beserta nama department yang memiliki total SKS (total credit) lebih dari 100.
3. Tampilkan nama student dan nama instructor yang bekerja pada department yang sama
## Penjelasan DDL
### No 1
```
SELECT student.name, department.dept_name
FROM student, department
WHERE student.dept_name = department.dept_name;
```
Menampilkan data nama yang diambil dari tabel student dan nama departemen yang diambil dari tabel department.
Dari tabel student dan department.
Dengan kondisi dimana akan menampilkan jika nilai kolom dept_name pada tabel student sama dengan nilai kolom dept_name pada tabel department.
### No 2
```
SELECT student.name, department.dept_name, student.tot_cred
FROM student JOIN department
ON  student.dept_name = department.dept_name
WHERE  student.tot_cred > 100;
```
Memilih name dari tabel student, dept_name dari tabel department dan tot_cred dari tabel student.
Menggabungkan tabel student dan departement.
Dengan kondisi dimana saat nilai kolom dept_name pada tabel student sama dengan nilai kolom dept_name pada tabel department.
Dimana akan mengambil data saat nilai tot_cred lebih besar dari 100
### No 3
```
SELECT student.name as "student name", instructor.name as "instructor name"
FROM student
JOIN instructor 
WHERE student.dept_name = instructor.dept_name;
```
Memilih name dari table setudent diberikan nama "student name" saat ditampilkan dan name dari tabel instructor diberikan nama "instructor name"
Mengambil data dari tabel student.
Menggabungkan data dari tabel instructor.
Dengan kondisi dimana dept_name dari tabel student sama dengan dept_name dari tabel instructor.
