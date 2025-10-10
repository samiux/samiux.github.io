# Pi-Hole & Unbound on Debian 12 (Bookworm)

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

## Install Pi-Hole.

```
curl -sSL https://install.pi-hole.net | bash
```

Answer the questions on the screen.  Make sure you use ```port 5353``` as ```upstream DNS``` for 127.0.0.1 and listen to ```eth1``` network interface.

Use the desirable ethernet interface, e.g. eth1.

*Make sure to write down the password displayed after the installation.* 

## Install Unbound.

```
sudo apt install unbound unbound-anchor unhound-host
```

```
sudo cp /usr/share/doc/unbound/examples/unbound.conf /etc/unbound/unbound.conf.d/
```

```
sudo nano /etc/unbound/unbound.conf.d/unbound.conf
```

Under ```server:``` append ```interface: 127.0.0.1@5353```


```
sudo systemctl enable unbound.service
sudo systemctl restart unbound.service
```

## Post installation.

```
http://<pi-hole ip address>/admin
```
e.g. http://192.168.68.210/admin

Make sure use the password given after the installation to login.

Go to Settings --> DNS (expert mode) --> Respond only on interface eth1 (enabled)

## Final Step.

Then go to router and under ```DHCP``` to set the Pi-Hole IP address to the ```Primary DNS (Optional)```, e.g. 192.168.68.210.  You can also make one more Pi-Hole as secondary DNS on the same network too.

## Enhancement.

Add the following [DNS Blocklists](https://github.com/hagezi/dns-blocklists) to Pi-Hole at Lists as ```Add blocklist```.

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

### Update the blocklists.

Go to Tools --> Update Gravity --> Update

## Restart Pi-Hole

After the blackout, you may required to restart your Pi-Hole in this way.

```
sudo systemctl restart pihole-FTL
```

## Reference

- [Pi-Hole - A black hole for Internet advertisements](https://github.com/pi-hole/pi-hole)       
- [Pi-Hole Offficial Site](https://pi-hole.net/)     
- [Unbound - a validating, recursive, caching DNS resolver](https://nlnetlabs.nl/projects/unbound/about/)       
- [Pi-Hole Ad Tester](https://fuzzthepiguy.tech/adtest/)    

Samiux       
OSCE   OSCP   OSWP    
September 30, 2025, Hong Kong, China      

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
