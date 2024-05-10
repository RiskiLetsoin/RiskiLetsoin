
Setting environment for using XAMPP for Windows.
LENOVO@DESKTOP-4P4TSMI c:\xampp
# mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 11
Server version: 10.4.28-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| pegawai            |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
6 rows in set (0.001 sec)

MariaDB [(none)]> use pegawai;
Database changed
MariaDB [pegawai]> CREATE TABLE data_pegawai (
    ->     id_pegawai CHAR(10) PRIMARY KEY,
    ->     nama_depan VARCHAR(10) NOT NULL,
    ->     nama_belakang VARCHAR(10) NOT NULL,
    ->     email VARCHAR(20) NOT NULL,
    ->     telepon VARCHAR(15) NOT NULL,
    ->     tgl_kontrak VARCHAR(15) NOT NULL,
    ->     id_job VARCHAR(10) NOT NULL,
    ->     gaji VARCHAR(10) NOT NULL,
    ->     tunjangan VARCHAR(10) NOT NULL
    -> );
Query OK, 0 rows affected (0.868 sec)

MariaDB [pegawai]> desc data_pegawai;
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| id_pegawai    | char(10)    | NO   | PRI | NULL    |       |
| nama_depan    | varchar(10) | NO   |     | NULL    |       |
| nama_belakang | varchar(10) | NO   |     | NULL    |       |
| email         | varchar(20) | NO   |     | NULL    |       |
| telepon       | varchar(15) | NO   |     | NULL    |       |
| tgl_kontrak   | varchar(15) | NO   |     | NULL    |       |
| id_job        | varchar(10) | NO   |     | NULL    |       |
| gaji          | varchar(10) | NO   |     | NULL    |       |
| tunjangan     | varchar(10) | NO   |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
9 rows in set (0.508 sec)

MariaDB [pegawai]> INSERT INTO data_pegawai (id_pegawai, nama_depan, nama_belakang, email, telepon, tgl_kontrak, id_job, gaji, tunjangan)
    -> VALUES
    -> ("E001", "Riski", "Letsoin", "ikhos@yahoo.com", "07117059004", "2005-09-01", "L0001", "2000000", "500000"),
    -> ("E002", "Didi", "Koedoeboen", "digan@yahoo.com", "081312345678", "2006-09-01", "L0002", "2000000", "200000"),
    -> ("E003", "Zahra", "Renhoran", "zraken@gmail.com", "081367384322", "2006-10-01", "L0003", "1500000", "NULL"),
    -> ("E004", "Reza", "Effendy", "jajax@gmail.com", "081363484342", "2006-10-01", "L0004", "1500000", "0");
Query OK, 4 rows affected (0.628 sec)
Records: 4  Duplicates: 0  Warnings: 0

MariaDB [pegawai]> select * from data_pegawai;
+------------+------------+---------------+------------------+--------------+-------------+--------+---------+-----------+
| id_pegawai | nama_depan | nama_belakang | email            | telepon      | tgl_kontrak | id_job | gaji    | tunjangan |
+------------+------------+---------------+------------------+--------------+-------------+--------+---------+-----------+
| E001       | Riski      | Letsoin       | ikhos@yahoo.com  | 07117059004  | 2005-09-01  | L0001  | 2000000 | 500000    |
| E002       | Didi       | Koedoeboen    | digan@yahoo.com  | 081312345678 | 2006-09-01  | L0002  | 2000000 | 200000    |
| E003       | Zahra      | Renhoran      | zraken@gmail.com | 081367384322 | 2006-10-01  | L0003  | 1500000 | NULL      |
| E004       | Reza       | Effendy       | jajax@gmail.com  | 081363484342 | 2006-10-01  | L0004  | 1500000 | 0         |
+------------+------------+---------------+------------------+--------------+-------------+--------+---------+-----------+
4 rows in set (0.086 sec)

MariaDB [pegawai]>
