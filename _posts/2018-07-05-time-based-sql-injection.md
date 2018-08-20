---
layout: post
title: SQL Injection
description: >

tags: [SQL Injection]
---

## Time-based SQL Injection  


A type of **SQL Injection** attack which is performed based on the response timing from the application. An attacker can perform "time-based SQL Injection" by tampering the user input with special characters such "',",*,\" etc which is then placed in the backend SQL query of the application. On parsing this query with database, it does not respond for a specified period of time. It can be exploited by using functions like sleep(), wait for delay etc and ask questions to the database for its name, version etc.

#### Steps to identify and exploit
  Step 1: Let's append some special characters as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/time-based/1.PNG)
  Step 2: But application does not respond anything, so we use a "Logical Operator" with "sleep()" to see if it is vulnerable to time-based attacks
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/time-based/2.PNG)
  Step 3: Note the application is not responding as per the specified period, so we use the query as "id=1' AND if((select substr(database(),1,1) = 's'), sleep(10),null) --+"
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/time-based/3.PNG)
  Step 4:Note the application is not responding since the "first character of the DB is 's'". In this way, we need to brute force for more details like version etc.