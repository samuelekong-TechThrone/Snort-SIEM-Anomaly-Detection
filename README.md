# SIEM: Anomaly Detection Using Snort

**Detecting SQL Injection and Nmap Scanning in a Controlled Lab Environment**

![Snort Alert Example](screenshots/sql%20alert.png)

## Overview

This project demonstrates how to deploy **Snort** (open-source Network Intrusion Detection System) on Ubuntu to detect common web attacks and reconnaissance activity:

- **SQL Injection** attempts (UNION SELECT, OR 1=1, comments, etc.)
- **Nmap scanning** techniques (SYN, FIN, NULL, Xmas, UDP, version detection)

Custom rules were developed, tested, and validated in a realistic lab setup using real attack simulations.

## 🎯 Objectives

- Deploy and configure Snort IDS on Ubuntu 24.04
- Write effective custom detection rules
- Simulate realistic attacks using Kali Linux
- Validate detection through alert analysis

## 🧪 Lab Environment

| Role           | Operating System       | IP Address         |
|----------------|------------------------|--------------------|
| IDS (Snort)    | Ubuntu 24.04           | 192.168.206.29     |
| Attacker       | Kali Linux 2024.2      | 192.168.206.235    |
| Victim         | Metasploitable 2       | 192.168.206.239    |

**Network:** `192.168.206.0/24` (Bridged)  
**Snort listening interface:** `enp0s3` (promiscuous mode)

## 🛠️ Tools & Technologies

- Snort 2.9.20
- Ubuntu Server 24.04
- Kali Linux 2024.2
- Metasploitable 2
- Nmap
- OWASP Mutillidae (vulnerable web app)

## Key Detection Capabilities

**SQL Injection**  
• UNION SELECT  
• OR 1=1 blind  
• SQL comments (`--`, `/* */`)  
• Dangerous keywords (`DROP`, `INSERT`, `UPDATE`)

**Nmap Scans**  
• TCP SYN  
• FIN / NULL / Xmas  
• UDP  
• Version detection

## Results Summary

All simulated attacks were successfully detected with appropriate Snort alerts containing:
- Timestamp
- Source & destination IPs
- Rule SID
- Packet details

## 📂 Repository Structure
