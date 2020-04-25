|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **How to upgrade Ubuntu 18.04.x to Ubuntu 20.04 on Croissants**

Ubuntu 20.04 LTS is released on April 23, 2020.  It is recommended to upgrade to Ubuntu 20.04 LTS.  You can upgrade Ubuntu 18.04.x to 20.04 on Croissants.

Ubuntu 18.04.x LTS will be End Of Life on April 2023 while Ubuntu 20.04 LTS will be End Of Life on April 2025.  Meanwhile, Ubuntu 20.04 LTS is faster and generate lesser heat due to newer Linux kernel.

Connect the ```monitoring cable``` to the internet instead of switch.  That means the Croissants is connected to the internet directly.  To make sure you are connected to the internet, you can ```ping google.com -c1``` to confirm.

Do not remote access to the Croissants.  Carrying out the following procedure directly to the Croissants instead of SSH.  If not, you may experience hanging at the end of the upgrade.

**WARNING : Upgrade may fail and you may need to re-install Ubuntu 20.04 and Croissants when failed!!**

```bash
sudo nano /etc/apt/sources.list.d/oisf-ubuntu-suricata-stable-bionic.list
```

Replace ```bionic``` with ```focal```

```bash
sudo do-release-upgrade -d
```

Answer ```y``` to the questions when asked and select ```default``` answer when it is highlighted.

Reboot the box at the end of the upgrade.

When the box is rebooted, do the following procedure.

```bash
sudo nano /etc/apt/sources.list.d/oisf-ubuntu-suricata-stable-bionic.list
```

Remove ```# ``` from ```# deb ``` and replace ```bionic``` with ```focal``` when necessary.

```bash
sudo update_ubuntu
sudo apt remove libhyperscan4
sudo apt install --reinstall suricata 
sudo apt install ifupdown
sudo pip3 install --upgrade suricata-update
```

Reconnect the ```monitoring cable``` back to the original position.  Reboot the box again.

Samiux  
OSCE  OSCP  OSWP  
April 25, 2020, Hong Kong, China  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
