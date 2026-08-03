# REPORT.md

# Three-Way Handshake Deep Analysis & Network Investigation Report

> **Project Type:** Cyber Security / Networking Analysis  
> **Level:** Beginner to Intermediate  
> **Author:** Mudasir Zia  
> **Status:** Completed  
> **Purpose:** Educational & Defensive Learning

---

# Project Overview

This project documents my practical study and investigation of the TCP Three-Way Handshake.

Instead of only learning the theory, I analyzed the communication process, validated IP addresses, investigated network reputation, verified routing paths, checked threat intelligence sources, and documented the entire process with screenshots.

The goal of this project is to understand how TCP communication begins before any actual data transfer takes place and how a security analyst can investigate communicating hosts using multiple security intelligence platforms.

This report serves as the complete documentation of the project.

---

# Learning Objectives

- Understand TCP communication
- Learn how TCP establishes reliable connections
- Analyze SYN, SYN-ACK and ACK packets
- Understand client/server communication
- Learn packet sequence
- Investigate source and destination IPs
- Validate routing paths
- Perform reputation analysis
- Use multiple threat intelligence platforms
- Document investigation like a SOC Analyst

---

# Technologies Used

- TCP/IP
- Wireshark
- Windows Command Prompt
- Ping
- Tracert
- VirusTotal
- Cisco Talos Intelligence
- Shodan
- Public IP Reputation Services

---

# Project Workflow

```
Capture Traffic
        │
        ▼
Identify TCP Session
        │
        ▼
Locate SYN Packet
        │
        ▼
Locate SYN-ACK Packet
        │
        ▼
Locate ACK Packet
        │
        ▼
Confirm Three-Way Handshake
        │
        ▼
Investigate Source IP
        │
        ▼
Investigate Destination IP
        │
        ▼
Validate Connectivity
        │
        ▼
Perform Threat Intelligence Analysis
        │
        ▼
Document Findings
```

---

# Understanding TCP Three-Way Handshake

TCP uses a three-step process before transmitting any application data.

---

## Step 1 — SYN

The client initiates communication by sending a SYN packet to the server.

Purpose:

- Request connection
- Synchronize sequence numbers
- Begin TCP session

### Screenshot

```
images/sync.png
```

---

## Step 2 — SYN-ACK

The server responds with a SYN-ACK packet.

Purpose:

- Acknowledge client request
- Send its own synchronization request
- Confirm willingness to establish connection

### Screenshot

```
images/sync_async.png
```

---

## Step 3 — ACK

The client sends the final ACK packet.

Purpose:

- Confirm server response
- Complete connection establishment
- Allow data transmission

### Screenshot

```
images/ack.png
```

---

# Complete Three-Way Handshake

The entire communication can be visualized as:

```
Client                          Server

SYN ---------------------------->

          <---------------------- SYN + ACK

ACK ---------------------------->

Connection Established
```

### Screenshot

```
images/3_way-handshake.png
```

---

# Source IP Investigation

After identifying the TCP session, the source IP address was investigated.

Objectives:

- Verify legitimacy
- Confirm ownership
- Identify reputation
- Detect malicious history
- Understand communication origin

### Screenshot

```
images/src_ip_prove.png
```

---

# Destination IP Investigation

The destination IP underwent multiple validation stages.

The investigation included:

- IP ownership
- Public exposure
- Reputation checks
- Routing validation
- Reachability
- Threat intelligence

---

## Destination Investigation — Part 1

```
images/dest_ip_prove1.png
```

---

## Destination Investigation — Part 2

```
images/dest_ip_prove2.png
```

---

## Destination Investigation — Part 3

```
images/dest_ip_prove3.png
```

---

## Destination Investigation — Part 4

```
images/dest_ip_prove4.png
```

---

## Destination Investigation — Part 5

```
images/dest_ip_prove5.png
```

---

# Connectivity Validation

Before trusting communication, connectivity was validated.

## Ping Test

Purpose:

