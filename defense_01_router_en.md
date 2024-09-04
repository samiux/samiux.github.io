# Series on Cybersecurity (Part One) – Router

[中文](/defense_01_router.md)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

Recently, a friend of mine complained about his internet speed plummeting from over 900 Mbps to around 300 Mbps. Initially, I suspected that my Intrusion Detection and Prevention System (IDPS) might be causing the slow-down, but I was skeptical. Thus, I launched an investigation.

Since he only had an Intrusion Detection and Prevention System (IDPS) installed without the detailed network information, we identified some unusual traffic going out through port 123, but could not ascertain which device was responsible. This required further examination of the devices involved.

At one point, I suspected that his Windows system might have been infected with malicious software. A scan with a well-known antivirus software revealed a Trojan concealed within an ISO file. However, theoretically, this Trojan shouldn't have been active, and after deleting it, the IDPS continued to detect unusual traffic, confirming that the issue was not related to the ISO file.

This prompted me to suspect that his router might have been infected with malware. After searching for information on the router's model, I discovered that the firmware for that model hadn't been updated since 2020 on the Hong Kong website, and there were multiple severe vulnerabilities reported between 2022 and 2024. Given this information, I concluded that his router had likely been compromised and malware installed. Further investigation revealed that other countries' websites offered firmware updates from 2024. After updating and resetting the router, the internet speed immediately returned to normal.

However, after performing additional checks, although the router was updated and reset and the speed was back to normal, there were still some unusual traffic flows on port 123. I suspected that a backdoor from the malware remained on the router. While this traffic was being intercepted, it still warranted action. Ultimately, replacing the router resolved the issue completely.

## Takeaway

In addition to regularly updating computer and mobile operating systems, it's essential not to overlook firmware updates for routers.

Furthermore, while an IDPS can block most malicious attacks, it is also an invaluable tool for effectively diagnosing network security issues.

Samiux  
OSCE OSCP OSWP  
September 3, 2024, Hong Kong, China  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
