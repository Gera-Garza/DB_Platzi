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


## Technologies
Project is created with:
* 
> * 

	
## Setup


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

