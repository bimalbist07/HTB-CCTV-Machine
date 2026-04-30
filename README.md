![HTB](https://img.shields.io/badge/Hack_The_Box-CCTV-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green?style=for-the-badge)
![OS](https://img.shields.io/badge/OS-Linux-blue?style=for-the-badge)
![Date](https://img.shields.io/badge/Pwn_Date-April_2026-purple?style=for-the-badge)

# Hack The Box - CCTV Machine

## 🏆 Flags Captured

| Flag | Value |
|------|-------|
| **User Flag** | `35485441621d3a1bf9b53966cf6e2d0` |
| **Root Flag** | `69507708250a83de49358aee134c758f` |

## 🔴 Vulnerabilities Exploited

| CVE | Description | Severity |
|-----|-------------|----------|
| CVE-2024-51482 | ZoneMinder Time-based Blind SQL Injection | High |
| CVE-2025-60787 | motionEye OS Command Injection | High |

## 📋 Attack Chain
Default Credentials (admin:admin)
↓
SQL Injection (CVE-2024-51482)
↓
Extracted User Hashes
↓
Password Cracking (opensesame)
↓
SSH Access as 'mark'
↓
Internal Enumeration (motionEye)
↓
SSH Tunneling
↓
Command Injection (CVE-2025-60787)
↓
🔴 ROOT Shell
↓
✅ Flags Captured

text

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **Nmap** | Port scanning & reconnaissance |
| **sqlmap** | SQL injection exploitation |
| **John the Ripper** | Password hash cracking |
| **SSH** | Remote access & tunneling |
| **Netcat** | Reverse shell listener |
| **curl** | HTTP requests & API interaction |

## 📁 Files in this Repository

| File/Folder | Description |
|-------------|-------------|
| `Screenshots/` | 20+ evidence screenshots |
| `PENETRATION TEST REPORT.pdf` | Full professional report |

## 📸 Screenshots Preview

All 20+ screenshots are available in the [`Screenshots/`](Screenshots) folder including:
- Nmap scan results
- ZoneMinder login and dashboard
- SQL injection with sqlmap
- SSH access and internal enumeration
- motionEye login and command injection
- Reverse shell and root access
- Flags captured

## ✅ Key Takeaways

- **Default credentials** are extremely dangerous and should never persist
- **SQL injection** can expose sensitive data even when blind
- **Internal services** bound to localhost are not safe after SSH access
- **Command injection** leads to full system compromise
- Security requires **defense in depth**

## 🔗 Connect with Me

[![GitHub](https://img.shields.io/badge/GitHub-bimalbist07-black?logo=github&style=for-the-badge)](https://github.com/bimalbist07)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Bimal_Bist-blue?logo=linkedin&style=for-the-badge)](https://www.linkedin.com/in/bimal-bist-98a324315/)

---

*This machine was completed as part of ethical hacking training on Hack The Box.*
