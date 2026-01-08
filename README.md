# SIEM: Detection of Anomalies Using Snort
Detecting SQL injection and Nmap scanning using Snort IDS in a controlled lab environment

---

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

## 🖼️ Screenshots

### Environment Setup

![Ubuntu Setup](screenshots/Ubuntu%20setup.png)
*Figure 1: Ubuntu environment setup for Snort deployment.*

![Kali Setup](screenshots/kali%20setup1.png)
*Figure 2: Kali Linux setup used for attack simulation.*

![Kali Setup Continued](screenshots/kali%20setup2.png)
*Figure 3: Additional Kali Linux configuration.*

![Metasploitable2 Setup](screenshots/Metasploitable2%20setup.png)
*Figure 4: Metasploitable2 vulnerable machine setup.*

---

### Snort Installation & Configuration

![Snort Version](screenshots/Snort%20version.png)
*Figure 5: Verification of installed Snort version.*

![Configuration Validation](screenshots/Config%20validation.png)
*Figure 6: Initial Snort configuration validation.*

![Configuration Validation Continued](screenshots/config%20validation2.png)
*Figure 7: Successful Snort configuration check.*

---

### Custom Rule Creation

![SQL Injection Rules](screenshots/SQL%20injection%20rules.png)
*Figure 8: Custom Snort rules for SQL injection detection.*

![Nmap Scan Rules](screenshots/nmap%20scan%20rules.png)
*Figure 9: Custom Snort rules for Nmap scan detection.*

---

### Attack Simulation & Alerts

![Attack Test 1](screenshots/Attack%20test1.png)
*Figure 10: Initial attack testing phase.*

![Attack Test 2](screenshots/Attack%20test2.png)
*Figure 11: Continued attack simulation.*

![SQL Injection Test 1](screenshots/sql%20injection1.png)
*Figure 12: SQL injection payload attempt.*

![SQL Injection Test 2](screenshots/sql%20injection2.png)
*Figure 13: Additional SQL injection attempt.*

![SQL Injection Test 3](screenshots/sql%20injection3.png)
*Figure 14: Final SQL injection test.*

![SQL Injection Alert](screenshots/sql%20alert.png)
*Figure 15: Snort alert triggered by SQL injection activity.*

![Nmap Alert](screenshots/nmap%20alert.png)
*Figure 16: Snort alert triggered by Nmap scanning activity.*

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
- `/screenshots` → Setup, attack simulation, and alert evidence
- `/logs` → Sample Snort alert logs (sanitized)

---

## 📚 References
- Snort Documentation
- OWASP Top 10
- Nmap Official Documentation
