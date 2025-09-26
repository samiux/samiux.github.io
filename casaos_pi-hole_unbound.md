# Setting up Pi-Hole & Unbound with CasaOS on Ubuntu 24.04.3 LTS

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

Change the port 53 to 5300 including TCP and UDP in the setup screen before installing the Pi-Hole.  Otherwise, the Pi-Hole cannot be installed on CasaOS as port 53 is being used.  Make sure to change the password and timezone inside the setting popup as well.

```   
[ -d /etc/systemd/resolved.conf.d ] || sudo mkdir -p /etc/systemd/resolved.conf.d

printf "%s\n%s\n" '[Resolve]' 'DNSStubListener=no' | sudo tee /etc/systemd/resolved.conf.d/10-make-dns-work.conf
```
Check if it is working properly.

```
$ cat /etc/systemd/resolved.conf.d/10-make-dns-work.conf

[Resolve]
DNSStubListener=no
```
```
sudo systemctl restart systemd-resolved
```

Install the Pi-Hole Unbound normally.

Go to Pi-Hole setting screen to change port 5300 back to port 53.

After the Pi-Hole installation, at the host (Ubuntu), do the following step to disable the DNS resolve function.  

```
sudo rm /etc/systemd/resolved.conf.d/10-make-dns-work.conf
sudo systemctl restart systemd-resolved  
```
   
Set the DHCP primary DNS to the IP of the Ubuntu host (Pi-hole hardware IP address), such as 192.168.0.244.

Make sure to set : Settings -- DNS (Expert Mode) click and enable ```Respond only on interface eth0```, then save the setting.

## Remarks

If browser is using secure DNS, such as Microsoft Edge, make sure to disable it or enable ```DNSSEC``` in Pi-Hole.  I prefer to disable secure DNS at the browser.

## Reference

- [CasaOS - A simple, easy-to-use, elegant open-source Personal Cloud system ](https://github.com/IceWhaleTech/CasaOS)     
- [Pi-Hole - Network-wide Ad Blocking](https://pi-hole.net/)    
- [Unbound - a validating, recursive, caching DNS resolver](https://nlnetlabs.nl/projects/unbound/about/)    

Samiux     
September 26, 2025, Hong Kong, China    

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|  
