---
layout: post
title: SQL Injection
description: >

tags: [SQL Injection]
---

## Second Order SQL Injection  


A type of **SQL Injection** attack which can be performed to manipulate/update contents in the database as injecting the payload in the first query and exploiting in the second query. An attacker perform "Second Order SQL Injection" by tampering the user input in a page and injects the payload as a normal input which is then stored in the database. Now, he will perform actions in the second page which is related to the input in the first page that gets executed. It is a very rare and difficult one to find out.

#### Steps to identify and exploit
  Step 1: Let's create a new user with username as "admin'-- -" as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/second-order/1.PNG)
  Step 2: User has been created successfully and login with the credentials as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/second-order/2.PNG)
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/second-order/3.PNG)
  Step 3: Check the database table which is created with our username and password as shhown
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/second-order/4.PNG)
  Step 4: As application prompted to change the password, so fill the appropriate details as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/second-order/5.PNG)
  Step 5: Note the passowrd has been updated successfully as shown
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/second-order/6.PNG)
  Step 6: Now check the "users" table for the password of the users "admin, admin' -- -"
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/second-order/7.PNG)
  Step 7: Voila!!! we are intended to change the password of the user "admin'-- -" but it has changed the password of "admin". Here thhe logic is the username is as "select * from users where username = 'admin' AND password='curr_pass'" but the query has been changed to "select * from users where username = 'admin'-- - AND password='curr_pass'". Due to this, the rest of the content has been ignored and new password has been updated for the user "admin".