# Pemrograman-Dasar-Database-MySQL 
Berikut adalah perintah perintah dasar dalam database MYSQL part 1

Enter password: ***
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 5
Server version: 5.5.51 MySQL Community Server (GPL)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> create database pegawai;
Query OK, 1 row affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| pegawai            |
| performance_schema |
| test               |
+--------------------+
5 rows in set (0.00 sec)

mysql> drop database pegawai;
Query OK, 0 rows affected (0.05 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| test               |
+--------------------+
4 rows in set (0.00 sec)

mysql> create database karyawan;
Query OK, 1 row affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| karyawan           |
| mysql              |
| performance_schema |
| test               |
+--------------------+
5 rows in set (0.00 sec)

mysql> use karyawan;
Database changed
mysql> create table sdm
    -> (id char (5) primary key,
    -> nama varchar (15) not null,
    -> jenis_kelamin varchar (10) not null,
    -> alamat varchar (15) not null);
Query OK, 0 rows affected (0.33 sec)

mysql> show tables;
+--------------------+
| Tables_in_karyawan |
+--------------------+
| sdm                |
+--------------------+
1 row in set (0.00 sec)

mysql> desc sdm;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| id            | char(5)     | NO   | PRI | NULL    |       |
| nama          | varchar(15) | NO   |     | NULL    |       |
| jenis_kelamin | varchar(10) | NO   |     | NULL    |       |
| alamat        | varchar(15) | NO   |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
4 rows in set (0.17 sec)

mysql> create table mahasiswa
    -> (nim char (10) primary key,
    -> nama varchar (20) not null,
    -> jurusan varchar (15) not null,
    -> alamat varchar (20) not null);
Query OK, 0 rows affected (0.14 sec)

mysql> show tables;
+--------------------+
| Tables_in_karyawan |
+--------------------+
| mahasiswa          |
| sdm                |
+--------------------+
2 rows in set (0.00 sec)

mysql> drop table mahasiswa;
Query OK, 0 rows affected (0.36 sec)

mysql> show tables;
+--------------------+
| Tables_in_karyawan |
+--------------------+
| sdm                |
+--------------------+
1 row in set (0.00 sec)

mysql> rename table sdm to pegawai;
Query OK, 0 rows affected (0.12 sec)

mysql> show tables;
+--------------------+
| Tables_in_karyawan |
+--------------------+
| pegawai            |
+--------------------+
1 row in set (0.00 sec)

mysql> alter table pegawai
    -> add status varchar (15) not null,
    -> add kota varchar (15) not null;
Query OK, 0 rows affected (0.31 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc pegawai;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| id            | char(5)     | NO   | PRI | NULL    |       |
| nama          | varchar(15) | NO   |     | NULL    |       |
| jenis_kelamin | varchar(10) | NO   |     | NULL    |       |
| alamat        | varchar(15) | NO   |     | NULL    |       |
| status        | varchar(15) | NO   |     | NULL    |       |
| kota          | varchar(15) | NO   |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
6 rows in set (0.03 sec)

mysql> alter table pegawai
    -> add tanggal_lahir date after jenis_kelamin;
Query OK, 0 rows affected (0.39 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc pegawai;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| id            | char(5)     | NO   | PRI | NULL    |       |
| nama          | varchar(15) | NO   |     | NULL    |       |
| jenis_kelamin | varchar(10) | NO   |     | NULL    |       |
| tanggal_lahir | date        | YES  |     | NULL    |       |
| alamat        | varchar(15) | NO   |     | NULL    |       |
| status        | varchar(15) | NO   |     | NULL    |       |
| kota          | varchar(15) | NO   |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
7 rows in set (0.03 sec)

mysql> alter table pegawai
    -> change jenis_kelamin jenkel char (1) not null;
Query OK, 0 rows affected (0.23 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc pegawai;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| id            | char(5)     | NO   | PRI | NULL    |       |
| nama          | varchar(15) | NO   |     | NULL    |       |
| jenkel        | char(1)     | NO   |     | NULL    |       |
| tanggal_lahir | date        | YES  |     | NULL    |       |
| alamat        | varchar(15) | NO   |     | NULL    |       |
| status        | varchar(15) | NO   |     | NULL    |       |
| kota          | varchar(15) | NO   |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
7 rows in set (0.03 sec)

mysql> alter table pegawai
    -> modify kota varchar (25) not null;
Query OK, 0 rows affected (0.53 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc pegawai;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| id            | char(5)     | NO   | PRI | NULL    |       |
| nama          | varchar(15) | NO   |     | NULL    |       |
| jenkel        | char(1)     | NO   |     | NULL    |       |
| tanggal_lahir | date        | YES  |     | NULL    |       |
| alamat        | varchar(15) | NO   |     | NULL    |       |
| status        | varchar(15) | NO   |     | NULL    |       |
| kota          | varchar(25) | NO   |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
7 rows in set (0.03 sec)

mysql> alter table pegawai
    -> drop kota;
Query OK, 0 rows affected (0.25 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc pegawai;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| id            | char(5)     | NO   | PRI | NULL    |       |
| nama          | varchar(15) | NO   |     | NULL    |       |
| jenkel        | char(1)     | NO   |     | NULL    |       |
| tanggal_lahir | date        | YES  |     | NULL    |       |
| alamat        | varchar(15) | NO   |     | NULL    |       |
| status        | varchar(15) | NO   |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
6 rows in set (0.05 sec)

mysql> insert into pegawai
    -> (id, nama, jenkel, tanggal_lahir, alamat, status)
    -> values
    -> ("P001", "Burhan", "L", "1998-10-10", "Bekasi", "Meikah");
Query OK, 1 row affected (0.09 sec)

mysql> insert into pegawai
    -> values
    -> ("P002", "Mirna", "P", "1999-05-09", "Tambun", "Belum Menikah"),
    -> ("P003", "Joko Ardi", "L", "1997-04-25", "Cibitung", "Menikah"),
    -> ("P004", "M.Sulaiman", "L", "1997-08-20", "Bekasi Selatan", "Menikah"),
    -> ("P005", "Siska", "P", "1997-08-08", "Karawang", "Belum Menikah");
Query OK, 4 rows affected (0.09 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from pegawai;
+------+------------+--------+---------------+----------------+---------------+
| id   | nama       | jenkel | tanggal_lahir | alamat         | status        |
+------+------------+--------+---------------+----------------+---------------+
| P001 | Burhan     | L      | 1998-10-10    | Bekasi         | Meikah        |
| P002 | Mirna      | P      | 1999-05-09    | Tambun         | Belum Menikah |
| P003 | Joko Ardi  | L      | 1997-04-25    | Cibitung       | Menikah       |
| P004 | M.Sulaiman | L      | 1997-08-20    | Bekasi Selatan | Menikah       |
| P005 | Siska      | P      | 1997-08-08    | Karawang       | Belum Menikah |
+------+------------+--------+---------------+----------------+---------------+
5 rows in set (0.00 sec)

mysql>
