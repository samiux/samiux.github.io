|[Home](/README.md)|[Articles](/articles.md)|[About](/about.md)|

# **中國香港網絡罪行硏究**

中國香港對於網絡罪行的法例比較分散，它們分佈在電訊條例、刑事罪行條例和盜竊罪條例中。我嘗試以我有限的法律知識去硏究一下中國香港的網絡罪行的法例，這純粹是我個人的意見，並不代表香港政府和香港警務處的立場。

以下的硏究是假設在沒有受攻擊方的書面同意書或授權書下地進行。

### 掃描器

大多數國家及地方都視掃描活動為犯法。至於中國香港又如何呢？

掃描器 (Scanner) 大致有分漏洞掃描器 (Vulnerability Scanner) 和端口掃描器 (Port Scanner) 兩大類。漏洞掃描器又大致有分網絡漏洞掃描器 (Network Vulnerability Scanner) 及網站漏洞掃描器 (Web Application Vulnerability Scanner) 兩大類。在搜證方面，我個人認為端口掃描器的活動比較難搜集證據，而最容易的是網站漏洞掃描器；至於網絡漏洞掃描器就介乎兩者之間。

基於網站漏洞掃描器的活動有可能影響和干擾網站的正常運作，這就有可能觸犯刑事毀壞罪 (Criminal Damage)。而網絡漏洞掃描器活動的影響和干擾相對比較少，但因搜證也不難，所以漏洞掃描器活動亦都有可能觸犯刑事毀壞罪。至於端口掃描活動相對對目標機器的影響和干擾極之少，但並不代表端口掃描活動不犯法，只是搜證比較困難罷了。

### 阻斷服務或分佈式阻斷服務攻擊

阻斷服務 (Denial of Service, DoS) 和分佈式阻斷服務 (Distributed Denial of Service, DDoS) 攻擊非常明顯地影響和干擾目標機器的正常運作，而且搜證也不太難，所以這活動有可能觸犯了刑事毀壞罪。

### 域名非法跳轉和跨站腳本攻擊

當網域名稱系統 (Domain Name Service, DNS) 被脅持或網站的跨站腳本 (Cross Site Scripting, XSS) 漏洞被利用，網站可能會被這樣的活動而非接觸式地被改頭換面 (Defacing)。

這活動亦有可能觸犯了刑事毀壞罪或不誠實使用電腦罪 (Obtaining Access Computer with Criminal or Dishonest Intent)，雖然在搜集證據上有一定的困難。

以上的例子在一般大眾是比較難理解的，所以在此列舉作出硏究，以免觸犯法律而不自知。所以掃描目標機器、阻斷服務攻擊和域名跳轉是有可能觸犯香港法例的。


Samiux  
OSCE  OSCP  OSWP  
二零一九年三月廿日，中國香港  

#### 参考資料

香港法例第二百章 刑事罪行條例 第五十九及六十節  
香港法例第二百章 刑事罪行條例 第一六一節  

|[Home](/README.md)|[Articles](/articles.md)|[About](/about.md)|
