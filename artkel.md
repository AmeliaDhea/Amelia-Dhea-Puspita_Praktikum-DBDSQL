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
