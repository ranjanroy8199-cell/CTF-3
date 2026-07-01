# CTF-3
This is my write-up for the WestWild Edited CTF, done as a lab exercise on Kali against a target VM. I've tried  to keep the steps in the order I actually did them, including a couple of dead ends, instead of just writing a clean  version after the fact. 
# WestWild Edited CTF Write-up

## Overview
This repository contains my complete walkthrough of the **WestWild Edited Capture The Flag (CTF)** machine. The assessment was performed in a controlled lab environment using **Kali Linux** as the attacking machine against an **Ubuntu-based target VM**.

The objective was to perform reconnaissance, enumerate available services, exploit misconfigurations, escalate privileges, and obtain root access by capturing the available flags.

---

## Environment

- **Attacker Machine:** Kali Linux
- **Target Machine:** WestWild VM (Ubuntu)
- **Virtualization:** VMware Workstation
- **Network:** Isolated NAT
- **Services Identified:**
  - SSH (22)
  - HTTP (80)
  - SMB (139, 445)

---

## Objectives

- Discover the target machine
- Enumerate exposed services
- Exploit SMB misconfigurations
- Gain initial access via SSH
- Perform privilege escalation
- Capture all accessible flags
- Document the complete attack process

---

## Tools Used

- Nmap
- ARP Scan
- Enum4linux
- SMBClient
- SSH
- Base64
- Find
- Linux Commands

---

## Attack Path

### Phase 1 – Reconnaissance
- Discovered the target IP using ARP scan.
- Performed an aggressive Nmap scan.
- Identified SSH, HTTP, and SMB services.

### Phase 2 – SMB Enumeration
- Used Enum4linux to enumerate:
  - Users
  - Shares
  - Password policy
  - Anonymous login support

### Phase 3 – SMB Exploitation
- Connected to the anonymous SMB share.
- Retrieved:
  - Flag 1
  - Username
  - Password

### Phase 4 – Initial Access
- Logged into the target using SSH with the leaked credentials.

### Phase 5 – Privilege Escalation
- Enumerated writable directories.
- Located a script containing another user's credentials.
- Switched to the second user.
- Escalated privileges using sudo.

### Phase 6 – Root Access
- Successfully obtained root privileges.
- Retrieved Flag 2.

### Phase 7 – Post Exploitation
- Investigated the system for additional flags.
- Verified that only two legitimate flags were discovered.

---

## Skills Demonstrated

- Network Reconnaissance
- Service Enumeration
- SMB Enumeration
- Credential Discovery
- Password Reuse Exploitation
- SSH Authentication
- Linux Privilege Escalation
- Post-Exploitation Enumeration
- Technical Documentation

---

## Key Findings

- Anonymous SMB access was enabled.
- Sensitive credentials were stored in plaintext.
- Password reuse enabled lateral movement.
- Writable directories exposed sensitive information.
- Weak security practices resulted in full system compromise.

---

## Lessons Learned

- Always disable anonymous SMB access.
- Never store credentials in plaintext.
- Enforce strong password policies.
- Avoid password reuse.
- Restrict permissions on sensitive directories.
- Regularly audit file permissions and services.

---

## Outcome

- ✅ Initial Access Obtained
- ✅ User Shell Obtained
- ✅ Privilege Escalation Successful
- ✅ Root Access Achieved
- ✅ Flag 1 Captured
- ✅ Flag 2 Captured

---

## Repository Contents

```
├── README.md
├── WestWild_Edited_CTF_Report.pdf
└── Screenshots/
```

---

## Disclaimer

This project was completed in a **legal, isolated lab environment** for educational and cybersecurity training purposes only. The techniques demonstrated should only be used on systems where explicit authorization has been granted.

---

## Author

**Ranjan Kumar Roy**

MCA Student | Cybersecurity Enthusiast

---
