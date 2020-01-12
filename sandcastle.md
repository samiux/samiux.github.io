|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **Sandcastle 沙堡 - Amazon AWS S3 Bucket Enumeration**

## What is Amazon S3?

Amazon Simple Storage Service is storage for the Internet. It is designed to make web-scale computing easier for developers.

Amazon S3 has a simple web services interface that you can use to store and retrieve any amount of data, at any time, from anywhere on the web. It gives any developer access to the same highly scalable, reliable, fast, inexpensive data storage infrastructure that Amazon uses to run its own global network of web sites. The service aims to maximize benefits of scale and to pass those benefits on to developers.

## Introduction

Sandcastle is Amazon Web Service S3 (AWS S3) Bucket Enumeration Tool.  It is original developed by <a href="https://github.com/0xSearches/sandcastle">ysx</a> since 2017.  <a href="https://github.com/Parasimpaticki/sandcastle">Parasimpaticki</a> who forked it and added some new features on it.

Original and forked version of Sandcastle use aws cli tool for the enumeration.  However, the aws cli tool has been changed recently and it is no longer working any more.  I, Samiux, modified Sandcastle for the purpose.

Sandcastle is developed in Python 2.7.x and Python 3.7.x.  It is modified by Samiux.  It is released under GPLv3.

## Download

```bash
sudo apt install git

git clone https://github.com/samiux/sandcastle
```

## ChangeLog

### Version 1.4.0  
Released on AUG 24, 2019 - GMT+8  
[+] Modified the code from Parasimpaticki version 1.3  

### Version 1.4.1  
Released on AUG 24, 2019 - GMT+8  
[+] Source code clean up  

### Version 1.4.2
Released on AUG 25, 2019 - GMT+8  
[+] Source code clean up  

### Version 1.4.3 (Latest, Stable)  
Released on OCT 03, 2019 - GMT+8  
[+] Modified for Python 3.7.x  

## Usage

```bash
cd sandcastle

python3 sandcastle.py -h

python3 sandcastle.py -t shopify -b bucket-names.txt
```
|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|


