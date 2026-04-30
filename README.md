<p align="left">
  <img src="https://img.shields.io/badge/Hack_The_Box-CCTV-red?style=for-the-badge&labelColor=black" />
  <img src="https://img.shields.io/badge/Difficulty-Easy-green?style=for-the-badge&labelColor=black" />
  <img src="https://img.shields.io/badge/OS-Linux-blue?style=for-the-badge&labelColor=black" />
  <img src="https://img.shields.io/badge/Pwn_Date-April_2026-purple?style=for-the-badge&labelColor=black" />
</p>

# Hack The Box - CCTV Machine

## 📋 Executive Summary

This penetration test successfully compromised the CCTV machine by chaining multiple vulnerabilities. The assessment began with external reconnaissance and resulted in full root access. The attack vector exploited weak authentication mechanisms, SQL injection, and command injection vulnerabilities.

## 🏆 Flags Captured

| Flag | Hash |
|------|------|
| **User Flag** | `35485441621d3a1bf9b53966cf6e2d0` |
| **Root Flag** | `69507708250a83de49358aee134c758f` |

## 🔴 Vulnerabilities Exploited

| CVE | Component | Description | CVSS | Severity |
|-----|-----------|-------------|------|----------|
| CVE-2024-51482 | ZoneMinder | Time-based Blind SQL Injection in `tid` parameter | 7.5 | High |
| CVE-2025-60787 | motionEye | OS Command Injection via Snapshot Filename field | 8.8 | High |

## 📋 Attack Chain

| Phase | Technique | Details |
|-------|-----------|---------|
| 1 | **Information Gathering** | Nmap scan revealed ports 22 (SSH) and 80 (HTTP) |
| 2 | **Initial Access** | ZoneMinder authentication bypass using common credentials |
| 3 | **Database Exploitation** | Time-based blind SQL injection (CVE-2024-51482) |
| 4 | **Credential Extraction** | Dumped `zm.Users` table containing bcrypt hashes |
| 5 | **Password Cracking** | John the Ripper cracked `mark` user hash |
| 6 | **Lateral Movement** | SSH access established as user `mark` |
| 7 | **Internal Reconnaissance** | Discovered motionEye service on localhost:8765 |
| 8 | **Service Tunneling** | SSH port forwarding to access internal motionEye |
| 9 | **Privilege Escalation** | OS command injection via motionEye (CVE-2025-60787) |
| 10 | **Full Compromise** | Reverse shell obtained with root privileges |
| 11 | **Objective Complete** | User and root flags captured |

## 🛠️ Tools Used

| Category | Tools |
|----------|-------|
| **Reconnaissance** | Nmap |
| **Web Exploitation** | sqlmap |
| **Password Cracking** | John the Ripper |
| **Lateral Movement** | SSH |
| **Tunneling** | SSH Port Forwarding |
| **Payload Delivery** | curl |
| **Reverse Shell** | Netcat |

## 📁 Repository Contents

| Path | Description |
|------|-------------|
| `Screenshots/` | 20+ evidence screenshots documenting each phase |
| `PENETRATION TEST REPORT.pdf` | Comprehensive professional report |

## 📸 Evidence

All screenshots are available in the [`Screenshots/`](Screenshots) directory, including:
- Network reconnaissance and port scanning
- Web application enumeration
- SQL injection exploitation
- Credential extraction and cracking
- SSH access and internal enumeration
- motionEye exploitation
- Root shell capture
- Flag extraction

## ✅ Key Findings & Recommendations

| Finding | Impact | Recommendation |
|---------|--------|----------------|
| Weak authentication credentials | Complete system access | Implement strong password policy |
| SQL injection vulnerability | Database compromise | Use parameterized queries, update ZoneMinder |
| Internal service exposure | Attack surface expansion | Restrict localhost services with firewall |
| Command injection in motionEye | Root privilege escalation | Update motionEye, implement input validation |

## 🔗 Connect with Me

[![GitHub](https://img.shields.io/badge/GitHub-bimalbist07-black?logo=github&style=for-the-badge)](https://github.com/bimalbist07)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Bimal_Bist-blue?logo=linkedin&style=for-the-badge)](https://www.linkedin.com/in/bimal-bist-98a324315/)

---

*This assessment was conducted on Hack The Box for educational purposes. All techniques demonstrated are part of authorized security testing.*
