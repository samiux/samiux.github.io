# Rosemary 迷迭香 - Intrusion Detection and Prevention System  防御入侵系统

Networks and computers that are opened to the public facing hacker attacks from all over the world every day.  Once we are compromised, we would be one of the cyber crime victims.  Our Rosemary is a high performance and ultra-low latency Intrusion Detection and Prevention System (IDPS).  Unlike well known and famous brands for large business enterprises in the market,  Rosemary is available in low price that everyone can afford.  It is ideal for home and Small Office Home Office (SOHO). 

Not a Network Security Monitoring (NSM) or Information Security (InfoSec) expert?  No problem!  Our Rosemary really is the "Plug, Play and Forget" system of your dreams, it is totally transparent.  Don't be the next cyber crime victims, try Rosemary now!

Rosemary is designed by a hacker to defend against hackers. He knows what hackers are doing and thinking, regardless of whether they are ethical or malicious.

## FEATURES

- Blocks known malicious activities  
- Compatible with Bittorrent and 4K video streaming  
- Ultra-low latency for demanding online games  
- Compatible with Microsoft Windows, GNU Linux, Apple macOS, Apple iOS, Google Android and Huawei HarmonyOS  
- No subscription fee  
- Automatically update  
- Plug, Play and Forget!  
- Totally transparent   

## HARDWARE

### Model A (Black)

- 8 cores CPU  
- 8GB RAM  
- 32GB Storge  
- 3 Network interfaces  
- 96.5mm (L) x 68mm (W) x 30mm (H)   

### Model B (Black)

- 4 cores CPU  
- 4GB RAM  
- 8GB Storge  
- 3 Network interfaces  
- 94.5mm (L) x 68mm (W) x 30mm (H)  
 
## DEPLOYMENT  

The following is the recommended connection method of Rosemary.  However, you can connect it behind router too.

```bash
            (WAN)             (LAN1 to Router's WAN)          (Router's LAN)          
   Modem ----------- Rosemary ----------------------- Router ----------------- PCs
                          |                           (WIFI)                      
                          |                             | (Router's LAN)                   
                          +-----------------------------+
                              (LAN2 to Router's LAN)
```
```bash
                                                                                +------- Laptops
                                                                                |
            (WAN)           (LAN1 to Router's WAN)     (Switch's LAN)           |
   Modem ----------- Rosemary ------------------ Router -------- Switch --------+
                          |                      (WIFI)             |           |
                          |                                         |           |
                          +-----------------------------------------+           +------- PCs
                                   (LAN2 to Switch's LAN)

```
```bash
                                                                    +------- WIFI AP
                                                                    |
            (WAN)          (LAN1 to Switch Port #1)                 |
5G Modem ----------- Rosemary ------------------ Switch ------------+
WIFI Router (unused)      |                        |                |
                          |                        |                |
                          +------------------------+                +------- PCs & Laptops
                                    (LAN2)

```

Do NOT use the wifi that comes with 5G modem as the traffic flow will NOT be protected by Rosemary.

## FAQ  

### When will the rules are updated?

#### 24/7
Between 0200 and 0600 hours every day, Rosemary will do the housekeeping and updating.  The defending work of Rosemary may be interrupted during this period.  Outdated logs will be deleted at 0200 hours.  All blacklists will be updated at 0300 hours.  Rosemary will be updated at 0400 hours (when necessary).  All rules will be updated at 0500 hours.  Rosemary will be updated at 0600 hours (it will auto reboot when necessary).  

#### non 24/7
Rosemary can be turned off and it is not required to operate 24/7.  The update will be carried out within half an hour when the Rosemary is booting up.  The Rosemary may be reboot itself when necessary.  It is advised not to turn off the Rosemary between 0300 and 0600 hours as it will do the update automatically.  If you do so, you may break the Rosemary.  Meanwhile, if you turn off the Croissants within half an hour of the booting up, you may also break the system too.    

### How many detecting / blocking rules in Rosemary?  
There are more than 40,000 rules in Rosemary and they are all free of charge.  The number of rules are increasing.    

### Do you recommend to access Rosemary via SSH in internet?
For security purpose, it is not recommended to connect Rosemary via SSH in internet.  However, you may connect Rosemary via SSH in intranet.    

### Can Rosemary decrypt the SSL/TLS traffic?
Rosemary cannot decrypt the SSL/TLS traffic well.  However, it can handle a limited SSL/TLS traffic flow.  Therefore, it is not ideal for using it as Web Application Firewall (WAF).  For example, Rosemary can detect and drop self signed SSL/TLS certificate traffic and etc.  

# AVAILABLE SOON! 
