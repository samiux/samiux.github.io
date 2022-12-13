|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Capture The Flag (CTF) - Linux Binary Exploitation Challenges Lab

## Basic Knowledge Requirements

- Linux  (Ubuntu, Parrot Security or Kali Linux is recommended)
- Linux security features  (RELRO, Canary, NX, PIE & etc)
- GNU Debugger (GDB)  
- GDB Plugins (gef, pwndbg & etc)  
- Assemble Language knowledge (optional when Ghidra or IDA is in force)  
- Ghidra or IDA (optional but recommended)
- C/C++ Language knowledge 
- Python Language  (Python 3 is recommended)
- Exploit Development skill 
- pwntools (optional but recommended)  

## Challenges

If you can solve the following challenges, please let me know (```Discord @samiux#3445```).  

### Linux Binary Exploitation (Pwn) Challenges Lab

PwnCTF 22.04 is developed on CTFd Framework.  The challenges are mainly designed for Pwnable and Practical purpose.  Difficulty is basic to intermediate level.  No heap exploitation is involved.

PwnCTF 22.04 is based on Glibc 2.35 (Ubuntu 22.04 LTS).  There are a total of 10 challenges.

#### Usage

Import the ova file into Virtualbox (or VMWare) and access the control panel at the server IP address on port 8000 with browser (e.g. http://192.168.56.50:8000).  It is well tested on Virtualbox.  Network interface is "Bridged Network" by default.  Please change the type of network interface on Virtualbox when necessary.   Please register at the control panel page for the challenges.   

**WARNING - This lab is vulnerable and do NOT allow it to be connected to the internet.**  

#### Download 

- __sha256 : b1b30ea8a38960c66613bfdc1cf3f69b6e579199c3f5c05b809ea305e2c1fe77 -- PwnCTF 22.04_v20221213.ova (Glibc 2.35)__  

- [Download PwnCTF 22.04 v20221104.ova (8.88GB)](<(https://drive.google.com/file/d/1m1faWaQfbnFd9If9MA2V1EK40vKsciuJ/view?usp=sharing)>)  

#### Changelog

- May 20, 2022 - Version 2022.0 -- First released  
- May 21, 2022 - Version 2022.1 -- Some improvement  
- May 21, 2022 - Version 2022.2 -- Increase 5 more challenges, a total of 10 challenges  
- Aug 19, 2022 - Version 2022.3 -- Modify the Virtualbox settings for better implementation experience  
- Sep 25, 2022 - Delete Glibc 2.31 version (PwnCTF 2022)
- Oct 15, 2022 - Version 22.04 -- Based on Ubuntu 22.04 LTS (GLib 2.35)  
- Oct 25, 2022 - Version 20221025 -- Updated Ubuntu
- Nov 04, 2022 - Version 20221104 -- Updated Ubuntu   
- Dec 13, 2022 - Version 20221213 -- Updated Ubuntu  

#### Demo

[![](https://img.youtube.com/vi/dpziHIbRYXM/0.jpg)](https://youtu.be/dpziHIbRYXM "PwnCTF 22.04 Demo")  

## Tutorials & Writeups

### Writeups  
- [Nightmare](https://guyinatuxedo.github.io/)  

### Tutorials  
- [pwn.college](https://pwn.college/)  - Basic concept in Videos   
- [CTF pwn tips](https://github.com/Naetw/CTF-pwn-tips)  
- [CTF Wiki](https://ctf-wiki.org/)  - Chinese  

## Books

- ```从 0 到 1 - CTFer 成长之路``` -- [Nu1L 战队]( https://www.nu1l.com/#/) 编著  (ISBN 978-7-121-37695-5)  
- ```CTF 竞赛权威指南 - Pwn 篇``` -- 杨超 编著  (ISBN 978-7-121-39952-7)  

## Bonus

Challenge : gets_only (Linux binary)  
Description : Oh! Only gets() in the binary!  
File : [gets_only](https://github.com/samiux/CTF/raw/main/gets_only)  
sha256 : 65075f0f30bbd5561ca80aa57c645c7b31af4b49b6f8764575fca4b44989cb1c  
Author : Samiux  
Date : August 21, 2022  

### Demo

[![](https://img.youtube.com/vi/cUEkw6Y9Zzw/0.jpg)](https://youtu.be/cUEkw6Y9Zzw "PwnCTF gets_only Demo")  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