- Verify host availability
- Measure latency
- Confirm reachability

### Screenshot

```
images/ping_on_dest_ip.png
```

---

## Traceroute

Purpose:

- Observe routing path
- Count network hops
- Detect routing anomalies
- Understand packet journey

### Screenshot

```
images/tracert_on_dest_ip.png
```

---

# VirusTotal Investigation

VirusTotal was used to inspect the investigated IP.

Checks included:

- Community reputation
- Vendor detections
- Malicious reports
- Network indicators
- Historical observations

---

## VirusTotal Result 1

```
images/virustotal_1.png
```

---

## VirusTotal Result 2

```
images/virustotal_2.png
```

---

## VirusTotal Result 3

```
images/virustotal_3.png
```

---

# Cisco Talos Intelligence Investigation

Cisco Talos Intelligence provides reputation and threat intelligence for IP addresses.

Objectives:

- Reputation
- Classification
- Threat score
- Security history

### Screenshot

```
images/taleos_intellegence.png
```

---

# Shodan Investigation

Shodan was used to determine whether the destination host exposed internet-facing services.

The investigation focused on:

- Open ports
- Running services
- Public fingerprints
- Network banners
- Device exposure
- Potential attack surface

---

## Shodan Result 1

```
images/shodan_1.png
```

---

## Shodan Result 2

```
images/shodan_2.png
```

---

## Shodan Result 3

```
images/shodan_3.png
```

---

## Shodan Result 4

```
images/shodan_4.png
```

---

# Security Analysis

During this project the communication process was validated from multiple perspectives.

The analysis included:

- TCP connection establishment
- Packet sequence verification
- Source IP validation
- Destination IP verification
- Connectivity confirmation
- Route analysis
- Threat intelligence review
- Public exposure assessment

Rather than relying on a single source, multiple intelligence platforms were consulted to build confidence in the investigation.

---

# Skills Demonstrated

- TCP/IP Fundamentals
- Network Packet Analysis
- Wireshark Investigation
- Three-Way Handshake Analysis
- Threat Intelligence
- IP Reputation Analysis
- OSINT Investigation
- Network Troubleshooting
- Ping Analysis
- Traceroute Analysis
- Cisco Talos Usage
- VirusTotal Investigation
- Shodan Enumeration
- Technical Documentation

---

# Key Takeaways

This project reinforced the importance of understanding how TCP establishes reliable communication before application data is exchanged.

Beyond packet analysis, it demonstrated how a security analyst can validate network communications through independent verification methods, reputation analysis, and publicly available threat intelligence.

The investigation combined protocol analysis with defensive security practices, creating a structured workflow that closely resembles the investigation process followed by entry-level SOC analysts.

---

# Repository Structure

```
.
├── images/
│   ├── 3_way-handshake.png
│   ├── ack.png
│   ├── sync.png
│   ├── sync_async.png
│   ├── src_ip_prove.png
│   ├── dest_ip_prove1.png
│   ├── dest_ip_prove2.png
│   ├── dest_ip_prove3.png
│   ├── dest_ip_prove4.png
│   ├── dest_ip_prove5.png
│   ├── ping_on_dest_ip.png
│   ├── tracert_on_dest_ip.png
│   ├── virustotal_1.png
│   ├── virustotal_2.png
│   ├── virustotal_3.png
│   ├── taleos_intellegence.png
│   ├── shodan_1.png
│   ├── shodan_2.png
│   ├── shodan_3.png
│   └── shodan_4.png
├── REPORT.md
└── README.md
```

---

# Conclusion

This project successfully demonstrates the TCP Three-Way Handshake from both a networking and cyber security perspective.

The work goes beyond explaining SYN, SYN-ACK, and ACK packets by validating real-world communication through packet analysis, IP investigation, routing verification, and multiple threat intelligence platforms.

It reflects practical defensive analysis skills that are relevant to SOC analysts, blue team practitioners, networking students, and anyone beginning their journey in cyber security.