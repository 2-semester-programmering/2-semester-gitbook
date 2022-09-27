# Databaser I

## Læringsmål

Efter i dag vil du kunne:

* Arbejde med IntelliJ´s databaseværktøj.
* Oprette en database med **CREATE** statement
* Slette en Database med **DROP**
* Oprette en **Tabel** med tilhørende **Kollonner**
* Oprette **Constrains** på en Tabels kollonner
* Indsætte data i tabellen med **INSERT INTO**
* Læse data fra en tabel med **SELECT**
* Bruge **WHERE** i en SELECT statement

## Materiale

* [Oprettelse af en database management server på AZURE](assets/AZURE\_opret\_db.png)
  * **NB: dette har i gjort med Janus i teknikundervisningen**


## Kode fra sql undervisningen 

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

## Øvelser

### Ex1: movie.csv til database tabel

```
	Year;Length;Title;Subject;Popularity;Awards
	1962;138;8 1/2;Drama;80;Yes
	1968;139;2001: A Space Odyssey;Science Fiction;83;No
	1982;92;48 Hrs.;Action;67;No
	1966;95;A Big Hand for the Little Lady;Comedy;12;No
	1992;60;A Certain Sacrifice;Music;24;No
	1962;105;A Child Is Waiting;Drama;60;No
	1985;118;A Chorus Line, The Movie;Music;71;No
	1990;89;A Chorus of Disapproval;Comedy;0;No
	1971;138;A Clockwork Orange;Science Fiction;83;Yes
	1967;100;A Coeur Joie, (Head Over Heels);Action;54;No

```

1. Baseret på csv filen herover skal i lave en database (imdb) med en tabel (movies) som indeholder alle kolonner fra csv filen.
2. Indsæt herefter de 10 film i movies tabellen.
3. Herefter skal i udtrække (SELECT):
	* Alle film i tabellen
	* Title fra alle film
	* Alle info på film fra 1962
	* Alle info på film med en længde over 100 minutter.
	* Tilterne på film fra Science Fiction genren.
	* Info på alle film fra Drama genren som har modtaget en Award.
	* Alle info på den film med højest popularity
		* skal løses vha [SQL MAX Function](https://www.w3schools.com/sql/func_mysql_max.asp) 

### Ex2: Nasa Mars Rover API data

I skal i denne øvelse oprette en database med data svarende til NASA´s mars rover API (et redigeret udsnit herunder):

```
photos": [
	{
		"id": 102693,
		"sol": 1000,
		"camera": "FHAS",
		"img_src": "http://mars.jpl.nasa.gov/msl-raw-images/proj/msl/redops/ods/surface/sol/01000/opgs/edr/fcam/FLB_486265257EDR_F0481570FHAZ00323M_.JPG",
		"earth_date": "2015-05-30",
		"rover": "Curiosity" 
	},
	{
		"id": 102694,
		"sol": 1000,
		"camera": "FHAS",
		"img_src": "http://mars.jpl.nasa.gov/msl-raw-images/proj/msl/redops/ods/surface/sol/01000/opgs/edr/fcam/FRB_486265257EDR_F0481570FHAZ00323M_.JPG",
		"earth_date": "2015-05-30",
		"rover": "Curiosity",
	},
	{
		"id": 102850,
		"sol": 1000,
		"camera": "RHAZ",
		"img_src": "http://mars.jpl.nasa.gov/msl-raw-images/proj/msl/redops/ods/surface/sol/01000/opgs/edr/rcam/RLB_486265291EDR_F0481570RHAZ00323M_.JPG",
		"earth_date": "2015-05-30",
		"rover": "Curiosity",
	},
	{
		"id": 102851,
		"sol": 1000,
		"camera": "RHAZ",
		"img_src": "http://mars.jpl.nasa.gov/msl-raw-images/proj/msl/redops/ods/surface/sol/01000/opgs/edr/rcam/RRB_486265291EDR_F0481570RHAZ00323M_.JPG",
		"earth_date": "2015-05-30",
		"rover": "Curiosity",
	}
] 

```
 
Herefter skal i SELECT:

* url´en til billederne taget af kameraet "FHAS"
* Alt info om billedet med id 102694
* Alt info om alle billeder.
