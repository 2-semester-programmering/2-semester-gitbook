
## Læringsmål
Efter i dag vil du kunne:

* Opdatere data i en kolonne vha. SQL´s **UPDATE** statement.
* Slette en kolonne vha. SQL´s **DELETE FROM** sttatement.
* Arbjde med SQL operatore.
* Arbejde med SQL functions.

## Materiale
* [W3School SQL tutorial](https://www.w3schools.com/sql/)

## Kode fra sql undervisningen 

```

CREATE DATABASE clbotest;

USE clbotest;

-- SQL Constraints (NOT NULL, PRIMARY KEY)
CREATE TABLE student (
                         id int NOT NULL,
                         name varchar(50),
                         email varchar(50) unique,
                         gender binary,
                         -- classid int,
                         PRIMARY KEY (id)
    -- FOREIGN KEY (classid) REFERENCES class(id)
);

INSERT INTO student (id, name, email, gender) VALUES (1, 'Claus', 'clbo@kea.dk', 1);
INSERT INTO student (id, name, email, gender) VALUES (4, 'Gerd', 'gerd@kea.dk', 1);
INSERT INTO student (id, name, email, gender) VALUES (5, 'Gerd', 'gerd@kea.dk', 0);



-- UPDATE
UPDATE student SET name='Henning' , email='henn@kea.dk' WHERE id=1;
SELECT * FROM student WHERE id=1;

-- DELETE
DELETE FROM student WHERE id=1;
SELECT * FROM student;


-- AND, OR and NOT Operators
SELECT * FROM student WHERE gender=0 AND name='Gerd';
SELECT * FROM student WHERE name='Claus' OR name = 'Gerd';
SELECT * FROM student WHERE NOT name = 'Claus';

-- ORDER BY
SELECT * FROM student ORDER BY name;
SELECT * FROM student ORDER BY name desc;

-- Functions
-- MIN() and MAX() Functions

SELECT MAX(gender) as maxnam FROM student;
SELECT MIN(gender) as minname FROM student;

-- COUNT(), AVG() and SUM()
SELECT COUNT(*) from student;
SELECT AVG(gender) as avggender FROM student;
SELECT SUM(gender) as sumGender FROM student;

-- LIKE Operator
SELECT * FROM student WHERE name LIKE '%a';

-- IN Operator
SELECT * FROM student WHERE name IN ('Claus', 'Ulla');

-- BETWEEN Operator
SELECT * FROM student WHERE id BETWEEN 2 AND 4;

-- Aliases
SELECT name as nickname FROM student;

-- DDL
-- Auto_increment, Not Null, Unique
CREATE TABLE test (
    id int AUTO_INCREMENT,
    name varchar(20) NOT NULL,
    email varchar(30) UNIQUE,
    PRIMARY KEY (id)
)


```



## Øvelser

### Ex1: Pokedex

Data for this exercise can be found here: https://github.com/2-semester-programmering/dat22v1_assets/blob/main/pokedex.sql

#### Before you start solving the tasks Reflect about:

1. What are the contents of the data-set?
2. What are the semantics (meaning) of the data-set?
3. How can we build a model (java class) that represents each entity? (you do not have to create java classes, just think about it).

#### Exercises:
1. Create a file pokedex.sql and copy/paste the insert statements from github into the file. 
Extend the sql file with a ```` CREATE DATABASE ```` , a ```` USE ```` and a ```` CREATE TABLE ````statement, thus creating a new database and a new table for the data.

2. Insert the data

Build the following views that displays:
* What are all primary types (show a list of the ones in the dataset)
* What are the average defence for all pokemon?
* What are the average hp for (primary) grass types?
* How many pokemon exists pr. primary type?
* How many fire pokemon has higher hp than the average pokemon?
* What primary type are the fastest?





