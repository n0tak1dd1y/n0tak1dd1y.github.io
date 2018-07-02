---
layout: post
title: SQL Injection
description: >

tags: [webapp]
---

## SQL Injection

**SQL Injection** attack allows an attacker to inject malicious SQL Queries into database which extracts sensitive data via user input fileds of the application. On successfull exploitation, an attacker can insert/modify data in database or even compromise the server 

####Data and its types
Data is any information which is being processed and stored on the computer for some purpose. It includes text documents, images, audios, videos etc.
Types of data are:
 - Structured which is well organizaed and stored in a hierarchical form
 - Unstructured which is not organized and does not have any hierarchies

####Database and its types
A **Database** is a collection of structured and unstructred data stored in a accessible location in an organized way using model approach.
Types of Databases:
 - Relational Database stores data in a tabular form with rows and columns where columns is a category and row is a data
 - Distributed Database stores data in multiple locations
 - Object-oriented Database works based on objects and data rather than actions and logic
 - Graph Database based on nodes and edges where a node is an entity and edge is a connection between nodes

A **Database Management System** is a software application which is used to store and tretireve all kinds of data in a digital format. it allows users and programmers to create and maintain the databases in the computer. It also provides a systematic way to create, update, retrieve and modify the data in the databse.  

There are two types of SQL databases available for developers and users based on the type of data:
 - SQL (Structured Query Language) Databases
 - NoSQL ("not-only" Structured Query Language) Databases

A __SQL__ is a **Structured Query Language** is used to query the databse for retrieving/modifying the data. This is a standard for interacting with databases. THese type of databases store the data in a structured way where each field is defined in the schema which value to where in the database.
Databases comes under SQL are :
 - Relational Database (RDBMS)
 - Distributed Databases (DDBMS)

A __NoSQL__ is a **not-only SQL** is used to query the database. NoSQL Databases are used to store unstructred data in the database where the fields are not defined to what kind of values these are free-form manner. 
Databases users NoSQL are:
 - Document Databases
 - key-value stores
 - Wide column stores
 - Graph Databases

### Types of SQL Injection:
 - Error-based SQL Injection
 - Blind SQL Injection
   - Boolean-based SQL Injection
   - Time-based SQL Injection
 - Second Order SQL Injection  
