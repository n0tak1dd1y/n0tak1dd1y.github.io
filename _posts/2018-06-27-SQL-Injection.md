---
layout: post
title: SQL Injection
description: >

tags: [webapp]
---

## SQL Injection

**SQL Injection** attack allows an attacker to inject malicious SQL Queries into database which extracts sensitive data via user input fileds of the application. On successfull exploitation, an attacker can insert/modify data in database or even compromise the server  
#### Data and its types
Data is any information which is being processed and stored on the computer for some purpose. It includes text documents, images, audios, videos etc.
Types of data are:
 - Structured which is well organizaed and stored in a hierarchical form
 - Unstructured which is not organized and does not have any hierarchies


#### Database and its types
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
 - Document Databases stores all the data in the JSON, XML formats
 - key-value stores uss a key-value to perform read and write processing of data like text, video, audio, text documents in high-speed
 - Wide column stores used tables with rows and columns to store the data and can be retrieved with a group of columns
 - Graph Databases uses graph structures to store, map and query relationships. It allows index-free adjacency to link adjacent elements 
 
 
Examples of **SQL Databases** are:  
  - MySQL
  - Oracle
  - Postgresql
 
 
Examples of **NoSQL Databases** are:
  - MongoDB
  - Redis
  - MemcacheDB


#### What can be done with SQL Injection?
Allows attackers to perform the below:  
 - Insert/Modify the contents of the database  
 - Dump the entire database of the application  
 - Gain access to the shell of the application server

#### Prone Vectors  
 - Input fields which interacts with databases  
 - Hidden fields  
 - HTTP Headers

#### Steps to detect SQL Injection
  Step 1: Enter an integer or text on the input field  
  Step 2: Check the results of the application  
  Step 3: Analyze what all the inputs interact with database  
  Step 4: Guess the DBMS used in the application and pass the special characters like ‘, “, #, * to break the syntax of the query.  
  Step 5: There are different ways to identify as follows:  
	  - Syntax error from the database  
	  - No Content displayed on tampering the query  
	  - If sleep function is passed server doesn’t respond for the specified time
  Step 6: Based on the response, the query has to be fixed.  
  Step 7: All about “Break and Fix the Syntax”. It’s not about passing the payloads on all the inputs and expect an output. It’s  a waste of time  
  Step 8: We can use tools like SQLMAP or manual to dup the database
#### SQL Injection Demo
  Step1: As the string entered in the search box with a "'" at the end of the word and it thrown an "SQL" syntax error  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/sqli/1.PNG)
  Step2: Since the syntax of the query might be as "SELECT * FROM TABLE WHERE ID = 'movie'", the "'" in thhe search box has overflowed and need to be fixed in order to execute queries in the database as shown.  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/sqli/2.PNG)
  Step3: As shown passing a comment "hello'-- -" fixed the syntax error. The reason is we have commented out the rest of the query as "SELECT * FROM TABLE WHERE ID = 'movie'-- -".  
  Step4: Now we can use this weakness to dump the entire content in thhe movies table as shhown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/sqli/3.PNG)
  Step5: As seen above, the keyword "hello' OR '1'='1'-- -" has dumped the entire content using an "Logical OR" logic. The query has become "SELECT * FROM TABLE WHERE ID = 'hello' OR '1'='1' -- -'". The first part of the query is "hello'" is false and the sencod part of the query is true as "1=1" is true. Hence the database has shown the entire content.
#### Types of SQL Injection:
 - Error-based SQL Injection  
 - Blind SQL Injection  
   - Boolean-based SQL Injection  
   - Time-based SQL Injection  
 - Second Order SQL Injection
