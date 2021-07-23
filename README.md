# General info
This is the repository for the course of fundamentals of Data Bases with Platzi, here you will see what I consider to be the most used topics and some examples.

## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)
* [Summary](#summary)
* [Relational_DB](#relational_db)
* [Non-Relational_DB](#non-relational_db)
* [Normalize](#normalize)
> * [No-Normalize](#no-normalize)
> * [1FN](#1FN)
> * [2FN](#2FN)
> * [3FN](#3FN)
> * [4FN](#4FN)
* [BASICS_COMMANDS](#basics_commands)
> * [DDL](#ddl)
> > * [CREATE](#create)
> > * [ALTER](#alter)
> > * [DROP](#drop)
> * [DML](#dml)
> > * [INSERT](#insert)
> * [SELECT](#select)
> * [QUERY](#query)
> [JOINS](#joins)
> * [LEFT_JOIN](#left_join)

## Technologies
Project is created with:
* MYSQL server 8.0.25
> * My SQL Wrokbench 8.0.14

	
## Setup
To prepre your work you first need to donload the next program [MySQL](https://dev.mysql.com/downloads/windows/installer/5.6.html) and select the custom installation. Then install MySQL server there sould only show 1 option and in application select workbench and select also the only opcion that should show and install those.

## Summary
In this course talk about the two kinds of data bases (from now on I will just reference as DB), how to normalize them to make it more it more understendable and easy to program later on,

## Relational_DB
> Also know as **Relational**

## Non-Relational_DB
> Also know as not **Non-Relational**


## Normalize
This is the process to make the structure of the DB better to implement when you are programming

### Not-Normalize
So this is a very basic form to express a database that can and must be modify to make a good DB

### 1FN
In this form you should eliminate the repeat values or the not atomic ones.
* It is atomic when all the atributes are atomic
* It does not have any variation in the number of columns
* There must exist and independency int the order between the rows and the columns

### 2FN
In this form it helps to differenciate the data from the entities
* Be already in [1FN](#1FN)
* It should not exist parcial dependecys
* All the atributes that are not the **Primary key** must depend only ont the **Primary key**

### 3F
In this form help us to separate conceptually the entities that are not dependencys
* Be on [2FN](#2FN)
* There is no functinoal dependecys in the atributes that are not key


### 4FN
In this form its about make the multi value data have not repeat data in between rows

* Be on [3FN](#3FN)
* The multi value filds are identify be a unique key


## Basics_Commands
There are some basic commands the [CREATE](#create), [INSERT](#insert), [SELECT](#select),[ALTER](#alter),[DROP](#drop) next I will explain a little more about them some of them are int the group of DML (Data Manipulation Lenguage) and DDL (Data Definition Lenguage).
 
### DDL

#### CREATE
The create command it for **creating** it could be table, databases or views
> **views** is a specific [SELECT](#select),  its a view of some data that you repeatly visit.
 ``` sql
CREATE TABLE IF NOT EXISTS people (
person_id INT NOT NULL AUTO_INCREMENT PRIMARY KEY, 
last_name VARCHAR(255) NULL,
first_name VARCHAR(255) NULL,
address VARCHAR(255) NULL, 
city VARCHAR(255) NULL
);
 ```

### ALTER
With this command you can **alter** a table or row or column 
> In the next example is for adding a column
 ``` sql
ALTER TABLE people ADD COLUMN date_of_birth DATETIME NULL AFTER city; 
 ```

#### DROP
This is for when you want to erase something it could be a row, a table or even a DB
> So be very careful when you use the **drop** command
> In the example you will eliminate the column previously created
 ``` sql
ALTER TABLE people DROP COLUMN date_of_birth;
 ```

### DML

### SELECT
This is one of the most used commands it is for selecting a specific data in the data base, only selecting and ordering what you want
> This is the most basic SELECT example is to see all the data that table have.
 ``` sql
SELECT * FROM people;
 ```

### INSERT
This is for when you need to insert values in a table
 ``` sql
INSERT INTO `platziblog`.`people` (`person_id`, `last_name`, `first_name`, `address`, `city`) 
VALUES ('1', 'Vásquez', 'Israel', 'Calle Famosa Num 1', 'México'),
	       ('2', 'Hernández', 'Mónica', 'Reforma 222', 'México'),
	       ('3', 'Alanis', 'Edgar', 'Central 1', 'Monterrey');
 ```

### UPDATE
The **UPDATE** statement is used to modify the existing records in a table.
``` sql
UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;
 ```
### DELETE
The **DELETE** statement is used to delete existing records in a table.
``` sql
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
 ```

## QUERY
This is when you want to know something from the DB the most basic coomands need it are [SELECT], and [FROM].
> **SELECT** is for selecting a specific column and **FROM** is from what table is that column
> **NOTE** if you see a * that means all data for example
  ``` sql
SELECT *
FROM posts;
 ```

 > Another example

``` sql
SELECT titulo, fecha_publicacion, estatus
FROM posts;
 ```

 There are some functions like count() that does what it's name implies count the number of data that it finds with the data you give.

## JOINS


### LEFT_JOIN

 ``` sql
 SELECT	*
FROM	usuarios 
LEFT JOIN posts on usuarios.id = posts.usuario_id;
 ```

### RIGHT JOIN

``` sql
SELECT	*
FROM	usuarios 
RIGHT JOIN posts on usuarios.id = posts.usuario_id
 ```

### INNER_JOIN
``` sql
SELECT	*
FROM	usuarios 
INNER JOIN posts on usuarios.id = posts.usuario_id;
 ```

### JOIN
``` sql
SELECT	*
FROM	usuarios 
JOIN posts on usuarios.id = posts.usuario_id;
 ```

## UNION
In this case will combine the query in this case will show everything from both tables but related by usuarios_id
``` sql
SELECT	*
FROM		usuarios 
	LEFT JOIN posts   ON usuarios.id = posts.usuario_id
UNION 
SELECT	*
FROM		usuarios 
	RIGHT JOIN posts ON usuarios.id = posts.usuario_id;
 ```

## WHERE
``` sql
SELECT	*
FROM		posts
WHERE	id	< 50;
 ```

 ### LIKE
 Search with that word 
 > the simbol % means that it can have anything in that space it could be a letter or many words
 ``` sql
SELECT	*
FROM		posts
WHERE	titulo LIKE '%escandalo%';
 ```


### BETWEEN
 ``` sql
SELECT	*
FROM		posts
WHERE	YEAR(fecha_publicacion) BETWEEN '2023' AND '2024';
 ```

 ## GROUP_BY
 ``` sql
SELECT estatus, COUNT(*) post_quantity
FROM posts
GROUP BY estatus;
 ```


## ORDER_BY
 ``` sql
SELECT *
FROM posts
ORDER BY  usuario_id DESC
 ```
 ### SPECIAL
 * DESC
 * ASC
 * LIMIT

 
