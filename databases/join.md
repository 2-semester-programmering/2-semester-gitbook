
## Læringsmål
* Forstå og arbejde med Primary/Foreign key relationer
 
## Materiale

## Kode fra sql undervisningen 

```
CREATE DATABASE IF NOT EXISTS shop;
USE shop;
DROP TABLE IF EXISTS customer;

CREATE TABLE customer(
    custId int AUTO_INCREMENT,
    firstname varchar(50),
    lastname varchar(50),
    email varchar(50),
    PRIMARY KEY (custId)
);

DROP TABLE IF EXISTS customer;

CREATE TABLE order(
    orderId int auto_increment,
    date date,
    quantity int,
    custId int not null,
    PRIMARY KEY (orderId)
    FOREIGN KEY (custId)
);

```



## Øvelser
