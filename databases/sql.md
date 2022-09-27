# Kode fra sql undervisningen 

```
-- Create DB
CREATE DATABASE clbotest;
CREATE DATABASE clbotest_2;

-- Drop (DELETE) DB
DROP DATABASE clbotest_2;

-- USE DB
USE clbotest;

-- Create Table
CREATE TABLE student (
	 id int,
	 name varchar(50),
	 email varchar(50),
	 gender binary
);

-- Drop (delete) table
DROP TABLE student;
DROP TABLE class;

-- SQL Constraints (NOT NULL, PRIMARY KEY)
CREATE TABLE student (
	 id int NOT NULL,
	 name varchar(50),
	 email varchar(50),
	 gender binary,
	 PRIMARY KEY (id)
);

-- DML
-- INSERT
INSERT INTO student (id, name, email, gender) VALUES (1, 'Anna', 'anna@kea.dk', 0);
INSERT INTO student (id, name, email, gender) VALUES (2, 'Claus', 'clbo@kea.dk', 1);

-- SELECT
SELECT * FROM student;
SELECT name, email from student;

-- WHERE
SELECT * FROM student WHERE id = 2;


``` 

