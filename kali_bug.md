|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Kali Linux developers are not up to the standard

No matter you are upgrading your Kali Linux (Rolling Release) from the previous version or fresh install 2022.1, you may encounter GNOME could not be started when you are installed GNOME only on your system (no matter it is physical hardware or Virtualbox's virtual machine).  

To reproduce it by fresh install Kali Linux 2022.1 on Virtualbox (latest version, no matter it is installed from official site or from Ubuntu 20.04.3 LTS).  Upgrade it by issuing ```"sudo apt update && sudo apt -y dist-upgrade"```.  Shutting down the system once or twice (or more) and booting it up again, you cannot login to the GNOME environment anymore.  If you are installed Kali Linux on Virtualbox, you are required to reinstall it with another Desktop Environment instead of GNOME.

Kali Linux user "soheilkhanalipur" submitted the problem (bug) to Kali Linux's Bug Tracker on April 6, 2022 ([0007661: GNOME does not start after authentication](https://bugs.kali.org/view.php?id=7661)).  Developer "arnaudr" was assigned to fix it on April 11, 2022.  However, he stated that he tested it without any problem and the bug tracker was closed then on the same day.  It is classifed as "not fixable".

On the other hand, Ubuntu 22.04 LTS is still under development and it is also using the latest version of GNOME.  However, it has no such problem on Virtualbox.  I am sure that it is not the bug in Debian or Ubuntu.  It should be the bug that created by Kali Linux.  I can reproduce the problem for many times as at this writing.  Since it is installed on Virtubalbox, there is no F1 to F10 keys.  I cannot check the system log to ensure what the problem is.

I doubt if Kali Linux developers are using Kali Linux.  Or, they are not testing it well or fully and properly before releasing it.  Meanwhile, developer "arnaudr" is not doing his best to find out the problem or reproducing it before closing the file.  Kali Linux developers are not up to the standard in my opinion.

If you do not like Kali Linux anymore, you can switch to other penetration testing Linux distributions, such as [Parrot Security](https://www.parrotsec.org/) which is also Debian based.

Samiux    
OSCE  OSCP  OSWP    
April 12, 2022, China, Hong Kong    

## Reference

- [0007661: GNOME does not start after authentication](https://bugs.kali.org/view.php?id=7661)    
- [Parrot Security](https://www.parrotsec.org/)    

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
