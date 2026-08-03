# DNS in Detail

## Room Information

- **Platform:** TryHackMe
- **Room:** DNS in Detail
- **Difficulty:** Easy
- **Category:** Networking / DNS

---

# Objective

The objective of this room was to understand how the Domain Name System (DNS) works, how domain names are translated into IP addresses, and the different types of DNS records used in modern networks.

---

# Topics Covered

- What is DNS?
- Domain Names
- DNS Hierarchy
- Root DNS Servers
- Top-Level Domains (TLDs)
- Authoritative Name Servers
- Recursive Resolver
- Recursive vs Iterative Queries
- DNS Cache
- DNS Records

---

# DNS Record Types

| Record | Purpose |
|---------|---------|
| A | Maps a domain to an IPv4 address |
| AAAA | Maps a domain to an IPv6 address |
| CNAME | Creates an alias for another domain |
| MX | Specifies the mail server for a domain |
| TXT | Stores text information (SPF, DKIM, verification, etc.) |
| NS | Identifies the authoritative name servers |
| SOA | Contains administrative information about the DNS zone |

---

# Commands Practiced

```bash
nslookup google.com

dig google.com

dig google.com MX

dig google.com NS

dig google.com TXT

host google.com
```

---

# Key Learnings

- DNS converts human-readable domain names into IP addresses.
- Every DNS request follows a hierarchical lookup process.
- Recursive resolvers cache responses to improve performance.
- Different DNS records serve different purposes.
- DNS is a critical component of modern networking.

---

# Skills Gained

- DNS Fundamentals
- Domain Resolution
- DNS Record Analysis
- Linux Networking
- DNS Troubleshooting

---

<img width="1912" height="502" alt="Dns" src="https://github.com/user-attachments/assets/49fa358d-5dfc-4218-a32d-7ad046c5d3c4" />


## Room Completion


---

# Lessons Learned

This room strengthened my understanding of how DNS functions behind the scenes and why it is one of the most important services in networking and cybersecurity.
