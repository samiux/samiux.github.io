# Series on Cybersecurity (Part II) – Virtual Servers

[中文](/defense_02_vps.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

About two years ago, a friend of mine had a virtual private server (VPS) for his website. His service provider complained that his VPS was attacking other VPSs and requested that he cease this activity. Unfortunately, my friend ignored the warning, and ultimately, his VPS service was suspended. At this point, he turned to me for help. After some negotiations, the service provider finally agreed to reactivate his VPS, marking the beginning of our cybersecurity efforts.

From my friend, I learned that his VPS was secured with a very simple SSH password—only six characters long and consisting of something like "123." Additionally, the account name was "root." This presented an excellent opportunity for hackers to exploit. I quickly changed the root password to something much stronger.

Upon further investigation, I discovered that hackers had hidden a difficult-to-detect encrypted trojan on the server. After removing it, I took additional measures to fortify the VPS's security. Since then, my friend has not received any further complaints about his VPS being involved in attacks.

## Takeaway

All passwords should be strong, containing a mix of uppercase and lowercase letters, numbers, and symbols, and they should be lengthy. More importantly, passwords should not be easily guessable, such as "MyStr0ngP@ssw0rd," which is not acceptable.

Servers should be reinforced with security measures, including antivirus software, Intrusion Detection and Prevention Systems (IDPS), and Web Application Firewalls (WAF).

Samiux  
OSCE OSCP OSWP  
September 4, 2024, Hong Kong, China  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
