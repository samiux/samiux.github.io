|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

# **Longjing 龙井 - Deep Learning Driven Web Application Firewall**

## DISCONTINUED - Deprecated

Longjing is Chinese green tea with a lot of antioxiants which can prevent you from getting cancer. Longjing Web Application Firewall (WAF) is deep learning driven by Python Scikit-Learn Library.  It is not designed for very high performance.  However, it is ideal for personal to small business web sites.

Longjing WAF is designed for any web server and any web application to block malicious web traffic, such as SQL Injection.

Longjing WAF is easy to install and deploy on modern Linux systems. The higher performance of the CPU, the higher efficiency of the Longjing WAF.

Longjing is the next generation Web Application Firewall! Fetch and try!

[![](https://img.youtube.com/vi/7ugn1bw4ZTA/0.jpg)](https://www.youtube.com/watch?v=7ugn1bw4ZTA)

## Features 

- detects common web attacks
- mainly for detecting SQL Injection attacks

## License

Longjing WAF's training data and modelling code are not open sourced.  However, the running python code and model built are open sourced, which is released under GPLv3 by Samiux.

## Requirement

- Ubuntu Linux Server 18.04.x LTS (other distribution may not be working properly)  
- Anaconda3 (Python 3)  
- mitmproxy 4.0.4 (Python 3)  
- any web server  
- any web application  
- high speed Hard disk (SSD is recommended)  
- about 1 GB RAM for Longjing WAF  

## ChangeLog

### Version 0.7.3  
Release date : 2018-02-09 GMT+8  
[+] First release  

### Version 0.7.4  
Release date : 2018-02-13 GMT+8  
[+] Model tuning  

### Version 0.7.5  
Release date : 2018-02-24 GMT+8  
[+] Code clean up  
[+] Add installer script  
[+] For mitmproxy 2.0.2  

### Version 0.8.0
Release date : 2018-02-26 GMT+8  
[+] Update for mitmproxy 3.0.3  

### Version 0.9.0
Release date : 2018-03-19 GMT+8  
[+] Modified for deep learning  

### Version 0.9.1
Release date : 2018-03-20 GMT+8  
[+] Performance tuning  

### Version 0.10.0
Release date : 2018-03-30 GMT+8  
[+] Performance tuning  
[+] Rebuild modelling  
[+] Rebuild training data  

### Version 0.10.1
Release date : 2018-04-04 GMT+8  
[+] Minor fix  
[+] Minor improvement  

### Version 0.10.2
Release date : 2018-04-09 GMT+8  
[+] Minor improvement  

### Version 0.10.3
Release date : 2018-05-24 GMT+8  
[+] Modified for mitmproxy 4.0.1  

### Version 0.10.4
Release date : 2018-10-21 GMT+8  
[+] Update training data  

### Version 0.10.5 [Stable, Latest]
Release date : 2019-03-04 GMT+8  
[+] Some improvement  
[+] Changed for Anaconda3 5.3.1  

## Usage

### Install Anaconda

```bash
sudo apt install build-essential libssl-dev libffi-dev python3-dev

wget https://repo.continuum.io/archive/Anaconda3-2019.07-Linux-x86_64.sh

chmod +x Anaconda3-2019.07-Linux-x86_64.sh

sudo -sH

./Anaconda3-2019.07-Linux-x86_64.sh
```

anaconda3 is default to install at ```/root/anaconda3``` and then answer "yes" to allow "conda" to initialize and change the ```.bashrc``` of root.

```bash
source /root/.bashrc
```

### Update Anaconda

```bash
sudo -sH

conda update --prefix /root/anaconda3 anaconda

conda update -n base conda
```

### Install mitmproxy

```bash
sudo -sH

conda install pip

pip install mitmproxy
```

Exit to normal user by entering ```exit```

### Update mitmproxy

```bash
sudo -sH

cd /root/anaconda3

pip install mitmproxy --upgrade
```

### Install Longjing

```
sudo apt install git

git clone https://github.com/samiux/longjing

cd longjing

nano config.conf
```

where :
- ```NET_INF``` is the network interface of the mitmproxy to be listening
- ```PORT``` is port number of the mitmproxy to be listening, e.g. 8080
- ```CERT``` is the location path of the private key TLS/SSL certificate of the domain when available.  It should be starting with ```--certs```.

Please read mitmproxy "about certificate" documents for details - [Using a custom certificate](https://mitmproxy.org/docs/latest/concepts-certificates/)

```bash
sudo ./install.sh
```

Finally, make sure to copy ```index.html``` to the web application root directory.

### Running

```bash
sudo systemctl restart longjing.service
```

### Limitation

- The source IP address cannot be detected or recorded.
- The speed of the web application will be slowed down a bit.

### Presentation

```sha256sum 116c66c8cb18b0cb280df0fc52425b250b17e231975f6dce50cc04fbcbbb5612  presentation-longjing.pdf```

Download : [presentation-longing.pdf](/pdf/presentation-longjing.pdf)

<object data="/pdf/presentation-longjing.pdf" type="application/pdf" width="900px" height="700px">
    <embed src="/pdf/presentation-longjing.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="/pdf/presentation-longjing.pdf">Download PDF</a>.</p>
</object>

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
