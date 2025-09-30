# Setting up Pi-Hole & Unbound with CasaOS on Ubuntu 24.04.3 LTS

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

Pi-Hole on CasaOS is running as Docker container.  The setting is a little bit difference to normal setup.

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

## Additional Blocklist

There are a lot of blocklist for Pi-Hole available in the internet.  I use the following blocklist.  Make sure to use the list for Pi-Hole or Adblock.  Update the lists after added the sources.

- [DNS-Blocklists: For a better internet - keep the internet clean!](https://github.com/hagezi/dns-blocklists)    

You can update the lists every day by using cronjob using the following command :

```
sudo docker exec big-bear-pihole-unbound pihole -g
```

### Recommanded Blocklist

```
DNS Rebind Protection - Prevents attackers from resolving domains to local IPs!
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adguard/dns-rebind-protection.txt

DoH/VPN/TOR/Proxy Bypass - Prevent methods to bypass your DNS!
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/doh-vpn-proxy-bypass.txt

Newly Registered Domains (NRD)
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/nrd28-22.txt

Threat Intelligence Feeds - Increases security significantly! (Recommended)
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/tif.txt

Pop-Up Ads - Protects against annoying and malicious pop-up ads!
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/popupads.txt

Fake - Protects against internet scams, traps & fakes!
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/fake.txt

Multi PRO - Extended protection (Recommended)
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/pro.txt

Most Abused TLDs - Protects against known malicious Top Level Domains! (Recommended)
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/spam-tlds-adblock.txt

Anti Piracy - Protects against piracy!
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/anti.piracy.txt

Gambling - Protects against gambling content!
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/gambling.txt

Dynamic DNS blocking - Protects against the malicious use of dynamic DNS services!
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/dyndns.txt

NSFW - Protects against adult content!
https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/adblock/nsfw.txt
```

## Remarks

If browser is using secure DNS, such as Microsoft Edge, make sure to disable it or enable ```DNSSEC``` in Pi-Hole.  I prefer to disable secure DNS at the browser as it cannot bypass the Pi-Hole.

## Reference

- [CasaOS - A simple, easy-to-use, elegant open-source Personal Cloud system ](https://github.com/IceWhaleTech/CasaOS)     
- [Pi-Hole - Network-wide Ad Blocking](https://pi-hole.net/)    
- [Unbound - a validating, recursive, caching DNS resolver](https://nlnetlabs.nl/projects/unbound/about/)    
- [DNS-Blocklists: For a better internet - keep the internet clean!](https://github.com/hagezi/dns-blocklists)    

Samiux     
September 26, 2025, Hong Kong, China    

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|  
