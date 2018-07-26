---
layout: post
title: SQL Injection
description: >

tags: [SQL Injection]
---

## Error-based SQL Injection  


A type of **SQL Injection** attack which is performed based on the "Yes/NO" response from the application in the form of blank page or no content displayed. An attacker can perform "boolean-based SQL Injection" by tampering the user input with special characters such "',",*,\" etc which is then placed in the backed SQL query of the application. On parsing this query with database, it does not show any content due to A SYNTAX error. If the user input does not break the syntax, the application displays the regular page. If the user input breaks the syntax, then the application displays blank page or a page with modified contents. It proves that the application is vulnerable to "Boolean-based SQL Injection".
#### Steps to identify and exploit
  Step 1: Let's append some special characters as shown  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/boolean/1.PNG)
  Step 2: There is no error on the application rather it is not displaying the contents. Let's use comment tag "--+" to see if the content is displayed again  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/boolean/2.PNG)
  Step 3: As there is no error to identify or enumerate database, we use "Logical operator AND" to enumerate as "Yes/No" format. Pass query as "id=1' AND 0"
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/boolean/3.PNG)
  Step 4:Note the application is not displaying content since it is a false condition, we use true condition and check it as "id=1' AND 1 --+"  
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/boolean/4.PNG)
  Step 5: As the application is showing content for true condition, so we can use this to enumerate the database details. Pass the query as "id=1' AND substr(database(),1,1) = 's'--+" it allows enumerate the database name chracter by character. Inorder to identify the DB name we need to brute force it for all the 26 characters. Here the first character is "s" identified as shown
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/boolean/5.PNG)
  Step 6: Similarly we can enumerate the version of the DB as "id=1' AND substr(version(),1,1)= 1 --+" 
  ![](https://raw.githubusercontent.com/n0tak1dd1y/n0tak1dd1y.github.io/master/assets/webapp/boolean/6.PNG)
  Step 7: In this way, we can enumerate all the contents of the database.
