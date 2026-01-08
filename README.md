# Snort-SIEM-Anomaly-Detection
Detecting SQL injection and Nmap scanning using Snort IDS in a controlled lab environment
# SIEM: Detection of Anomalies Using Snort

## 🔍 Project Overview
This project demonstrates the deployment of **Snort**, an open-source Network Intrusion Detection System (NIDS), on an Ubuntu machine to detect **SQL injection attacks** and **Nmap scanning probes** in real time.

The goal was to design, implement, and test custom Snort rules capable of identifying malicious network behavior within a controlled lab environment.

---

## 🎯 Objectives
- Deploy Snort IDS on Ubuntu 24.04
- Create custom detection rules for:
  - SQL Injection attacks
  - Nmap reconnaissance scans
- Simulate attack traffic from an attacker machine
- Analyze alerts and refine rules for accuracy

---

## 🧪 Lab Environment
| Role | OS | IP Address |
|----|----|----|
| IDS Monitor | Ubuntu 24.04 | 192.168.206.29 |
| Attacker | Kali Linux 2024.2 | 192.168.206.235 |
| Victim | Metasploitable 2 | 192.168.206.239 |

- Network: `192.168.206.0/24`
- Mode: Bridged Adapter
- Snort Interface: `enp0s3` (Promiscuous Mode Enabled)

---

## 🛠️ Tools & Technologies
- Snort 2.9.20
- Ubuntu Server 24.04
- Kali Linux
- Metasploitable 2
- Nmap
- OWASP Mutillidae

---

## 🚨 Detection Capabilities
### SQL Injection
- `UNION SELECT`
- `OR 1=1`
- `DROP`, `INSERT`, `UPDATE`, `DELETE`
- SQL comments and hexadecimal encoding

### Nmap Scans
- TCP SYN Scan
- FIN Scan
- Null Scan
- Xmas Scan
- UDP Scan
- Version Detection

---

## 📊 Results
- All simulated SQL injection attempts were detected
- Nmap scans triggered appropriate alerts
- Alerts logged with timestamps, source/destination IPs, and rule IDs
- Rule accuracy improved through iterative refinement

---

## 📈 Future Improvements
- SIEM integration for centralized log analysis
- Detection of DDoS and malware traffic
- Automated rule updates
- Performance optimization for large networks

---

## 📂 Repository Contents
- `/rules` → Custom Snort rules
- `/docs` → Detailed documentation
- `/screenshots` → Visual evidence (optional)

---

## 📚 References
- Snort Documentation
- OWASP Top 10
- Nmap Official Docs
