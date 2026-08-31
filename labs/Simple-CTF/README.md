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
------First flag and second flag
<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/d5efae81-ea4d-4b66-b03b-30943abdd557" />











------Third flag
<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/b3740506-79d5-4905-8690-41f28e831bcc" />
<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/247c5803-d806-4cff-ab35-f31590b404ce" />
<img width="1890" height="941" alt="image" src="https://github.com/user-attachments/assets/b7a20af1-6dcf-4d6d-ace5-3d0b8c0c78c8" />













# Lessons Learned

This room reinforced the importance of systematic enumeration before exploitation. It demonstrated how careful reconnaissance, service enumeration, and privilege escalation techniques are combined during a penetration testing engagement while emphasizing ethical and authorized security testing.
