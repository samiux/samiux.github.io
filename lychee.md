|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# Lychee 荔枝 - ClamAV On-Access Scanning Installer Script

ClamAV's On-Access scanning can detect the known malwares/virus in real time.  Any Debian/RPM based Linux system can install this script when FANOTIFY is configured in your Linux kernel.

## Verify

```
cat /boot/config-$(uname -r) | grep FANOTIFY
```

The suitable display is :

```
CONFIG_FANOTIFY=y
CONFIG_FANOTIFY_ACCESS_PERMISSIONS=y
```

When you see the following message, your Linux system is not suitable for this script.

```
CONFIG_FANOTIFY_ACCESS_PERMISSIONS is not set
``` 

## Softwares

- ClamAV 1.0.0
- Ubuntu 22.04.1 LTS and Fedora 37 are tested

Remarks : ClamAV uses about 3GB RAM.

## Change Log

### Version 0.1 (Dated DEC 28, 2022) (Latest)
- First release for ClamAV 1.0.0

Remarks : This script is developed by Samiux and it is released under GPLv3.  It is an Open Source Project.

## Install

Download the script.
```
git clone https://github.com/samiux/lychee
```

Edit the related parts at the top parts of the script.
```
cd lychee

nano clamav-installer
```

Then run the script to install ClamAV On-Access scanning.
```
sudo chmod +x clamav-installer
sudo ./clamav-installer
```
Please allow about 1 to 2 minutes for ClamAV to load the signatures.   
You can run this script at any time on the same Linux system box without any harm.

## Uninstall

```
sudo systemctl stop clamav-freshclam.service
sudo systemctl disable clamav-freshclam.service
sudo systemctl unmask clamav-freshclam.service
sudo systemctl stop clamav-daemon.service
sudo systemctl disable clamav-daemon.service
sudo systemctl unmask clamav-daemon.service
sudo systemctl stop clamav-clamonacc.service
sudo systemctl disable clamav-clamonacc.service
sudo systemctl unmask clamav-clamonacc.service
sudo rm -R /var/log/clamav
sudo rm -R /var/lib/clamav
``` 

If DEB package :
```
sudo dpkg -r clamav
```

If RPM package :
```
sudo rpm -e clamav
```

## Test file
- [Eicar Test File](https://www.eicar.org/download-anti-malware-testfile/)  

## Known issues

- [BUG : /home directory cannot be used](https://github.com/Cisco-Talos/clamav/issues/799)
- / directory cannot be used as it will lockup the system.
- Non-existent directory will caused high CPU usage.

## Reference

- [ClamAV Official Site](https://www.clamav.net/)  
- [ClamAV Downloads](https://www.clamav.net/downloads)  
- [ClamAV Documentation](https://docs.clamav.net/)  
- [ClamAV GitHub](https://github.com/Cisco-Talos/clamav)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
