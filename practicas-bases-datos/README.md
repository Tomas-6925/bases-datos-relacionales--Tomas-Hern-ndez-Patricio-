# Base de Datos UPEM - Gestión de Alumnos

# Práctica: Introducción a Bases de Datos Relacionales
## Datos del alumno
Nombre: TOMAS ALEJANDRO HERNANDEZ PATRICIO
Grupo:7°
Materia: BASES DE DATOS RELACIONALES
Fecha: 02/10/2026

- Requisitos Previos

* **XAMPP** (Servicios de Apache y MySQL activos).
* Acceso a la consola de comandos (`cmd`) o a **phpMyAdmin**.

---

MariaDB [(none)]> CREATE DATABASE upem;
Query OK, 1 row affected (0.004 sec)

MariaDB [(none)]> USE upem;
Database changed
MariaDB [upem]> CREATE TABLE alumnos (id INT PRIMARY KEY,nombre VARCHAR(50),apellido VARCHAR(50),edad INT,semestre ITN);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near ')' at line 1
MariaDB [upem]> CREATE TABLE alumnos (id INT PRIMARY KEY,nombre VARCHAR(50),apellido VARCHAR(50),edad INT,semestre INT);
Query OK, 0 rows affected (0.011 sec)

MariaDB [upem]> INSERT INTO alumnos (id, nombre, apellido, edad, semestre)
    -> VALUES
    -> (1, 'Ana', 'López', 18, 2),
    -> (2, 'Carlos', 'Pérez', 19, 4),
    -> (3, 'María', 'García', 18, 2);
Query OK, 3 rows affected (0.020 sec)
Records: 3  Duplicates: 0  Warnings: 0

MariaDB [upem]> SELECT * FROM alumnos;
+----+--------+----------+------+----------+
| id | nombre | apellido | edad | semestre |
+----+--------+----------+------+----------+
|  1 | Ana    | López    |   18 |        2 |
|  2 | Carlos | Pérez    |   19 |        4 |
|  3 | María  | García   |   18 |        2 |
+----+--------+----------+------+----------+
3 rows in set (0.007 sec)

MariaDB [upem]> SELECT nombre, apellido
    -> FROM alumnos;
+--------+----------+
| nombre | apellido |
+--------+----------+
| Ana    | López    |
| Carlos | Pérez    |
| María  | García   |
+--------+----------+
3 rows in set (0.000 sec)

MariaDB [upem]> SELECT *
    -> FROM alumnos
    -> WHERE semestre = 2;
+----+--------+----------+------+----------+
| id | nombre | apellido | edad | semestre |
+----+--------+----------+------+----------+
|  1 | Ana    | López    |   18 |        2 |
|  3 | María  | García   |   18 |        2 |
+----+--------+----------+------+----------+
2 rows in set (0.004 sec)

MariaDB [upem]> UPDATE alumnos
    -> SET edad = 19
    -> WHERE id = 1;
