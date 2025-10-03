# Deployment of OpenVPN Access Server with 2 Connections Free

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

The fastest way to deploy OpenVPN server is to install [OpenVPN Access Server](https://openvpn.net/access-server/) on Linux server, such as Ubuntu 24.04.3 LTS.  However, you can only get 2 free concurrency connections.  The license fee of the OpenVPN Access Server is very high per connection, see [Pricing](https://openvpn.net/access-server/pricing/).  The price is $11-US per connection each month.

You need to sign up your account at [OpenVPN Access Server Page](https://myaccount.openvpn.com/signup?product=AS) and follow the instruction to install and deploy the server.

The current version is 3.0.1 as of this time writing and you can install the previous old 2.x versions (the latest is 2.14.3) too.  Please refer to the [Release Notes](https://openvpn.net/as-docs/release-notes.html) for details.

## Installation

```
wget https://packages.openvpn.net/as/install.sh
sudo bash install.sh --yes
```

To install the previous specified version, e.g. version 2.14.3.  Make sure to mark the version to avoid from being upgrade to the latest version.

```
sudo bash install.sh --as-version 2.14.3 --yes
sudo apt-mark hold openvpn-as
```

## Access

The screen would display the necessary access information to the admin account, such as IP addresses, username and password.  For example :

```
Access Server Web UIs are available here:
Admin  UI: https://192.168.0.100:943/admin
Client UI: https://192.168.0.100:943/
To login please use the "openvpn" account with "xxxxxxxxxxxx" password.
(password can be changed on Admin UI)
```

## Profile

To download user's ```profile``` on Client UI per user and import to the latest version of ```OpenVPN Connect 3``` client application.  It is available for Windows, macOS, iOS, Android and ChromeOS.

## Reference

- [Installing Access Server](https://openvpn.net/as-docs/installation.html)

Samiux    
OSCE  OSCP  OSWP    
September 21, 2025, Hong Kong, China    

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
