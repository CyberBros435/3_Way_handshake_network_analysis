# 🛡️ TCP Three-Way Handshake — Wireshark Capture & Network Investigation

![Wireshark](https://img.shields.io/badge/Tool-Wireshark-blue?logo=wireshark)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)
![Platform](https://img.shields.io/badge/Platform-Windows-blue)
![Protocol](https://img.shields.io/badge/Protocol-TCP-orange)
![Analysis](https://img.shields.io/badge/Analysis-Network_Forensics-red)

A complete network traffic analysis project demonstrating how a real TCP Three-Way Handshake works using **Wireshark**, followed by an in-depth investigation of the remote IP address using multiple **OSINT** and **Threat Intelligence** platforms.

The project not only explains how a TCP connection is established but also follows a real-world SOC Analyst workflow to verify whether the communicating host is legitimate through independent security validation.

---

# 📖 Full Documentation

Complete investigation report:

```text
report/report.md
```

---

# 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Project Objectives](#-project-objectives)
- [Environment](#-environment)
- [Wireshark Display Filter](#-wireshark-display-filter)
- [TCP Three-Way Handshake](#-tcp-three-way-handshake)
- [Packet Breakdown](#-packet-breakdown)
- [Network Investigation](#-network-investigation)
- [Threat Intelligence Analysis](#-threat-intelligence-analysis)
- [Investigation Summary](#-investigation-summary)
- [Project Workflow](#-project-workflow)
- [Skills Demonstrated](#-skills-demonstrated)
- [Learning Outcomes](#-learning-outcomes)
- [Repository Structure](#-repository-structure)
- [Tools Used](#-tools-used)
- [Author](#-author)

---

# 🎯 Project Overview

| Item | Description |
|------|-------------|
| Project | TCP Three-Way Handshake Analysis |
| Category | Network Security |
| Difficulty | Beginner → Intermediate |
| Tool | Wireshark |
| Local Host | `192.168.0.102` |
| Remote Host | `98.70.192.224` |
| Organization | Microsoft Corporation |
| Cloud Platform | Microsoft Azure |
| Destination | Pune, Maharashtra, India |
| Protocol | TCP |
| Destination Port | 443 (HTTPS) |
| Investigation Status | Completed |

---

# 🎯 Project Objectives

This project was created to:

- Capture a real TCP Three-Way Handshake
- Analyze every TCP control flag
- Understand sequence and acknowledgment numbers
- Verify packet ownership
- Investigate the destination IP
- Validate the host using multiple OSINT sources
- Perform threat intelligence analysis
- Practice professional SOC-style documentation

---

# 💻 Environment

| Component | Value |
|-----------|-------|
| Operating System | Windows |
| Packet Analyzer | Wireshark |
| Network Interface | Wi-Fi |
| Protocol | TCP |
| Service | HTTPS (443) |

---

# 🔍 Wireshark Display Filter

```wireshark
tcp.flags.syn == 1 or (tcp.seq == 1 and tcp.ack == 1 and tcp.len == 0)
```

This filter isolates only the packets involved in the TCP connection establishment process.

---

# 🤝 TCP Three-Way Handshake

```text
Client (192.168.0.102)                    Server (98.70.192.224:443)

        SYN (Seq=0)
---------------------------------------------->

                        SYN + ACK (Seq=0 Ack=1)
<----------------------------------------------

        ACK (Seq=1 Ack=1)
---------------------------------------------->

            TCP CONNECTION ESTABLISHED
```

The handshake consists of three packets:

1. SYN
2. SYN-ACK
3. ACK

Once these packets are exchanged successfully, the TCP session enters the **ESTABLISHED** state and application data transmission can begin.

---

# 📦 Packet Breakdown

| Packet | TCP Flags | Purpose | Key Information |
|---------|-----------|----------|----------------|
| SYN | `0x002` | Client initiates connection | Seq=0, Win=64240, MSS=1460 |
| SYN-ACK | `0x012` | Server acknowledges request | Seq=0, Ack=1, Win=65535, MSS=1440 |
| ACK | `0x010` | Client completes handshake | Seq=1, Ack=1, Window=132352 |

Detailed screenshots and packet analysis are available inside:

```text
report/report.md
```

---

# 🌍 Network Investigation

After confirming the TCP handshake, the destination IP address was investigated using multiple independent verification methods.

Destination IP

```text
98.70.192.224
```

Investigation included:

- WHOIS lookup
- Multi-source geolocation
- Ping testing
- Traceroute analysis
- VirusTotal
- Cisco Talos
- Shodan

---

## WHOIS Verification

Result

```text
Owner

Microsoft Corporation
```

```text
Network Range

98.70.128.0 - 98.70.255.255
```

Ownership was confirmed using ARIN WHOIS records.

---

## Multi-Source Geolocation

The IP address was cross-verified using multiple providers.

Consensus

```text
Organization

Microsoft Corporation
```

```text
Cloud Platform

Microsoft Azure
```

```text
ASN

8075
```

```text
Location

Pune

Maharashtra

India
```

Using multiple providers increases confidence by reducing reliance on a single database.

---

## Connectivity Validation

### Ping

```text
Packet Loss

0%
```

```text
Average Latency

204 ms
```

The destination responded successfully.

---

### Traceroute

```text
18 Network Hops

Successfully Reached Destination
```

Traffic followed expected ISP and Microsoft network infrastructure.

---

# 🛡️ Threat Intelligence Analysis

The destination IP was investigated using multiple threat intelligence platforms.

| Platform | Result |
|----------|--------|
| VirusTotal | 0 detections |
| Cisco Talos | Neutral reputation |
| Shodan | Legitimate Microsoft services |
| WHOIS | Microsoft owned |
| Geolocation | Microsoft Azure |
| Traceroute | Normal routing |
| Ping | Reachable |

---

## VirusTotal

```text
Detections

0 / Multiple Security Vendors
```

No malicious history associated with the IP.

---

## Cisco Talos

```text
Sender Reputation

Neutral
```

```text
Web Reputation

Neutral
```

```text
Blocklists

Clean
```

---

## Shodan

Open Ports

```text
80

443
```

Certificate

```text
Microsoft TLS G2 RSA CA CSP 10
```

Hostnames

```text
*.activity.windows.com

*.roaming.windows.com
```

The certificate and hostnames match legitimate Microsoft cloud infrastructure.

---

# ✅ Investigation Summary

Every independent verification method reached the same conclusion.

| Verification | Status |
|-------------|--------|
| TCP Analysis | ✅ Successful |
| WHOIS | ✅ Microsoft Owned |
| Geolocation | ✅ Microsoft Azure |
| Ping | ✅ Reachable |
| Traceroute | ✅ Legitimate Routing |
| VirusTotal | ✅ Clean |
| Cisco Talos | ✅ Neutral |
| Shodan | ✅ Legitimate TLS Certificate |

---

# 🔄 Project Workflow

```text
Capture Packets
        │
        ▼
Apply Wireshark Filter
        │
        ▼
Identify SYN → SYN-ACK → ACK
        │
        ▼
Analyze TCP Flags
        │
        ▼
Verify Local Source
        │
        ▼
Investigate Destination IP
        │
        ▼
WHOIS Validation
        │
        ▼
Geolocation Verification
        │
        ▼
Ping & Traceroute
        │
        ▼
Threat Intelligence
        │
        ▼
Shodan Investigation
        │
        ▼
Final Security Assessment
```

---

# 💡 Skills Demonstrated

- TCP/IP Fundamentals
- TCP Three-Way Handshake Analysis
- Wireshark Packet Analysis
- TCP Flag Interpretation
- Sequence Number Analysis
- Acknowledgment Number Analysis
- Network Troubleshooting
- Windows Networking
- WHOIS Investigation
- OSINT Investigation
- IP Reputation Analysis
- VirusTotal Investigation
- Cisco Talos Intelligence
- Shodan Reconnaissance
- TLS Certificate Validation
- Network Documentation
- Security Reporting

---

# 📚 Learning Outcomes

Through this project, I learned how to:

- Capture a real TCP Three-Way Handshake.
- Interpret TCP control flags directly from Wireshark.
- Understand TCP sequence and acknowledgment numbers.
- Verify IP ownership using WHOIS.
- Cross-check geolocation using multiple providers.
- Validate host availability using Ping and Traceroute.
- Investigate IP reputation using VirusTotal and Cisco Talos.
- Use Shodan to analyze exposed services and TLS certificates.
- Document a professional network investigation suitable for a cybersecurity portfolio.

---

# 📂 Repository Structure

```text
TCP-Three-Way-Handshake/
│
├── report/
│   └── report.md
│
├── screenshots/
│   ├── 3_way-handshake.png
│   ├── ack.png
│   ├── sync.png
│   ├── sync_async.png
│   ├── w1.png
│   ├── w2.png
│   ├── w3.png
│   ├── w4.png
│   ├── w5.png
│   ├── whois_rsw_on_dest_ip.png
│   ├── ping_on_dest_ip.png
│   ├── tracert_on_dest_ip.png
│   ├── virustotal_1.png
│   ├── virustotal_2.png
│   ├── virustotal_3.png
│   ├── taleos_intellegence.png
│   ├── shodan_1.png
│   ├── shodan_2.png
│   ├── shodan_3.png
│   ├── shodan_4.png
│   ├── dest_ip_prove1.png
│   ├── dest_ip_prove2.png
│   ├── dest_ip_prove3.png
│   ├── dest_ip_prove4.png
│   └── dest_ip_prove5.png
│
└── README.md
```

---

# 🧰 Tools Used

- Wireshark
- Windows Command Prompt
- ARIN WHOIS
- IP Geolocation Services
- Ping
- Traceroute
- VirusTotal
- Cisco Talos Intelligence
- Shodan

---

# 👨‍💻 Author

**Mudasir Zia**

GitHub

```text
https://github.com/CyberBros435
```

LinkedIn

```text
https://linkedin.com/in/mudasir-zia-a535243b5
```

---

⭐ If you found this repository useful, consider giving it a **Star**.