Query OK, 1 row affected (0.004 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [upem]> SELECT *
    -> FROM alumnos
    -> WHERE id = 1;
+----+--------+----------+------+----------+
| id | nombre | apellido | edad | semestre |
+----+--------+----------+------+----------+
|  1 | Ana    | López    |   19 |        2 |
+----+--------+----------+------+----------+
1 row in set (0.001 sec)

MariaDB [upem]> UPDATE alumnos
    -> SET edad = 20,
    -> semestre = 3
    -> WHERE id = 1;
Query OK, 1 row affected (0.002 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [upem]> SELECT * FROM alumnos;
+----+--------+----------+------+----------+
| id | nombre | apellido | edad | semestre |
+----+--------+----------+------+----------+
|  1 | Ana    | López    |   20 |        3 |
|  2 | Carlos | Pérez    |   19 |        4 |
|  3 | María  | García   |   18 |        2 |
+----+--------+----------+------+----------+
3 rows in set (0.001 sec)

MariaDB [upem]> SELECT * FROM alumnos;
+----+--------+----------+------+----------+
| id | nombre | apellido | edad | semestre |
+----+--------+----------+------+----------+
|  1 | Ana    | López    |   20 |        3 |
|  2 | Carlos | Pérez    |   19 |        4 |
|  3 | María  | García   |   18 |        2 |
+----+--------+----------+------+----------+
3 rows in set (0.001 sec)

MariaDB [upem]> DELETE FROM alumnos
    -> WHERE id = 3;
Query OK, 1 row affected (0.003 sec)

MariaDB [upem]> SELECT * FROM alumnos;
+----+--------+----------+------+----------+
| id | nombre | apellido | edad | semestre |
+----+--------+----------+------+----------+
|  1 | Ana    | López    |   20 |        3 |
|  2 | Carlos | Pérez    |   19 |        4 |
+----+--------+----------+------+----------+
2 rows in set (0.000 sec)

MariaDB [upem]> SELECT * FROM alumnos INTO OUTFILE 'C:/xampp/mysql/data/alumnos.txt';
Query OK, 2 rows affected, 1 warning (0.003 sec)
  
- LOS SIGUIENTES EJERCICIOS TIENEN COMO OBJETIVO CONSULTAR, INSERTAR Y MODIFICAR EN LAS BASES DE DATOS, MOSTRANDO HERRORES QUE ME PERMITIERON OBTENER NOCION Y CONOCIMIENTO ATRAVES DE LA PRUEBA Y ERROR:


C:\xampp\mysql\bin>CREATE DATABASE biblioteca;
"CREATE" no se reconoce como un comando interno o externo,
programa o archivo por lotes ejecutable.

C:\xampp\mysql\bin>mysql -u root -h localhost -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> CREATE DATABASE biblioteca;
Query OK, 1 row affected (0.002 sec)

MariaDB [(none)]> USE biblioteca;
Database changed
MariaDB [biblioteca]> CREATE TABLE libros Bye
Ctrl-C -- exit!

C:\xampp\mysql\bin>mysql -u root -h localhost -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 10
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> USE biblioteca;
Database changed
MariaDB [biblioteca]> CREATE TABLE libros(id INT PRYMARY KEY,titulo VARCHAR(50),autor VARCHAR(50),año INT,categoria INT);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'KEY,titulo VARCHAR(50),autor VARCHAR(50),año INT,categoria INT)' at line 1
MariaDB [biblioteca]> CREATE TABLE libros (id INT PRIMARY KEY,titulo VARCHAR(50),autor VARCHAR(50),año INT,categoria INT);
Query OK, 0 rows affected (0.012 sec)

MariaDB [biblioteca]> ALTER TABLE libros MODIFY COLUMN categoria VARCHAR(50);
Query OK, 0 rows affected (0.038 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [biblioteca]> INSERT INTO libros (id,titulo,autor,año,categoria)VALUES(1,'Don Quijote de la Mancha','Miguel de Cervantes',1605,Novela Clásica),(2,'Cien años de soledad','Gabriel Garcia Márquez',1967,Realismo clasico),(3,'1984','George Orwell',1949,Ciencia Ficcion politica),(4,'Madame Bovary','Gustave Flaubert',1857,Realismo),(5,'Crimen y Castigo','Fiódor Dostoievski',1866,Novela psicológica);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'Clásica),(2,'Cien años de soledad','Gabriel Garcia Márquez',1967,Realismo ...' at line 1
MariaDB [biblioteca]> USE libros;
ERROR 1049 (42000): Unknown database 'libros'
MariaDB [biblioteca]> INSERT INTO libros (id,titulo,autor,año,categoria) VALUES (1,'Don Quijote de la Mancha','Miguel de Cervantes',1605,Novela Clásica),(2,'Cien años de soledad','Gabriel Garcia Márquez',1967,Realismo clasico),(3,'1984','George Orwell',1949,Ciencia Ficcion politica),(4,'Madame Bovary','Gustave Flaubert',1857,Realismo),(5,'Crimen y Castigo','Fiódor Dostoievski',1866,Novela psicológica);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'Clásica),(2,'Cien años de soledad','Gabriel Garcia Márquez',1967,Realismo ...' at line 1
MariaDB [biblioteca]> INSERT INTO libros (id,titulo,autor,año,categoria)VALUES(1,'Don Quijote de la Mancha','Miguel de Cervantes',1605,'Novela Clásica'),(2,'Cien años de soledad','Gabriel Garcia Márquez',1967,'Realismo clasico'),(3,'1984','George Orwell',1949,'Ciencia Ficcion politica'),(4,'Madame Bovary','Gustave Flaubert',1857,'Realismo'),(5,'Crimen y Castigo','Fiódor Dostoievski',1866,'Novela psicológica');
Query OK, 5 rows affected (0.003 sec)
Records: 5  Duplicates: 0  Warnings: 0

MariaDB [biblioteca]> SELECT * ALUMNOS;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'ALUMNOS' at line 1
MariaDB [biblioteca]> SELECT * libros;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'libros' at line 1
MariaDB [biblioteca]> SELECT * FROM libros;
+----+--------------------------+------------------------+------+--------------------------+
| id | titulo                   | autor                  | año  | categoria                |
+----+--------------------------+------------------------+------+--------------------------+
|  1 | Don Quijote de la Mancha | Miguel de Cervantes    | 1605 | Novela Clásica           |
|  2 | Cien años de soledad     | Gabriel Garcia Márquez | 1967 | Realismo clasico         |
|  3 | 1984                     | George Orwell          | 1949 | Ciencia Ficcion politica |
|  4 | Madame Bovary            | Gustave Flaubert       | 1857 | Realismo                 |
|  5 | Crimen y Castigo         | Fiódor Dostoievski     | 1866 | Novela psicológica       |
+----+--------------------------+------------------------+------+--------------------------+
5 rows in set (0.001 sec)

MariaDB [biblioteca]> SELECT titulo,autor From libros;
+--------------------------+------------------------+
| titulo                   | autor                  |
+--------------------------+------------------------+
| Don Quijote de la Mancha | Miguel de Cervantes    |
| Cien años de soledad     | Gabriel Garcia Márquez |
| 1984                     | George Orwell          |
| Madame Bovary            | Gustave Flaubert       |
| Crimen y Castigo         | Fiódor Dostoievski     |
+--------------------------+------------------------+
5 rows in set (0.001 sec)

MariaDB [biblioteca]> SELECT * FROM libros WHERE año = 1900;
Empty set (0.001 sec)

MariaDB [biblioteca]> SELECT * FROM libros WHERE año => 1900;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '> 1900' at line 1
MariaDB [biblioteca]> SELECT * FROM libros WHERE año > 1900;
+----+----------------------+------------------------+------+--------------------------+
| id | titulo               | autor                  | año  | categoria                |
+----+----------------------+------------------------+------+--------------------------+
|  2 | Cien años de soledad | Gabriel Garcia Márquez | 1967 | Realismo clasico         |
|  3 | 1984                 | George Orwell          | 1949 | Ciencia Ficcion politica |
+----+----------------------+------------------------+------+--------------------------+
2 rows in set (0.001 sec)

MariaDB [biblioteca]> UPDATE libros SET año = 1950;
Query OK, 5 rows affected (0.004 sec)
Rows matched: 5  Changed: 5  Warnings: 0

MariaDB [biblioteca]> SELECT FROM libros;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'FROM libros' at line 1
MariaDB [biblioteca]> SELECT * FROM libros;
+----+--------------------------+------------------------+------+--------------------------+
| id | titulo                   | autor                  | año  | categoria                |
+----+--------------------------+------------------------+------+--------------------------+
|  1 | Don Quijote de la Mancha | Miguel de Cervantes    | 1950 | Novela Clásica           |
|  2 | Cien años de soledad     | Gabriel Garcia Márquez | 1950 | Realismo clasico         |
|  3 | 1984                     | George Orwell          | 1950 | Ciencia Ficcion politica |
|  4 | Madame Bovary            | Gustave Flaubert       | 1950 | Realismo                 |
|  5 | Crimen y Castigo         | Fiódor Dostoievski     | 1950 | Novela psicológica       |
+----+--------------------------+------------------------+------+--------------------------+
5 rows in set (0.000 sec)

MariaDB [biblioteca]> UPDATE libros SET año = 1967 WERE id = 2;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'WERE id = 2' at line 1
MariaDB [biblioteca]> DELETE FROM libros WHERE id 5;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '5' at line 1
MariaDB [biblioteca]> DELETE FROM libros WHERE id = 5;
Query OK, 1 row affected (0.003 sec)

MariaDB [biblioteca]> SELECT * FROM libros;
+----+--------------------------+------------------------+------+--------------------------+
| id | titulo                   | autor                  | año  | categoria                |
+----+--------------------------+------------------------+------+--------------------------+
|  1 | Don Quijote de la Mancha | Miguel de Cervantes    | 1950 | Novela Clásica           |
|  2 | Cien años de soledad     | Gabriel Garcia Márquez | 1950 | Realismo clasico         |
|  3 | 1984                     | George Orwell          | 1950 | Ciencia Ficcion politica |
|  4 | Madame Bovary            | Gustave Flaubert       | 1950 | Realismo                 |
+----+--------------------------+------------------------+------+--------------------------+
4 rows in set (0.001 sec)

MariaDB [biblioteca]> SELECT * FROM alumnos INTO OUTFILE 'C:/xampp/mysql/data/libros.txt';
ERROR 1146 (42S02): Table 'biblioteca.alumnos' doesn't exist
MariaDB [biblioteca]> SELECT * FROM alumnos INTO OUTFILE 'C:/xampp/mysql/data/biblioteca.txt';
ERROR 1146 (42S02): Table 'biblioteca.alumnos' doesn't exist
MariaDB [biblioteca]> SELECT * FROM biblioteca INTO OUTFILE 'C:/xampp/mysql/data/libros.txt';
ERROR 1146 (42S02): Table 'biblioteca.biblioteca' doesn't exist
MariaDB [biblioteca]> SELECT * FROM libros INTO OUTFILE 'C:/xampp/mysql/data/libros.txt';
Query OK, 4 rows affected, 1 warning (0.002 sec)

MariaDB [biblioteca]> exit
Bye

C:\xampp\mysql\bin>mysql -u root -h localhost -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 11
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> CREATE DATABASE tienda;
Query OK, 1 row affected (0.012 sec)

MariaDB [(none)]> USE tienda;
Database changed
MariaDB [tienda]> CREATE TABLE productos (id INT PRIMARY KEY,nombre del producto VARCHAR(50),categoria deL producto VARCHAR(50),precio del producto INT, producto existente INT);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'producto VARCHAR(50),categoria deL producto VARCHAR(50),precio del producto I...' at line 1
MariaDB [tienda]> CREATE TABLE productos (id INT PRIMARY KEY,nombre del producto VARCHAR(50),categoria VARCHAR(50),precio INT, P_existente INT);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'producto VARCHAR(50),categoria VARCHAR(50),precio INT, P_existente INT)' at line 1
MariaDB [tienda]> CREATE TABLE productos (id INT PRIMARY KEY,nombre VARCHAR(50),categoria VARCHAR(50),precio INT,existencia INT);
Query OK, 0 rows affected (0.032 sec)

MariaDB [tienda]> INSERT INTO productos (id,nombre,categoria,precio,existencia) VALUES (1,'COCACOLA 600 ML','BEBIDAS',25,30),(2,'TONALLAN 300 ML','VINOS Y LICORES',30,10),(3,'CREMA CORPORAL 200 G','FARMACIA',85,12),(4,'TALCO PARA PIES 150 G','FARMACIA',63,8),(5,'REFRIGERADOR MABE','ELECTRODOMESTICOS',12560,4),(6,'HORNO DE MICRO HONDAS','ELECTRODOMESTICOS',3245,5);
Query OK, 6 rows affected (0.013 sec)
Records: 6  Duplicates: 0  Warnings: 0

MariaDB [tienda]> SELECT * FROM productos;
+----+-----------------------+-------------------+--------+------------+
| id | nombre                | categoria         | precio | existencia |
+----+-----------------------+-------------------+--------+------------+
|  1 | COCACOLA 600 ML       | BEBIDAS           |     25 |         30 |
|  2 | TONALLAN 300 ML       | VINOS Y LICORES   |     30 |         10 |
|  3 | CREMA CORPORAL 200 G  | FARMACIA          |     85 |         12 |
|  4 | TALCO PARA PIES 150 G | FARMACIA          |     63 |          8 |
|  5 | REFRIGERADOR MABE     | ELECTRODOMESTICOS |  12560 |          4 |
|  6 | HORNO DE MICRO HONDAS | ELECTRODOMESTICOS |   3245 |          5 |
+----+-----------------------+-------------------+--------+------------+
6 rows in set (0.076 sec)

MariaDB [tienda]> SELECT nombre,precio * FROM productos;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'FROM productos' at line 1
MariaDB [tienda]> SELECT nombre,precio FROM productos;
+-----------------------+--------+
| nombre                | precio |
+-----------------------+--------+
| COCACOLA 600 ML       |     25 |
| TONALLAN 300 ML       |     30 |
| CREMA CORPORAL 200 G  |     85 |
| TALCO PARA PIES 150 G |     63 |
| REFRIGERADOR MABE     |  12560 |
| HORNO DE MICRO HONDAS |   3245 |
+-----------------------+--------+
6 rows in set (0.001 sec)

MariaDB [tienda]> SELECT * FROM productos WHERE precio >85;
+----+-----------------------+-------------------+--------+------------+
| id | nombre                | categoria         | precio | existencia |
+----+-----------------------+-------------------+--------+------------+
|  5 | REFRIGERADOR MABE     | ELECTRODOMESTICOS |  12560 |          4 |
|  6 | HORNO DE MICRO HONDAS | ELECTRODOMESTICOS |   3245 |          5 |
+----+-----------------------+-------------------+--------+------------+
2 rows in set (0.007 sec)

MariaDB [tienda]> UPDATE productos SET precio = 12000 WERE id = 5;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'WERE id = 5' at line 1
MariaDB [tienda]> UPDATE productos SET precio = 12000 WHERE id = 5;
Query OK, 1 row affected (0.008 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [tienda]> SELECT * FROM productos;
+----+-----------------------+-------------------+--------+------------+
| id | nombre                | categoria         | precio | existencia |
+----+-----------------------+-------------------+--------+------------+
|  1 | COCACOLA 600 ML       | BEBIDAS           |     25 |         30 |
|  2 | TONALLAN 300 ML       | VINOS Y LICORES   |     30 |         10 |
|  3 | CREMA CORPORAL 200 G  | FARMACIA          |     85 |         12 |
|  4 | TALCO PARA PIES 150 G | FARMACIA          |     63 |          8 |
|  5 | REFRIGERADOR MABE     | ELECTRODOMESTICOS |  12000 |          4 |
|  6 | HORNO DE MICRO HONDAS | ELECTRODOMESTICOS |   3245 |          5 |
+----+-----------------------+-------------------+--------+------------+
6 rows in set (0.001 sec)

MariaDB [tienda]> UPDATE productos SET existencia = 50 WHERE id = 1;
Query OK, 1 row affected (0.004 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [tienda]> DELETE FROM productos WHERE id = 4;
Query OK, 1 row affected (0.005 sec)

MariaDB [tienda]> SELECT * FROM productos;
+----+-----------------------+-------------------+--------+------------+
| id | nombre                | categoria         | precio | existencia |
+----+-----------------------+-------------------+--------+------------+
|  1 | COCACOLA 600 ML       | BEBIDAS           |     25 |         50 |
|  2 | TONALLAN 300 ML       | VINOS Y LICORES   |     30 |         10 |
|  3 | CREMA CORPORAL 200 G  | FARMACIA          |     85 |         12 |
|  5 | REFRIGERADOR MABE     | ELECTRODOMESTICOS |  12000 |          4 |
|  6 | HORNO DE MICRO HONDAS | ELECTRODOMESTICOS |   3245 |          5 |
+----+-----------------------+-------------------+--------+------------+
5 rows in set (0.001 sec)

MariaDB [tienda]> exit
Bye

C:\xampp\mysql\bin>mysql -u root -h localhost -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 12
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> CREATE DATABASE videojuegos;
Query OK, 1 row affected (0.005 sec)

MariaDB [(none)]> USE videojuegos;
Database changed
MariaDB [videojuegos]> CREATE TABLE juegos;
ERROR 1113 (42000): A table must have at least 1 column
MariaDB [videojuegos]> CREATE TABLE juegos (id INT PRIMARY KEY,titulo VARCHAR(50),género VARCHAR(50),plataforma VARCHAR(50),año INT);
Query OK, 0 rows affected (0.014 sec)

MariaDB [videojuegos]> INSER INTO (id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATAFORMAS','NAVEGADOR_MÓVIL',2026),(2,'PUTTY WORLD','PLATAFORMAS','NINTENDO SWITCH2',2027),(3,'METROID RAVENOUS','AVENTURA Y ACCIÓN','NINTENDO SWITCH 2',2027),(4,'WARCRAFT III ','ESTRATEGIA EN TIEMPO REAL','PC_MAC',2026),(5,'MARVELS WOLVERINE','AVENTURA Y ACCIÓN','PS5',2026),(6,'ONIMUSHA:WAY OF THE SWORD','MUNDO ABIERTO','PS5_XSX_PC_SWITCH 2'2026),(7,THE BLOOD OF DAWNWALKER,'MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 FIRST LIGHT','SHOOTER EN TERCERA PERSONA','PS5_XSX_PC_SWITCH 2',2026);
ERROR 2006 (HY000): MySQL server has gone away
No connection. Trying to reconnect...
Connection id:    13
Current database: videojuegos

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'INSER INTO (id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATA...' at line 1
MariaDB [videojuegos]> EXIT
Bye

C:\xampp\mysql\bin>mysql -u root -h localhost -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 8
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> USE videojuegos
Database changed
MariaDB [videojuegos]>  INSER INTO (id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATAFORMAS','NAVEGADOR_MÓVIL',2026),(2,'PUTTY WORLD','PLATAFORMAS','NINTENDO SWITCH2',2027),(3,'METROID RAVENOUS','AVENTURA Y ACCIÓN','NINTENDO SWITCH 2',2027),(4,'WARCRAFT III ','ESTRATEGIA EN TIEMPO REAL','PC_MAC',2026),(5,'MARVELS WOLVERINE','AVENTURA Y ACCIÓN','PS5',2026),(6,'ONIMUSHA:WAY OF THE SWORD','MUNDO ABIERTO','PS5_XSX_PC_SWITCH 2'2026),(7,THE BLOOD OF DAWNWALKER,'MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 FIRST LIGHT','SHOOTER EN TERCERA PERSONA','PS5_XSX_PC_SWITCH 2',2026);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'INSER INTO (id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATA...' at line 1
MariaDB [videojuegos]>  INSERT INTO (id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATAFORMAS','NAVEGADOR_MÓVIL',2026),(2,'PUTTY WORLD','PLATAFORMAS','NINTENDO SWITCH2',2027),(3,'METROID RAVENOUS','AVENTURA Y ACCIÓN','NINTENDO SWITCH 2',2027),(4,'WARCRAFT III ','ESTRATEGIA EN TIEMPO REAL','PC_MAC',2026),(5,'MARVELS WOLVERINE','AVENTURA Y ACCIÓN','PS5',2026),(6,'ONIMUSHA:WAY OF THE SWORD','MUNDO ABIERTO','PS5_XSX_PC_SWITCH 2'2026),(7,THE BLOOD OF DAWNWALKER,'MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 FIRST LIGHT','SHOOTER EN TERCERA PERSONA','PS5_XSX_PC_SWITCH 2',2026);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '(id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATAFORMAS','NA...' at line 1
MariaDB [videojuegos]>  INSERT INTO juegos (id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATAFORMAS','NAVEGADOR_MÓVIL',2026),(2,'PUTTY WORLD','PLATAFORMAS','NINTENDO SWITCH2',2027),(3,'METROID RAVENOUS','AVENTURA Y ACCIÓN','NINTENDO SWITCH 2',2027),(4,'WARCRAFT III ','ESTRATEGIA EN TIEMPO REAL','PC_MAC',2026),(5,'MARVELS WOLVERINE','AVENTURA Y ACCIÓN','PS5',2026),(6,'ONIMUSHA:WAY OF THE SWORD','MUNDO ABIERTO','PS5_XSX_PC_SWITCH 2'2026),(7,THE BLOOD OF DAWNWALKER,'MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 FIRST LIGHT','SHOOTER EN TERCERA PERSONA','PS5_XSX_PC_SWITCH 2',2026);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '2026),(7,THE BLOOD OF DAWNWALKER,'MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 F...' at line 1
MariaDB [videojuegos]>  INSERT INTO juegos (id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATAFORMAS','NAVEGADOR_MÓVIL',2026),(2,'PUTTY WORLD','PLATAFORMAS','NINTENDO SWITCH2',2027),(3,'METROID RAVENOUS','AVENTURA Y ACCIÓN','NINTENDO SWITCH 2',2027),(4,'WARCRAFT III ','ESTRATEGIA EN TIEMPO REAL','PC_MAC',2026),(5,'MARVELS WOLVERINE','AVENTURA Y ACCIÓN','PS5',2026),(6,'ONIMUSHA:WAY OF THE SWORD','MUNDO ABIERTO','PS5_XSX_PC_SWITCH 2',2026),(7,THE BLOOD OF DAWNWALKER,'MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 FIRST LIGHT','SHOOTER EN TERCERA PERSONA','PS5_XSX_PC_SWITCH 2',2026);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'BLOOD OF DAWNWALKER,'MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 FIRST LIGHT','...' at line 1
MariaDB [videojuegos]>  INSERT INTO juegos (id,titulo,genero,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATAFORMAS','NAVEGADOR_MÓVIL',2026),(2,'PUTTY WORLD','PLATAFORMAS','NINTENDO SWITCH2',2027),(3,'METROID RAVENOUS','AVENTURA Y ACCIÓN','NINTENDO SWITCH 2',2027),(4,'WARCRAFT III ','ESTRATEGIA EN TIEMPO REAL','PC_MAC',2026),(5,'MARVELS WOLVERINE','AVENTURA Y ACCIÓN','PS5',2026),(6,'ONIMUSHA:WAY OF THE SWORD','MUNDO ABIERTO','PS5_XSX_PC_SWITCH 2',2026),(7,'THE BLOOD OF DAWNWALKER','MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 FIRST LIGHT','SHOOTER EN TERCERA PERSONA','PS5_XSX_PC_SWITCH 2',2026);
ERROR 1054 (42S22): Unknown column 'genero' in 'field list'
MariaDB [videojuegos]>  INSERT INTO juegos (id,titulo,género,plataforma,año) VALUES (1,'HAPPY WHEELS','PLATAFORMAS','NAVEGADOR_MÓVIL',2026),(2,'PUTTY WORLD','PLATAFORMAS','NINTENDO SWITCH2',2027),(3,'METROID RAVENOUS','AVENTURA Y ACCIÓN','NINTENDO SWITCH 2',2027),(4,'WARCRAFT III ','ESTRATEGIA EN TIEMPO REAL','PC_MAC',2026),(5,'MARVELS WOLVERINE','AVENTURA Y ACCIÓN','PS5',2026),(6,'ONIMUSHA:WAY OF THE SWORD','MUNDO ABIERTO','PS5_XSX_PC_SWITCH 2',2026),(7,'THE BLOOD OF DAWNWALKER','MUNDO ABIERTO','PS5_XSX_PC',2026),(8,'007 FIRST LIGHT','SHOOTER EN TERCERA PERSONA','PS5_XSX_PC_SWITCH 2',2026);
Query OK, 8 rows affected (0.005 sec)
Records: 8  Duplicates: 0  Warnings: 0

MariaDB [videojuegos]> SELECT * FROM videojuegos;
ERROR 1146 (42S02): Table 'videojuegos.videojuegos' doesn't exist
MariaDB [videojuegos]> SELECT * FROM juegos;
+----+---------------------------+----------------------------+---------------------+------+
| id | titulo                    | género                     | plataforma          | año  |
+----+---------------------------+----------------------------+---------------------+------+
|  1 | HAPPY WHEELS              | PLATAFORMAS                | NAVEGADOR_MÓVIL     | 2026 |
|  2 | PUTTY WORLD               | PLATAFORMAS                | NINTENDO SWITCH2    | 2027 |
|  3 | METROID RAVENOUS          | AVENTURA Y ACCIÓN          | NINTENDO SWITCH 2   | 2027 |
|  4 | WARCRAFT III              | ESTRATEGIA EN TIEMPO REAL  | PC_MAC              | 2026 |
|  5 | MARVELS WOLVERINE         | AVENTURA Y ACCIÓN          | PS5                 | 2026 |
|  6 | ONIMUSHA:WAY OF THE SWORD | MUNDO ABIERTO              | PS5_XSX_PC_SWITCH 2 | 2026 |
|  7 | THE BLOOD OF DAWNWALKER   | MUNDO ABIERTO              | PS5_XSX_PC          | 2026 |
|  8 | 007 FIRST LIGHT           | SHOOTER EN TERCERA PERSONA | PS5_XSX_PC_SWITCH 2 | 2026 |
+----+---------------------------+----------------------------+---------------------+------+
8 rows in set (0.001 sec)

MariaDB [videojuegos]> SELECT * FROM titulo, plataforma FROM juegos;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'FROM juegos' at line 1
MariaDB [videojuegos]> SELECT titulo, plataforma FROM juegos;
+---------------------------+---------------------+
| titulo                    | plataforma          |
+---------------------------+---------------------+
| HAPPY WHEELS              | NAVEGADOR_MÓVIL     |
| PUTTY WORLD               | NINTENDO SWITCH2    |
| METROID RAVENOUS          | NINTENDO SWITCH 2   |
| WARCRAFT III              | PC_MAC              |
| MARVELS WOLVERINE         | PS5                 |
| ONIMUSHA:WAY OF THE SWORD | PS5_XSX_PC_SWITCH 2 |
| THE BLOOD OF DAWNWALKER   | PS5_XSX_PC          |
| 007 FIRST LIGHT           | PS5_XSX_PC_SWITCH 2 |
+---------------------------+---------------------+
8 rows in set (0.001 sec)

MariaDB [videojuegos]> SELECT plataforma = PS5 FROM JUEGOS
    -> ;
ERROR 1054 (42S22): Unknown column 'PS5' in 'field list'
MariaDB [videojuegos]> SELECT plataforma = PS5 FROM juegos;
ERROR 1054 (42S22): Unknown column 'PS5' in 'field list'
MariaDB [videojuegos]> SELECT plataforma = PC_MAC FROM juegos;
ERROR 1054 (42S22): Unknown column 'PC_MAC' in 'field list'
MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = PS5;
ERROR 1054 (42S22): Unknown column 'PS5' in 'where clause'
MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = 5;
Empty set, 8 warnings (0.004 sec)

MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = P;
ERROR 1054 (42S22): Unknown column 'P' in 'where clause'
MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = 2;
Empty set, 8 warnings (0.001 sec)

MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = NINTENDO SWITCH 2;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'SWITCH 2' at line 1
MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = 5 ;
Empty set, 8 warnings (0.001 sec)

MariaDB [videojuegos]> SELECT  FROM juegos WHERE plataforma = 'PS5' ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'FROM juegos WHERE plataforma = 'PS5'' at line 1
MariaDB [videojuegos]> SELECT titulo FROM juegos WHERE plataforma = 'PS5';
+-------------------+
| titulo            |
+-------------------+
| MARVELS WOLVERINE |
+-------------------+
1 row in set (0.003 sec)

MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = 'XSX';
Empty set (0.001 sec)

MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = 'PC';
Empty set (0.001 sec)

MariaDB [videojuegos]> SELECT * FROM juegos WHERE plataforma = 'NINTENDO SWITCH 2';
+----+------------------+-------------------+-------------------+------+
| id | titulo           | género            | plataforma        | año  |
+----+------------------+-------------------+-------------------+------+
|  3 | METROID RAVENOUS | AVENTURA Y ACCIÓN | NINTENDO SWITCH 2 | 2027 |
+----+------------------+-------------------+-------------------+------+
1 row in set (0.001 sec)

MariaDB [videojuegos]> SELECT * FROM juegos WHERE año > 2026;
+----+------------------+-------------------+-------------------+------+
| id | titulo           | género            | plataforma        | año  |
+----+------------------+-------------------+-------------------+------+
|  2 | PUTTY WORLD      | PLATAFORMAS       | NINTENDO SWITCH2  | 2027 |
|  3 | METROID RAVENOUS | AVENTURA Y ACCIÓN | NINTENDO SWITCH 2 | 2027 |
+----+------------------+-------------------+-------------------+------+
2 rows in set (0.001 sec)

MariaDB [videojuegos]> UPDATE juegos SET género = MULTIPLATAFORMAS WHERE id = 2;
ERROR 1054 (42S22): Unknown column 'MULTIPLATAFORMAS' in 'field list'
MariaDB [videojuegos]> UPDATE juegos SET género = 'MULTIPLATAFORMA' WHERE id = 2;
Query OK, 1 row affected (0.004 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [videojuegos]> UPDATE juegos SET año = 2025 WHERE id = 2;
Query OK, 1 row affected (0.004 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [videojuegos]> DELETE FROM juegos WHERE id = 8;
Query OK, 1 row affected (0.005 sec)

MariaDB [videojuegos]> SELECT * FROM juegos;
+----+---------------------------+---------------------------+---------------------+------+
| id | titulo                    | género                    | plataforma          | año  |
+----+---------------------------+---------------------------+---------------------+------+
|  1 | HAPPY WHEELS              | PLATAFORMAS               | NAVEGADOR_MÓVIL     | 2026 |
|  2 | PUTTY WORLD               | MULTIPLATAFORMA           | NINTENDO SWITCH2    | 2025 |
|  3 | METROID RAVENOUS          | AVENTURA Y ACCIÓN         | NINTENDO SWITCH 2   | 2027 |
|  4 | WARCRAFT III              | ESTRATEGIA EN TIEMPO REAL | PC_MAC              | 2026 |
|  5 | MARVELS WOLVERINE         | AVENTURA Y ACCIÓN         | PS5                 | 2026 |
|  6 | ONIMUSHA:WAY OF THE SWORD | MUNDO ABIERTO             | PS5_XSX_PC_SWITCH 2 | 2026 |
|  7 | THE BLOOD OF DAWNWALKER   | MUNDO ABIERTO             | PS5_XSX_PC          | 2026 |
+----+---------------------------+---------------------------+---------------------+------+
7 rows in set (0.001 sec)

