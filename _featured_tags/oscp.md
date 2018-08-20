---
layout: list
title: OSCP Guide
slug: OSCP
menu: true
order: 3
description: >
  OSCP Certification Path
---

Offensive Security Certified Professional (OSCP) Course is the only course which provides 100% practical experience in penetration testing. It provides you materials in the form of videos and pdf which contains the basic idea of each protocol and their attacking mechanism. It contains a variety of techniques and the scenarios which is handy in solving few machines in the lab. They also provide execercises on each chapter which gives you brief idea on how to work on. For beginners into penetration testing must have to solve those excercises and get into the lab machines which helps a lot. Even experience professionals who perform vulnerability assessment and penetration testing in the companies also doesn't have much exposure to the complete root of the system since the scope will always be limited to finding the vulnerabilities but not exploitation because they are production systems. Experience professionals may get to learn a lot of new techniques and gets more confidence on compromising the systems in the network. After completing this course, the person will be able to compromise the any given laptop/server with better easily but not all  as the recent security features are getting increased and the attack vectors has also widened. 

For more detailed information on the course fees and other details click [here](https://www.offensive-security.com/information-security-training/penetration-testing-training-kali-linux/)

In this article, i will be providing a path to earn OSCP certification which improve readers knowledge and boost the career.
Let's get started about the world which works on "information is wealth"!!!!!!  
To start the penetration testing, it has many many things to know few are listed:  
 - Networking is the main requirement for anyone to start with Pentesting since we are gonna play on the ground named as "Computer Networks". Hence it is mandatory to aware of working, protocols used, devices utilized etc. Certifications recommended are CCNA is the basic for networking. Also, helps you compromise misconfigured CISCO devices since you learn the configuration of the device as well in CCNA. it is not mandatory to have certification to start if you have the knowledge its enough. Few things as listed are
  - 7 Layers of OSI Model
  - Different request types (Unicast, Broadcast, Multicast)
  - Network Topologies
  - Subneting and LAN Technologies
  - Protocols such as ARP, DHCP, DNS, FTP, SSH, HTTP, SMB, SNMP, SMTP etc
  - Working of various types of Firewalls such network, application level
  - Working of various types of IDS, IPS, NAC devices

OSI Model
  - Entire computer network is based on the OSI Model, different protocls work on each layer of the model. Go through below link to get high level understanding the OSI Layers and its working. Also, it has few modules related to LAN technologies and network topologies which should also to be covered as necessary
  - [OSI Modle](http://www.techexams.net/technotes/ccna/osimodel.shtml)

Address Resolution Protocol (DHCP)
  - ARP protocol is used to resolve destination host MAC with IPv4 address 
  - [Understanding ARP](http://www.omnisecu.com/tcpip/address-resolution-protocol-arp.php)

Dynamic Host Configuration Protocol (DHCP)
  - DHCP is the one which provides identity(IP address) to all the devices in the network without IP no device can be live in network
  - [Understanding DHCP](https://technet.microsoft.com/pt-pt/library/cc780760(v=ws.10).aspx)

Internet Control Message Protocol (ICMP)
  - ICMP is the one used to identify any live host in the computer network. All the Ping, Traceroutes use ICMP
  - [Understanding ICMP](https://en.wikibooks.org/wiki/Communication_Networks/Ping)

Domain Name Service (DNS)
  - DNS is used to identify any domain's existence in the internet. It is like a telephone directory for internet. Read about it, it's really awesome
  - [Understanding DNS](https://technet.microsoft.com/pt-pt/library/cc772774(v=ws.10).aspx)

File Transfer Protocol (FTP)
  - FTP is most commonly used to transfer files from one system to another via internet. It is the most targeted protocol as well due to clear-text transmission of credentials. This protocol plays key role in compromising many machines in the lab. One must familiarize with many ways to upload and download file. In lab, you wont use traditional methods needs to explore the tricks to download files as well. It also has many exploits few are listed and more needs to researched which may limits the joy of learning so not giving them here
  - Dork intitle:ftp exploit site:exploit-db.com
  - [Pentesting FTP](https://shahmeeramir.com/penetration-testing-of-an-ftp-server-19afe538be4b)
  - [Remote Buffer Overflow](https://www.exploit-db.com/exploits/26471/)
  - [Directory Traversal](https://www.exploit-db.com/exploits/11973/)
  - [Authentication Bypass](https://www.exploit-db.com/exploits/37097/0)

Secure Shell (SSH)
  - SSH is one of the most secured protocol due to its encryption mechanism used on the communication process. It provides command line access to all the systems which runs ssh in it. It is has various authentication mechanisms like using credentials, RSA keys etc. There are few ways to hijack these RSA keys due a recent technique which allows to predict the RSA key with user's auth keys. If you get an LFI and SSH is running, don't always focus on RFI if not exist try this as well
  - [Introduction to ssh](https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process)
  - [SSH Protocol versions](http://thegeekyway.com/ultimate-guide-how-ssh-works/)
  - [Logging with password and RSA keys](https://www.digitalocean.com/community/tutorials/how-to-use-ssh-to-connect-to-a-remote-server-in-ubuntu)
  - [Attacks on SSH and its keys](http://www.hackingarticles.in/ssh-penetration-testing-port-22/)
  - [Abusing SSH Keys](https://www.pentestpartners.com/security-blog/how-to-abuse-ssh-keys/)

Telnet
  - Telnet is used to connect to any service like http, smtp, ftp etc. It is very handy in many situations like accessing smtp and imap to send and read emails etc
  - [Understanding and using telnet](https://procurity.wordpress.com/2013/07/15/beginners-guide-to-telnet-basics/)

Simple Mail Transfer Protocol (SMTP)
  - SMTP is used to send an email from one person to another based on the email address. It is very popular and used in all email communications, it has many security issues and are interesting too. Explore more exploits from the exploit-db will teach you more techniques to target easily
  - Dork - intitle:smtp exploit site:exploit-db
  - [Understanding SMTP](https://www.afternerd.com/blog/smtp/)
  - [Telnet to SMTP](https://mediatemple.net/community/products/dv/204404584/sending-or-viewing-emails-using-telnet)
  - [RCE Exploit](https://www.exploit-db.com/exploits/25970/)

Internet Message Access Protocol  (IMAP)
  - IMAP protocol is the most commonly used in all the email clients due to its flexibility. It is used to read received emails in the clients. It can be done with telnet as well. There are many exploits too available explore them to understand the security issues of it
  - Dork intitle:imap exploit site:exploit-db.com
  - [Telnet to IMAP](https://mediatemple.net/community/products/dv/204404584/sending-or-viewing-emails-using-telnet)

Server Message Block (SMB)
  - SMB is the most popular and vulnerable protocol which is used to share files and folders in windows, linux etc. In linux, it is samba. There are many exploits and ways to trick smb for our advantage. 
  - [Understanding SMB](http://www.tech-faq.com/smb-protocol.html)
  - Dork intitle:smb exploit site:exploit-db.com
  - [SMB Enum](http://www.hackingarticles.in/netbios-and-smb-penetration-testing-on-windows/)
  - [SMB Null Session](https://www.adampalmer.me/iodigitalsec/2013/08/10/windows-null-session-enumeration/)

Hyperext Transfer Protocol (HTTP)
  - HTTP is one of the most popular protocol which is used in web applications that contains client-server architeccture. All the applications running with the help of web browser uses HTTP protocol to request resources on the remote location. It is a separate domain in terms of security. It is called Application security which is more interesting to learn, explore with the below links
  - [HTTP Basics](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)
  - [HTTPs and auth](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-2--net-31155)
  - [Understanding SSL](https://medium.com/@User3141592/what-is-ssl-and-how-does-it-work-a5465d19b494)
Simple Network Management Protocol (SNMP)
  - SNMP allows to configure and monitor network devices. It contains all the information about the hosts, routers details like ip address, mac and os details, applications installed on the machine etc. These information are very useful penetration testing processs. Connecting to SNMP server willl allow you to gather as much information about the server with the below tools provided which will give you a simple output.
  - [Working of SNMP](https://technet.microsoft.com/pt-pt/library/cc783142(v=ws.10).aspx)
  - [SNMP in depth](https://www.networkmanagementsoftware.com/snmp-tutorial/)
  - [Enumerating SNMP with snmp-check](https://tools.kali.org/information-gathering/snmp-check)
  - [Pentesting SNMP](https://resources.infosecinstitute.com/snmp-pentesting/#gref)

Internet Relay Chat (IRC)
  - IRC is the protocol used to chat with people in the forums. This protocol will also be used in the lab or exam, one require awareness on the working and usage of this protocol to fuzz when it appeared
  - [IRC Tutorial](https://www.howtoforge.com/tutorial/linux-irc-clients/)

Bash Terminal
  - Learning Bash Terminal is required since most of the linux machines needs to be handled via terminal rather GUI. Hence, it is advised to have good hands on with bash terminal
  - [Bash Basics](https://www.youtube.com/watch?v=oxuRxtrO2Ag)

Scripting Languages to learn
  - Scripting Languages are pretty simple when compared with other programming languages. Also python is very simple to learn and script faster with full efficiency. One should have good command any scripting, since most of the boring works can be automated and many exploits can be modified as per the requirement to make it work
  - [Python Scripting](https://learnpythonthehardway.org/book/)

Web Application Security
  - Web Application security is more interesting and necessary to gain low privilege shell of any machine since it is the entry point for any organization or a machine. Web app pentest is a broader area where many things to be understood and practice. Below provided links will help you learn and practice the concepts
  - [Web App Testing Guide](https://www.owasp.org/index.php/Web_Application_Penetration_Testing)
  - [WebGoat](https://github.com/WebGoat/WebGoat)
  - [WebGoat Tutorial](http://webappsecmovies.sourceforge.net/webgoat/)
  - [bWAPP](http://www.itsecgames.com/)
  - [bWAPP Tutorial](https://teckk2.github.io/category/Web-Pentesting.html)
  - [LFI/RFI](https://medium.com/@Aptive/local-file-inclusion-lfi-web-application-penetration-testing-cc9dc8dd3601)
  - [Pentest Lab](https://pentesterlab.com/exercises/web_for_pentester/course)

Windows Privilege Escalation
  - [PrivEsc Tutorial](https://pentest.blog/windows-privilege-escalation-methods-for-pentesters/)
  - [Exploit Suggester](https://github.com/GDSSecurity/Windows-Exploit-Suggester)
  - [PrivEsc Checker](https://github.com/pentestmonkey/windows-privesc-check)
  - [ Privesc cheatsheet](https://www.sploitspren.com/2018-01-26-Windows-Privilege-Escalation-Guide/)
  - [Exploits](https://github.com/SecWiki/windows-kernel-exploits)

Linux Privilege Escalation
  - [Privesc Tutorial](https://payatu.com/guide-linux-privilege-escalation/)
  - [PrivEsc Cheatsheet](https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/)
  - [PrivEsc Checker](http://pentestmonkey.net/tools/audit/unix-privesc-check)
  - [PrivEsc Checker](https://github.com/sleventyeleven/linuxprivchecker)
  - [Exploit Suggester](https://github.com/mzet-/linux-exploit-suggester)
  - [Exploit Suggester](http://pentestmonkey.net/tools/audit/exploit-suggester)
  - [Exploits](https://github.com/SecWiki/linux-kernel-exploits)

Metasploit Framework
  - [Metasploit Tutorial](https://www.offensive-security.com/metasploit-unleashed/) Guess no intro required for this guy

Brute FOrce
  - Password Cracking is required sometimes in the lab where you might need to crack the hashes or login passwords need the below tools
  - [md5 crack](https://www.md5online.org/) Want to crack md5 or sha1 just use this one gives you result in secs
  - [John the Ripper](https://medium.com/@petergombos/lm-ntlm-net-ntlmv2-oh-my-a9b235c58ed4) Helps you crack all kind of hashes includes ntlm, md5 etc. Best advantage is automatically detects the type of hash and starts cracking it.
  - [HashCat](https://www.4armed.com/blog/hashcat-crack-md5-hashes/) Great cracking tool which uses the hardware to complete the tasks quickly

File Transfers
  - File transfers often required while moving files from one machine to another during the pentest process these tools may handy
  - [Netcat, a Swiss Army knife](https://www.binarytides.com/netcat-tutorial-for-beginners/) Multi purpose tool, we can transfer files, shells and can gain reverse shell as well
  - [wget](https://www.poftut.com/wget-command-tutorial-examples-linux/) To download files on the linux machine
  - [Wget Powershell](https://github.com/wg135/pentest/blob/master/wget.ps1) If you gain command line access and want to download files via command line it is very useful
  - [Wget VBS](https://gist.github.com/sckalath/ec7af6a1786e3de6c309) Got cmd access but no powershell, no gui - this is useful just run "Cscript.exe wget.vbs url/filename" to download

Web Enum
  - [Curl](https://curl.haxx.se/docs/httpscripting.html) Multi purpose command line tool allows to interact with web servers, download files, exploit put method etc
  - [Directory Buster](https://null-byte.wonderhowto.com/how-to/hack-like-pro-hack-web-apps-part-7-finding-hidden-objects-with-dirb-0168596/) Identify the hidden directories 
  - [Nikto](http://dasunhegoda.com/nikto-web-vulnerability-scanner-tutorial-imawhitehat/893/) Detects server Misconfigurations and helps you faster the pentest process
  - [cadaver](http://www.hackingarticles.in/5-ways-to-exploiting-put-vulnerability/) A WebDav client to access the remote server
  - [cadaver Manual](https://www.systutorials.com/docs/linux/man/1-cadaver/)

Remote Tools
  - [PSExec](http://jjasser.com/2014/04/psexec-simple-tutorial/) Have credentials and want another user of same machine access, use it to enjoy
  - [Mimikatz](https://www.offensive-security.com/metasploit-unleashed/mimikatz/) Dump the windows credentials
  - [Runas](https://www.windows-commandline.com/windows-runas-command-prompt/) How to run a program with admin access in cmd? Find out here

[Reverse Shells Cheatsheet](http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet) All reverse shells in just a line at one place

[Spawning a TTY shell](https://netsec.ws/?p=337) Got an error need interactive shell to execute commands, here is the solution

Network Pivoting or Port tunneling
  - [SSH Tunnel](https://chamibuddhika.wordpress.com/2012/03/21/ssh-tunnelling-explained/) To tunnel a port from one network to another needs these techniques
  - [SShuttle](https://www.ivoidwarranties.tech/posts/pentesting-tuts/pivoting/sshuttle/) SShuttle is used to automate the port forwarding or pivoting to another network which is accessible through 

Practice Plattforms
  - [Root.me](https://www.root-me.org/en/Challenges/)  Solve the challenges here it will help a lot in the lab especially for privesc go for it to enjoy
  - [VulnHub VM's](https://www.abatchy.com/2017/02/oscp-like-vulnhub-vms) Provides a kick start to OSCP challenges and a way to proceed in penetration testing process. Helps you a lot and try harder for it
  - [HackTheBox](https://www.hackthebox.eu/)  Great plattofrm to enhance and improve the penetration testing skills and a free paltform to enhance
  - [HTB Walkthroughs](https://www.youtube.com/watch?v=K05mJazHhF4&list=PLidcsTyj9JXL8AIU-45CQ9GBfqjArnkkZ)
  - [Penetration Testing Lab](https://lab.pentestit.ru/) Platform which simulates real time network topology fron an entry router/firewall to a main Domain controller. Really interesting to solve like compromising an organization