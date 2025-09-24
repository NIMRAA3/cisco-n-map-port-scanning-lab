````markdown
# 🔍 Cisco Lab: Use a Port Scanner to Detect Open Ports  

## 📖 Description  
This repository contains my Cisco CSE Operating System lab on **using Nmap to detect open ports**.  
The lab demonstrates TCP and UDP scanning, service/version detection, and aggressive scanning to analyze open ports, services, and vulnerabilities inside the CSE-LABVM environment.  



## 🎯 Objectives  
- Use **Nmap** to detect open TCP and UDP ports.  
- Identify services and their versions running on the host.  
- Understand the purpose of these services.  
- Research vulnerabilities associated with open ports.  
- Practice security analysis and reporting.  


## 🖥️ Resources  
- PC with **CSE-LABVM** in VirtualBox  
- **Nmap 7.80** pre-installed in the VM  
- Terminal access  



## 📝 Lab Steps  

### Step 1: Run a Basic TCP Scan  
```bash
nmap localhost
````

### Step 2: Run a UDP Scan

```bash
sudo nmap -sU localhost
```

### Step 3: Service & Version Detection

```bash
nmap -sV localhost
```

### Step 4: Aggressive Scan

```bash
nmap -A localhost
```


## ❓ Lab Questions & Answers

1. **What TCP ports are open?**
   → 22 (SSH), 23 (Telnet), 631 (IPP)

2. **Purpose of TCP services?**

   * **SSH (22):** Secure remote access
   * **Telnet (23):** Remote CLI (insecure, cleartext)
   * **IPP (631):** Printing services

3. **What UDP ports are open?**
   → 123 (NTP), 631 (IPP), 5353 (mDNS)

4. **Purpose of UDP services?**

   * **NTP (123):** Time synchronization
   * **IPP (631):** Printing
   * **mDNS (5353):** Local device discovery

5. **Vulnerabilities?**

   * **SSH (22):** Brute force, weak keys
   * **Telnet (23):** Cleartext login, sniffing
   * **IPP (631):** Remote code execution, DoS
   * **NTP (123):** Amplification DDoS
   * **mDNS (5353):** DoS, spoofing, info disclosure



## 🎓 Learning Outcomes

* Gained hands-on practice with **Nmap scans**.
* Learned to interpret **open ports and services**.
* Understood **real-world risks** tied to common services.
* Practiced writing a **professional lab report** for cybersecurity.



## 📌 Summary

This lab showed how **Nmap** is used to detect open ports, analyze running services, and evaluate their vulnerabilities. It reinforced the importance of **port scanning, vulnerability management, and hardening systems** in real-world cybersecurity.

 

| Port            | Service       | Purpose                        | Risks / Vulnerabilities                                        | Mitigation                                                              |
| --------------- | ------------- | ------------------------------ | -------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **21/tcp**      | FTP           | File transfers                 | Anonymous login, cleartext credentials, brute-force attacks    | Disable anonymous FTP, use SFTP/FTPS, or uninstall FTP server           |
| **22/tcp**      | SSH           | Secure remote login            | Brute-force attacks, weak keys, misconfiguration               | Use key-based auth, disable root login, update OpenSSH, enable fail2ban |
| **23/tcp**      | Telnet        | Remote CLI (unencrypted)       | Cleartext credentials, eavesdropping, replay attacks           | Remove Telnet, replace with SSH                                         |
| **631/tcp/udp** | IPP (CUPS)    | Network printing               | Remote code execution (CVE-2024-47176 etc.), DoS, info leakage | Patch CUPS, restrict to localhost, disable if unused                    |
| **123/udp**     | NTP           | Time synchronization           | Amplification DDoS, DoS, exploitation of outdated ntpd         | Block public access, patch NTP, disable monlist/mode7                   |
| **5353/udp**    | mDNS/Zeroconf | Local device/service discovery | DoS, spoofing, cache poisoning, info disclosure                | Patch Avahi/Bonjour, restrict to LAN, disable if unused                 |


[click here to downolad file  ](
