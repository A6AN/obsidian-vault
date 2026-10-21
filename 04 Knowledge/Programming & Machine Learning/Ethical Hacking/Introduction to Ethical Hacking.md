---
tags: [cybersecurity, machine-learning, programming]
---

2025-03-15 16:41

Status: #baby 

Tags: [[Ethical Hacking]]

# Introduction to Ethical Hacking


To start with Nmap we entered a command into terminal that is 
`nmap -A scanme.nmap.org`
it uses nmap to scan the test server nmap.org 
Which returns
```
`Starting Nmap 7.95 ( https://nmap.org ) at 2025-03-15 07:08 EDT`
`Nmap scan report for scanme.nmap.org (45.33.32.156)`
`Host is up (0.055s latency).`
`Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f`
`Not shown: 989 closed tcp ports (reset)`
`PORT      STATE    SERVICE      VERSION`
`22/tcp    open     ssh          OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)`
`| ssh-hostkey:` 
`|   1024 ac:00:a0:1a:82:ff:cc:55:99:dc:67:2b:34:97:6b:75 (DSA)`
`|   2048 20:3d:2d:44:62:2a:b0:5a:9d:b5:b3:05:14:c2:a6:b2 (RSA)`
`|   256 96:02:bb:5e:57:54:1c:4e:45:2f:56:4c:4a:24:b2:57 (ECDSA)`
`|_  256 33:fa:91:0f:e0:e1:7b:1f:6d:05:a2:b0:f1:54:41:56 (ED25519)`
`80/tcp    open     http         Apache httpd 2.4.7 ((Ubuntu))`
`|_http-title: Go ahead and ScanMe!`
`|_http-server-header: Apache/2.4.7 (Ubuntu)`
`|_http-favicon: Nmap Project`
`135/tcp   filtered msrpc`
`139/tcp   filtered netbios-ssn`
`445/tcp   filtered microsoft-ds`
`1022/tcp  filtered exp2`
`1023/tcp  filtered netvenuechat`
`1026/tcp  filtered LSA-or-nterm`
`9898/tcp  filtered monkeycom`
`9929/tcp  open     nping-echo   Nping echo`
`31337/tcp open     tcpwrapped`
`Device type: general purpose|WAP`
`Running (JUST GUESSING): Linux 2.4.X|3.X (89%), Actiontec embedded (89%), Microsoft Windows XP|7|2012 (88%)`
`OS CPE: cpe:/o:linux:linux_kernel:2.4.37 cpe:/h:actiontec:mi424wr-gen3i `cpe:/o:linux:linux_kernel cpe:/o:linux:linux_kernel:3.2 `cpe:/o:linux:linux_kernel:4.4 cpe:/o:microsoft:windows_xp::sp3 cpe:/o:microsoft:windows_7 cpe:/o:microsoft:windows_server_2012`
`Aggressive OS guesses: DD-WRT v24-sp2 (Linux 2.4.37) (89%), Actiontec MI424WR-GEN3I WAP (89%), Linux 3.2 (89%), Linux 4.4 (89%), Microsoft Windows XP SP3 or Windows 7 or Windows Server 2012 (88%)`
`No exact OS matches for host (test conditions non-ideal).`
`Network Distance: 2 hops`
`Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel`

`TRACEROUTE (using port 80/tcp)`
`HOP RTT     ADDRESS`
`1   0.29 ms 172.16.38.2`
`2   0.26 ms scanme.nmap.org (45.33.32.156)`

`OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .`
`Nmap done: 1 IP address (1 host up) scanned in 45.87 seconds`
```

This is Nmap Scan Analysis (scanme.nmap.org)

#### **1️⃣ Open Ports (Possible Entry Points)**

- **22/tcp (SSH) – OpenSSH 6.6.1p1 (Ubuntu)**  
    🔹 Secure Shell (SSH) service is running. If we had valid credentials, we could remotely access the machine.  
    🔹 Older versions of OpenSSH sometimes have vulnerabilities—could research exploits for version **6.6.1p1**.
    
- **80/tcp (HTTP) – Apache 2.4.7 (Ubuntu)**  
    🔹 A web server is running.  
    🔹 The **http-title** says: `"Go ahead and ScanMe!"`, which means it's designed for testing.  
    🔹 **Apache 2.4.7** is an older version; checking for known vulnerabilities might be useful.
    
- **9929/tcp (Nping Echo)**  

> [!NOTE]
> %%   ==Transmission Control Protocol (TCP) operating alongside the Internet Protocol (IP)==, forming the foundation of how data is transmitted reliably over networks like the internet. 
> 
> Here's a more detailed explanation:
> 
> TCP/IP Model:
>     
>     TCP and IP are two key protocols within the TCP/IP model, a suite of protocols that defines how data is transmitted between devices on a network. 
>     
> IP's Role (Internet Protocol):
>     
>     IP handles the addressing and routing of data packets across networks, ensuring that each packet reaches its intended destination. 
>     
> TCP's Role (Transmission Control Protocol):
>     
>     TCP provides a reliable, connection-oriented data transmission service, ensuring that data is delivered in the correct order and without errors. 
>     
> Working Together:
>     
>     IP uses the IP address to route packets, while TCP ensures the packets are delivered reliably, reassembling them into the original data stream at the destination. %%

    🔹 This is an uncommon service. Could be used for debugging or monitoring.
    
- **31337/tcp (tcpwrapped)**  
    🔹 "Elite hacker port" (31337 = "eleet" in leetspeak).  
    🔹 Likely an admin backdoor or a service with extra security.
    

---

#### **2️⃣ OS Detection (Operating System & Device Guessing)**

- **Host is running Linux (Ubuntu-based).**
- Possible OS matches:  
    🔹 **DD-WRT v24-sp2 (Linux 2.4.37)**  
    🔹 **Ubuntu Linux Kernel 3.2 or 4.4**  
    🔹 **Actiontec MI424WR-GEN3I WAP (router, possibly a firewall)**  
    🔹 Some **Microsoft Windows XP/7 signatures appeared**—could be a honeypot (fake system to catch attackers).

---

#### **3️⃣ Traceroute (Finding the Path to the Target)**

- **Hop 1**: 172.16.38.2 (Your network gateway)
- **Hop 2**: scanme.nmap.org (45.33.32.156)  
    🔹 Only 2 hops → The target is **very close** to your network, or it's using a direct connection.

### **🛠 Next Steps – What to Do Now?**

#### **🔍 1. Investigate the Web Server**

Use **Gobuster** to find hidden directories on the website:

```
bash
`gobuster dir -u http://scanme.nmap.org -w /usr/share/wordlists/dirb/common.txt`
```

This will check if there are secret admin panels, login pages, or files left open by mistake.

#### **📡 2. Check for Apache Vulnerabilities**

Search for known exploits related to **Apache 2.4.7**:

```
bash

`searchsploit apache 2.4.7`
```

or  
Check online at: [https://www.exploit-db.com](https://www.exploit-db.com)

#### **🛜 3. Probe the SSH Service**

Check if OpenSSH **6.6.1p1** has vulnerabilities:
```
bash

`searchsploit openssh 6.6.1`
```
If brute-forcing was allowed (which we **DON’T DO** without permission 😤), we’d use:
```
bash

`hydra -L userlist.txt -P passlist.txt ssh://scanme.nmap.org`
```
But we won't because we're **ethical** hackers. 😇

#### **1️⃣ Check If the Website Supports HTTPS**

Try **switching to HTTP** instead of HTTPS:

```
bash
`gobuster dir -u http://scanme.nmap.org -w /usr/share/wordlists/dirb/common.txt`
```

> [!example]
> gobuster dir -u http://scanme.nmap.org -w /usr/share/wordlists/dirb/common.txt =============================================================== Gobuster v3.6 by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart) =============================================================== [+] Url: http://scanme.nmap.org [+] Method: GET [+] Threads: 10 [+] Wordlist: /usr/share/wordlists/dirb/common.txt [+] Negative Status codes: 404 [+] User Agent: gobuster/3.6 [+] Timeout: 10s =============================================================== Starting gobuster in directory enumeration mode =============================================================== /.hta (Status: 403) [Size: 286] /.htaccess (Status: 403) [Size: 291] /.htpasswd (Status: 403) [Size: 291] /.svn (Status: 301) [Size: 316] [--> http://scanme.nmap.org/.svn/] /.svn/entries (Status: 403) [Size: 294] /favicon.ico (Status: 403) [Size: 293] /images (Status: 301) [Size: 318] [--> http://scanme.nmap.org/images/] /index (Status: 200) [Size: 6974] /index.html (Status: 200) [Size: 6974] /server-status (Status: 403) [Size: 295] /shared (Status: 301) [Size: 318] [--> http://scanme.nmap.org/shared/] Progress: 4614 / 4615 (99.98%) =============================================================== Finished ===============================================================

If the site doesn’t have an SSL certificate, this might work.

> [!important]
> ### **🔍 What Did Gobuster Find?**
> 
> Gobuster brute-forced the directories and found **the following:**
> 
> #### **1️⃣ Forbidden (403) Directories & Files:**
> 
> - `/.hta`, `/.htaccess`, `/.htpasswd` → These are **access control files** for Apache web servers.
> - `/favicon.ico` → The site's icon, but restricted access.
> - `/server-status` → **This page might reveal system info**, but it's blocked (403).
> 
> #### **2️⃣ Redirects (301) - Publicly Accessible Folders:**
> 
> - `/.svn/` → Old **Subversion (SVN) repository**. _Might leak source code if misconfigured._
> - `/images/` → Likely a folder containing **website images**.
> - `/shared/` → This might contain **publicly available files**.
> 
> #### **3️⃣ Directly Accessible (200) Pages:**
> 
> - `/index` & `/index.html` → **Main website pages.**
>     - Try visiting: **`http://scanme.nmap.org/index.html`**
> - `/shared/` & `/images/` → You can **browse these directories** if they're misconfigured.

#### **2️⃣ Test Your Connection to ScanMe**

Run these commands and **post the output**:

🟢 **Check if you can even reach the server:**

```
bash
`ping -c 4 scanme.nmap.org`
```

If packets are dropping, the server is **down or blocking you**.

🟢 **See if the port is actually open:**

```
bash
`nc -zv scanme.nmap.org 80 nc -zv scanme.nmap.org 443`
```

If you get "Connection refused," the site is **blocking connections** on that port.

---

#### **3️⃣ Try Curl to Confirm Connectivity**

```
bash
`curl -I http://scanme.nmap.org`
```

If it **fails**, the issue is your connection, not Gobuster.

---

#### **4️⃣ Use a Proxy (If You're Being Blocked)**

If the site is rejecting your requests, **use a proxy**:

```
bash
`proxychains gobuster dir -u http://scanme.nmap.org -w /usr/share/wordlists/dirb/common.txt`
```

(You’ll need `proxychains` installed first.)


### **Next Steps - What You Can Do?**

✅ **1. Try Visiting These URLs** (in a browser or curl):

```
bash

`curl -I http://scanme.nmap.org/shared/ curl -I http://scanme.nmap.org/images/ curl -I http://scanme.nmap.org/.svn/`
```

If they **return 200**, then the folders are **publicly browsable**!

✅ **2. Check for SVN Misconfiguration**  
If `.svn/entries` exists, you might be able to list the repository contents:

```
bash
`curl http://scanme.nmap.org/.svn/entries`
```

If successful, you might **leak source code**!

✅ **3. Try to Access Hidden Files**  
Since `.htaccess` is **blocked**, try finding other sensitive files:

```
bash
`gobuster dir -u http://scanme.nmap.org -w /usr/share/wordlists/dirb/small.txt`
```

(_Using a different wordlist might reveal more hidden stuff._)

---

### **⚠️ Important Notes**

- **403 Forbidden** means **you don’t have permission** to access those files.
- **301 Redirects** mean the folder exists, but it redirects you somewhere else.
- **200 OK** means **BINGO!** You can access the file or directory.
# References

