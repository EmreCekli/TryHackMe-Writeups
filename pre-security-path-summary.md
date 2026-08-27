# TryHackMe — Pre Security Path

**Platform:** TryHackMe
**Path:** Pre Security
**Date:** August 2026
**Status:** Completed ✅

---

## Overview

The Pre Security path covers the foundational knowledge required before starting offensive-security-focused training (Jr Penetration Tester path). It spans networking fundamentals, operating systems, virtualisation, cloud computing, and core security concepts.

---

## Rooms Completed

- Linux Fundamentals (Part 1, 2, 3)
- What is Networking?
- Packets & Frames
- OS Introduction
- Virtualisation Basics
- Cloud Computing
- Guided Web Pentest (IDOR → Weak Password Reset → File Upload Bypass → RCE — full writeup: [guided-pentest-web.md](./guided-pentest-web.md))

---

## Key Concepts

### CIA Triad

| Attack | Component Affected |
|---|---|
| Ransomware | Availability |
| Trojan | Confidentiality + Integrity |
| IDOR | Confidentiality |
| Log deletion | Integrity |
| ARP Spoofing | Confidentiality + Integrity |
| DDoS | Availability |

### Networking

- **IP addressing:** 4 octets (0-255 each), private (`192.168.x.x`) vs. public ranges.
- **MAC addressing:** 12 hex characters — first 6 identify the vendor, last 6 the device.
- **ARP:** resolves IP → MAC within a local network; poisoning the ARP cache enables man-in-the-middle attacks.
- **TCP vs UDP:** TCP is connection-oriented (3-way handshake: SYN → SYN-ACK → ACK), reliable, used for HTTP/email/FTP. UDP is connectionless, faster, used for DNS/video/gaming.
- **OSI Model** — each layer maps to distinct classes of vulnerabilities:

| Layer | Name | Example Vulnerability |
|---|---|---|
| 7 | Application | XSS, SQLi, IDOR |
| 6 | Presentation | SSL Stripping |
| 5 | Session | Session Hijacking |
| 4 | Transport | Port scanning, SYN flood |
| 3 | Network | IP Spoofing |
| 2 | Data Link | ARP/MAC Spoofing |
| 1 | Physical | Physical access |

### Operating Systems

- Kernel space vs. user space separation.
- Core OS responsibilities: process management, memory management, file system management, user management, device management.
- Security fundamentals: authentication, permission systems, process isolation.

### Virtualisation & Cloud

- **Hypervisor Type 1** (bare-metal, e.g. ESXi) vs. **Type 2** (hosted, e.g. VirtualBox/UTM — runs as an application on top of an existing OS).
- **Service models:** IaaS (raw infrastructure, e.g. AWS EC2), PaaS (managed runtime, e.g. Heroku), SaaS (finished product, e.g. Gmail).
- **Deployment models:** Public (shared infrastructure), Private (dedicated), Hybrid (mix — sensitive data kept private, less critical workloads on public cloud for cost/scalability).

---

## Why This Matters

These fundamentals directly inform offensive-security work: understanding OSI layers clarifies where different attack classes operate, understanding TCP/UDP explains why tools like `nmap` scan them differently, and understanding virtualisation/cloud models explains how real-world infrastructure (and its attack surface) is actually deployed.

---

*TryHackMe profile: [tryhackme.com/p/cekliemre](https://tryhackme.com/p/cekliemre)*
