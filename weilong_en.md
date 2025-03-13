# 威龙  Weilong - Intrusion Detection and Prevention System  防御入侵系统
# Model 6 Version 2

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

[中文](/weilong_cn.md)  

### The callsign of our country - China's fifth generation invisiable jet fighter J-20 is "Mighty Dragon", as known as "Weilong".

As technology advances, so do cybersecurity threats, which can leave individuals and small businesses vulnerable to cybercrime. Public-facing networks and computers are highly susceptible to daily hacker attacks from around the world. In response to this need, the Weilong Intrusion Detection and Prevention System (IDPS) was developed as a highly efficient and ultra-low latency security solution.

One of the most significant benefits of Weilong is its user-friendly design, making it accessible to everyone, regardless of their technical expertise in Network Security Monitoring (NSM) or Information Security (InfoSec). This "Plug, Play and Forget" system efficiently eliminates the need for any complex configurations or maintenance. Also, Weilong is making it an affordable and ideal solution for home and small office/home office (SOHO) setups.

Weilong's creator is an experienced white hat hacker, so the cybersecurity solution's design effectively detects and prevents sophisticated cyber threats. The Weilong Intrusion Detection and Prevention System utilizes the malicious hacker's inside knowledge of current and potential malicious hacker tactics. And it provides complete transparency and is hassle-free for users.

Protecting digital assets should be a priority, and Weilong Intrusion Detection and Prevention System meets this need. With this reliable and easy-to-use cybersecurity solution, individuals and small office/home office businesses can feel secure knowing that their digital assets are protected, and their data is secured against cyberattacks.

In summary, Weilong Intrusion Detection and Prevention System is an effective, user-friendly, and accessible cybersecurity solution that can cater to the varying security needs of individuals and small office/home office businesses.

## FEATURES

- Blocks known malicious activities, e.g. attack attempts
- Blocks known malwares, e.g. ransomwares  
- Blocks known malicious and phishing websites  
- Monitoring and inspecting traffic for analysis  
- Compatible with Bittorrent and 4K video streaming  
- Ultra-low latency for demanding online games  
- Compatible with Microsoft Windows, GNU Linux, Apple macOS, Apple iOS, Google Android and Huawei HarmonyOS  
- No subscription and annual fee  
- Automatically update  
- Plug, Play and Forget!  
- Totally transparent  
- Setup is not required   

## CHARACTERISTICS

The standout feature of Weilong Intrusion Detection and Prevention System compared to other similar products is its ability to confuse hackers.

For example, when a thief wants to break into a room, they usually enter through doors or windows. But if the thief cannot find or see any doors or windows, even though they actually exist, how can they break into the room?

Similarly, if hackers cannot find or see any points of intrusion, even though they actually exist, how can they invade your computer or network?

This is a design concept that strikes at the source, and has been proven to be feasible, reliable, and practical. It is highly effective in preventing hacker intrusions.

## THREAT OF INVASION

After a hacker invasion, they can leave or take any information they want, and they can also use your computer or network for any purpose, including using it as a jumping point to invade other computers or networks.

## HARDWARE

- Max. power consumption 5W, fanless, no noise  
- Slightly larger than a credit card  
- 96.5mm (L) x 68mm (W) x 30mm (H)   

## DEPLOYMENT  

You are recommended to connect the Weilong in front of router.  However, you can connect it behind router too.  If you connect the Weilong in front of router, you cannot see the intranet.

If it is deployed in front of router, it will generate a lot of alerts and may be too noisy.  However, if situation is allowed and some ports are opened, it is recommended to place it in front of router.

- Fig. 1 Cannot see intranet

```
            (WAN)             (LAN1 to Router's WAN)          (Router's LAN)          
   Modem ----------- Weilong ----------------------- Router ----------------- PCs & Laptops
   (or with WIFI)         |                           (WIFI)                      
     (unused)             |                             | (Router's LAN)                   
                          +-----------------------------+
                              (LAN2 to Router's LAN)
```

- Fig. 2 Cannot see intranet

