# SIEM: Detection of Anomalies Using Snort
## Detailed Project Report

---

## 1. Introduction
This report documents the deployment of Snort as a Network Intrusion Detection System (NIDS) for detecting SQL injection attacks and Nmap scanning activity within a controlled lab environment.

The objective was to design, implement, and validate custom detection rules capable of identifying malicious network behavior in real time.

---

## 2. Lab Architecture
The lab consisted of three virtual machines configured on a bridged network:

- Ubuntu 24.04 – Snort IDS
- Kali Linux – Attacker machine
- Metasploitable 2 – Vulnerable target

All systems operated within the `192.168.206.0/24` network range.

---

## 3. Tools & Technologies
- Snort 2.9.20
- Ubuntu Server 24.04
- Kali Linux 2024.2
- Metasploitable 2
- Nmap
- OWASP Mutillidae

---

## 4. Snort Installation & Configuration
Snort was installed on Ubuntu and configured to operate in promiscuous mode. Custom rules were enabled by including the `local.rules` file in the Snort configuration.

Configuration validation was performed to ensure rule integrity and syntax correctness before live testing.

---

## 5. Custom Rule Development
Custom Snort rules were written to detect:

### 5.1 SQL Injection
- Keyword-based detection (`SELECT`, `UNION`)
- Boolean-based injection (`OR 1=1`)
- Comment-based evasion (`--`)
- Time-based techniques (`SLEEP()`)

### 5.2 Nmap Scanning
- TCP SYN scans
- FIN, NULL, and Xmas scans
- UDP scans
- Version detection and OS fingerprinting

---

## 6. Attack Simulation & Testing
SQL injection attempts were executed from the attacker machine against the vulnerable application hosted on Metasploitable 2.

Nmap was used to perform multiple reconnaissance scans against the target system to test rule effectiveness.

---

## 7. Detection & Results
Snort successfully generated alerts for all simulated SQL injection attempts and Nmap scans. Alerts included timestamps, source IP addresses, destination IPs, and rule identifiers.

---

## 8. Limitations
- Signature-based detection may miss zero-day attack patterns
- High traffic environments may require performance tuning
- False positives are possible without context-aware analysis

---

## 9. Future Improvements
- Integration with a SIEM platform for centralized analysis
- Expansion of detection rules for malware and DDoS traffic
- Automation of rule updates

---

## 10. Conclusion
This project demonstrates the effectiveness of Snort as a lightweight IDS for detecting common web attacks and reconnaissance activity when properly configured with custom rules.
