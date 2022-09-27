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
                         classid int,
                         PRIMARY KEY (id)
    -- FOREIGN KEY (classid) REFERENCES class(id)
);

-- DML
-- INSERT
INSERT INTO student (id, name, email, gender, classid) VALUES (1, 'Anna', 'clbo@kea.dk', 0, 1);

-- SELECT
SELECT * FROM class;
SELECT name, email from student;

-- WHERE
SELECT * FROM student WHERE id = 2;

-- DDL
CREATE TABLE class (
                       id int,
                       person int,
                       class_name varchar(20),
                       PRIMARY KEY (id)
);

-- UPDATE (ALTER)
ALTER TABLE student ADD FOREIGN KEY (classid) REFERENCES class(id);

INSERT INTO class (id, class_name) VALUES (2,'dat22v2');

``` 

