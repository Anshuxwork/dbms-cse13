Microsoft Windows [Version 10.0.26200.7623]
(c) Microsoft Corporation. All rights reserved.

C:\Users\Lenovo>cd ..

C:\Users>cd ..

C:\>cd xampp

C:\xampp>cd mysql

C:\xampp\mysql>cd bin

C:\xampp\mysql\bin>mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
5 rows in set (0.052 sec)

MariaDB [(none)]> CREATE DATABASE iilm;
Query OK, 1 row affected (0.002 sec)

MariaDB [(none)]> USE iilm;
Database changed
MariaDB [iilm]> SHOW TABLES;
Empty set (0.001 sec)

MariaDB [iilm]> CREATE TABLE Student (
    ->     student_id INT PRIMARY KEY,
    ->     first_name VARCHAR(50) NOT NULL,
    ->     last_name VARCHAR(50) NOT NULL,
    ->     email VARCHAR(100) UNIQUE NOT NULL,
    ->     dob DATE NOT NULL,
    ->     course VARCHAR(50) NOT NULL,
    ->     fees DECIMAL(8,2) CHECK (fees > 0)
    -> );
Query OK, 0 rows affected (0.057 sec)

MariaDB [iilm]> SHOW Tables;
+----------------+
| Tables_in_iilm |
+----------------+
| student        |
+----------------+
1 row in set (0.002 sec)

MariaDB [iilm]> Describe student;
+------------+--------------+------+-----+---------+-------+
| Field      | Type         | Null | Key | Default | Extra |
+------------+--------------+------+-----+---------+-------+
| student_id | int(11)      | NO   | PRI | NULL    |       |
| first_name | varchar(50)  | NO   |     | NULL    |       |
| last_name  | varchar(50)  | NO   |     | NULL    |       |
| email      | varchar(100) | NO   | UNI | NULL    |       |
| dob        | date         | NO   |     | NULL    |       |
| course     | varchar(50)  | NO   |     | NULL    |       |
| fees       | decimal(8,2) | YES  |     | NULL    |       |
+------------+--------------+------+-----+---------+-------+
7 rows in set (0.050 sec)

MariaDB [iilm]> INSERT INTO student
    -> VALUES (1, 'Anshu' , 'Rana' , 'anshu@gmail.com', '2007-04-10', 'BTech', 2000000);
Query OK, 1 row affected, 1 warning (0.082 sec)

MariaDB [iilm]> SELECT * FROM student_details;
ERROR 1146 (42S02): Table 'iilm.student_details' doesn't exist
MariaDB [iilm]> INSERT INTO student
    -> VALUES (1, 'Anshu' , 'Rana' , 'anshu@gmail.com', '2007-04-10', 'BTech', 2000000);
ERROR 1062 (23000): Duplicate entry '1' for key 'PRIMARY'
MariaDB [iilm]> INSERT INTO student
    -> VALUES (2, 'Vaishnav ', 'Verma', 'Vaishnav@iilm.edu', '2005-01-07', ' BTech', 400000);
Query OK, 1 row affected (0.033 sec)

MariaDB [iilm]> SELEct * FROM students;
ERROR 1146 (42S02): Table 'iilm.students' doesn't exist
MariaDB [iilm]> INSERT INTO student
    -> VALUEs ( 3, 'saniya' ,'parveen', 'saniya@gmail.com', '2006-02-14','BBA', 100000);
Query OK, 1 row affected (0.033 sec)

MariaDB [iilm]> SELECT * FROM student;
+------------+------------+-----------+-------------------+------------+--------+-----------+
| student_id | first_name | last_name | email             | dob        | course | fees      |
+------------+------------+-----------+-------------------+------------+--------+-----------+
|          1 | Anshu      | Rana      | anshu@gmail.com   | 2007-04-10 | BTech  | 999999.99 |
|          2 | Vaishnav   | Verma     | Vaishnav@iilm.edu | 2005-01-07 |  BTech | 400000.00 |
|          3 | saniya     | parveen   | saniya@gmail.com  | 2006-02-14 | BBA    | 100000.00 |
+------------+------------+-----------+-------------------+------------+--------+-----------+
3 rows in set (0.001 sec)

MariaDB [iilm]> ^D^ECtrl-C -- exit!