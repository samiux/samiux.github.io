|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

Vulnerable Machine - Seattle Sounds

Vulnerable VM : Seattle v0.3  
Difficulty : Beginner/Moderate  

Seattle Sounds web application is a virtual machine and it is vulnerable by design. The author of this virtual machine is HollyGraceful who is a female penetration tester. The virtual machine is designed for beginner and/or Moderate. This web application has the following vulnerabilities :

SQL Injection  
Reflected and Stored Cross-Site Scripting  
Insecure Direct-Object Reference  
Username Enumeration  
Path Traversal  
Exposed phpinfo()  
Exposed Administrative Interface  
Weak Admin Credentials  

You can download it at [VulnHub](https://www.vulnhub.com/entry/seattle-v03,145/) (File size : 579 MB)

To extract the downloaded file in debian or Ubuntu Linux :

```bash
sudo apt-get install p7zip

7z x Seattle-0.0.3.7z
```

Then import to Virtualbox and browse it with your browser.

```
sha256sum 9661c846f1bada165adff670395d459b22a9690711a1d2ca61f6dacee3612ee3  seattle-report-compressed.pdf
```

The following is the penetration testing report of the vulnerable virtual machine :

<object data="/pdf/seattle-report-compressed.pdf" type="application/pdf" width="900px" height="700px">
    <embed src="/pdf/seattle-report-compressed.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="/pdf/seattle-report-compressed.pdDownload PDF</a>.</p>
</object>

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

