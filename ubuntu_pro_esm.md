|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# How to enable Ubuntu Pro Expanded Security Maintenance with 5 Free Machines

## What is Extended Security Maintenance (ESM)?

[Extended Security Maintenance (ESM)](https://ubuntu.com/security/esm) is one of the features of Ubuntu Pro. It provides 10 years security coverage for Ubuntu Linux.  It fixes the vulnerabilities (CVEs) with 1 day gap instead of 98 days which without ESM enabled.

For personal users, Ubuntu Pro provides 5 free machines for the services per account.  You are required to registered in [Ubuntu One](https://login.ubuntu.com/) in order to have this free support.

Once you registered in Ubuntu One, you can follow the below steps to enable ESM.

```
sudo pro attach
```
It will output :

```
Initiating attach operation...

Please sign in to your Ubuntu Pro account at this link:
https://ubuntu.com/pro/attach
And provide the following code: XXXXXX
```

After that, you are required to login to ```https://ubuntu.com/pro/attach``` with your previous Ubuntu One account's username and password.  Once login, you enter the code ```XXXXXX``` into the field provided.  The Ubuntu box will automatically enabled the ESM and your Ubuntu box will then be updated.

To confirm that your box is attached to Ubuntu Pro ESM or not.

```
pro status
```

The output will be similar to the following :

```
SERVICE          ENTITLED  STATUS    DESCRIPTION
esm-apps         yes       enabled   Expanded Security Maintenance for Applications
esm-infra        yes       enabled   Expanded Security Maintenance for Infrastructure
livepatch        yes       enabled   Canonical Livepatch service
realtime-kernel  yes       disabled  Ubuntu kernel with PREEMPT_RT patches integrated

Enable services with: pro enable <service>

     Account: xxxx@xxxxmail.com
Subscription: Ubuntu Pro - free personal subscription
```

Samiux  
OSCE  OSCP  OSWP  
January 27, 2023, Hong Kong, China  

## Reference

- [Extended Security Maintenance (ESM)](https://ubuntu.com/security/esm)  
- [Ubuntu Pro](https://ubuntu.com/pro)  
- [Ubuntu One](https://login.ubuntu.com/)  
- [Ubuntu Pro Attach](https://ubuntu.com/pro/attach)  
- [Ubuntu Pro Tutorial](https://ubuntu.com/pro/tutorial)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
