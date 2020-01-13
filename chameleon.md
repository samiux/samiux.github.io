|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **Chameleon 变色龙 - Website IP Address Seeker**

## Introduction

Chameleon is designed for seeking IP address of a target website with a searchable string in a given IP range.

It is developed in Python 3.7.x by Samiux and it is released under GPLv3.

## Limitation

If the IP address and/or the domain is not pointed to the web root directory, Chameleon cannot find the site as expected. Do NOT set the vaule of &quot;--thread&quot; too high as it will consume all your memory.

[![](https://img.youtube.com/vi/SKZa5eLuO90/0.jpg)](https://www.youtube.com/watch?v=SKZa5eLuO90)

## Download

```bash
sudo apt install git

git clone https://github.com/samiux/chameleon
```

## Changelog

### Version 0.0.1
Released on FEB 22, 2015 GMT+8  
[+] First release  

### Version 0.0.2
Released on FEB 25, 2015 GMT+8  
[+] Add input file for the ip address comparison  
[+] Add timeout option  
[-] Drop the single ip address for comparison  

### Version 0.0.3
Released on FEB 26, 2015 GMT+8
[+] Add exceptional error handling  
[+] Add threading option  
[+] Add output file option  
[+] Add batch of IP address per thread option  

### Version 0.0.4
Released on MAR 5, 2015 GMT+8  
[+] Add exceptional error handling  
[+] Bugs fix  

### Version 0.0.5
Released on SEP 13, 2019 GMT+8  
[+] Bug fix  
[+] Add more broswer user-agent option  
[+] Add Referer Header option  

### Version 0.0.6
Released on SEP 14, 2019 GMT+8  
[+] Bug fix  

### Version 0.0.7
Released on SEP 14, 2019 GMT+8
[+] Performance and resources tuning  
[+] Add port number option  
[+] Bug fix  
[+] Major modification  

### Version 0.0.8
Released on SEP 15, 2019 GMT+8  
[+] Add path to the search  

### Version 0.0.9
Released on SEP 16, 2019 GMT+8
[+] Lower the default threads setting to 30  
[+] Add the IP range of USA and other, Ocean Digital  
[+] Update the IP range of Singapore, Ocean Digital  

### Version 0.0.10
Released on SEP 16, 2019 GMT+8  
[+] Multi-threading bug fix  

### Version 0.0.11
Released on SEP 17, 2019 GMT+8  
[+] Multi-threading bug fix  
[+] Change back to 100 default threads setting  

### Version 0.0.12
Released on SEP 18, 2019 GMT+8  
[+] Performance boost  
[+] Multi-threading bug fix  

### Version 0.0.13
Released on SEP 22, 2019 GMT+8  
[+] Major modification  
[+] Bug fix  

### Version 0.0.14
Released on SEP 23, 2019 GMT+8  
[+] Minor improvement  

### Version 0.0.15
Released on SEP 28, 2019 GMT+8  
[+] Major improvement  

### Version 0.0.16
Released on SEP 29, 2019 GMT+8  
[+] Add the IP range of all and ap-northeast-{1,2,3}, aws  
[+] Add example  

### Version 0.0.17
Released on OCT 01, 2019 GMT+8  
[+] Minor improvement  

### Version 0.0.18
Released on OCT 02, 2019 GMT+8  
[+] Minor improvement  
[+] Bug fix  

### Version 0.0.19
Released on OCT 03, 2019 GMT+8
[+] Python 3 bug fix  

### Version 0.0.20 (Stable, Latest)  
Released on OCT 04, 2019 GMT+8  
[+] Minor improvement  

## Usage

```bash
cd chameleon

python3 chameleon.py -s github -f ip-addresses.txt -P 9000 -w github.txt -a "index/homepage.php" -R True

or

python3 chameleon.py -s github -f ip-addresses.txt -p https -P 9000 -w github.txt -a "index/homepage.php" -H github.com -R True
```
##### You may comfortable to run this script on 8GB RAM system with 10Mbps internet in default settings.

## Bonus

### IP Ranges of Common VPS/Cloud Providers

(A) IP Range of AWS</b><br>

[AWS IP Address Ranges](https://docs.aws.amazon.com/general/latest/gr/aws-ip-ranges.html)

```bash
sudo apt install jq

wget https://ip-ranges.amazonaws.com/ip-ranges.json
```

__Get all IP range of AWS :__


```bash
jq -r '.prefixes | .[].ip_prefix' < ip-ranges.json
```

__Get all IP range of ap-northeast-1, AWS :__

```bash
jq -r '.prefixes[] | select(.region=="ap-northeast-1") | .ip_prefix' < ip-ranges.json
```

(B) IP Range of Ocean Digital

[Ocean Digital IP Address Ranges](https://ipinfo.io/AS14061)

(C) IP Range of Vultr

[Vultr IP Address Ranges](https://ipinfo.io/AS20473)

(D) IP Range of Starry Network Limited

[Starry Network Limited IP Address Ranges](https://ipinfo.io/AS134835)

## Reference

[CIDR to IPv4 Conversion](https://www.ipaddressguide.com/cidr)

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|