```
                                                                                +------- Laptops
                                                                                |
            (WAN)           (LAN1 to Router's WAN)     (Switch's LAN)           |
   Modem ----------- Weilong ------------------ Router -------- Switch ---------+
   (or with WIFI)         |                      (WIFI)             |           |
     (unused)             |                                         |           |
                          +-----------------------------------------+           +------- PCs
                                   (LAN2 to Switch's LAN)

```

- Fig. 3 Can see intranet

```
                                                                                +------- Laptops
                                                                                |
            (WAN)           (to Weilong's WAN)     (LAN1 to Switch's LAN1)      |
   Modem ----------- Router ------------------ Weilong -------- Switch ---------+------- WIFI AP
                     with WIFI (unused)           |                 |           |
                                                  |                 |           |
                                                  +-----------------+           +------- PCs
                                                 (LAN2 to Switch's LAN)

```

- Fig. 4 Can see intranet

```
                                                                   
                                                                    
            (WAN)          (LAN1 to WIFI AP's WAN)                  
Modem with ----------- Weilong --------------- WIFI AP -------------------- PCs & Laptops
WIFI Router (unused)      |                        |               
                          |                        |               
                          +------------------------+              
                            (LAN2 to WIFI AP's LAN)

```

- Fig. 5 Can see intranet

```
                                                                    +------- WIFI AP
                                                                    |
            (WAN)          (LAN1 to Switch's Port #1)               |
Modem with ----------- Weilong ---------------- Switch -------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (LAN2 to Switch's LAN)

```

- Fig. 6 Can see intranet

```
                                                                    +------- WIFI AP
                                                                    |
            (WAN)          (LAN1 to Switch's Port #1)               |
5G Modem ----------- Weilong ------------------ Switch -------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                            (LAN2 to Switch's LAN)
```

Do NOT use the wifi that comes with 5G modem or modem with WIFI router as the traffic flow will NOT be protected by Weilong.

## FAQ  

### When will the rules be updated?

#### 24/7
Between 0600 and 0630 hours every day, Weilong will do the housekeeping and updating.  The defending work of Weilong may be interrupted during this period.  

#### non 24/7
Weilong can be turned off and it is not required to operate 24/7.  The update will be carried out within half an hour when the Weilong is booting up.  It is advised NOT to turn off the Weilong between 0600 and 0630 hours as it will do the update automatically.  If you do so, you may break the Weilong.  Meanwhile, if you turn off the Weilong within half an hour of the booting up, you may also break the system too.    

### How many detecting / blocking rules in Weilong?  
There are over 38,000 rules in Weilong and they are all free of charge.  The number of rules are increasing.    

### Can Weilong decrypt the SSL/TLS traffic?
Weilong cannot decrypt the SSL/TLS traffic well.  However, it can handle a limited SSL/TLS traffic flow.  Therefore, it is not ideal for using it as Web Application Firewall (WAF).  For example, Weilong can detect and drop self signed SSL/TLS certificate traffic and etc.  

### Do I also need anti-virus on my computer or laptop?
Yes, anti-virus is required.  You are also advised to install the following add-ons or extensions for your browser such as Firefox or Chrome in order to increase the security for surfing the internet.

- uBlock Origin  
- Ghostery  
- Malwarebytes Browser Guard  
- Avast Online Security & Privacy  (except Firefox)  
- MalwareAI Browser Security  
- VT4Browsers  

## KNOWN ISSUES

Public Secure DNS will encrypt the DNS query that will affect the ability of blocking of IDPS, those secure DNS cannot be used, such as 

- Cloudflare DNS
- Quad9 DNS
- NextDNS
- OpenDNS
- DNSWatch

## PRICE

System price : Please contact Samiux  (NOT including delivery)

Package included : device x 1, power adapter x 1 and USB Type-C cable x 1, as well as CAT 6 network cables x 2.

Copyright (c) 2012-2025 Samiux  

## SUPPORT AND ENQUIRY

Discord samiux @samiux   (#3445)  

## SEE ALSO  

- [Intrusion Detection, Intrusion Prevention, and Antivirus: The Differences](https://bestructured.com/intrusion-detection-intrusion-prevention-and-antivirus-the-differences/)
- [洋葱式防御 - 网络空间安全篇 (最新篇）](/onion-defense_3.md)

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
