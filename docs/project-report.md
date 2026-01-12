# Project Report: SIEM – Detection of Anomalies Using Snort

**Detecting SQL Injection Attacks and Nmap Reconnaissance Scans**

**Date:** January 2026

## 1. Introduction

This project demonstrates the practical deployment of **Snort**, a widely used open-source Network Intrusion Detection System (NIDS), for real-time detection of two common network threats:

- **SQL Injection** attacks targeting web applications
- **Nmap** reconnaissance scanning activity

The work was carried out in a fully controlled virtual lab environment. Custom Snort rules were developed, tested, and iteratively refined to achieve reliable detection with minimal false positives.

## 2. Lab Architecture

**Virtual Machines:**

| Role              | OS                     | IP Address         | Purpose                              |
|-------------------|------------------------|--------------------|--------------------------------------|
| Snort IDS         | Ubuntu Server 24.04    | 192.168.206.29     | Traffic monitoring & rule evaluation |
| Attacker          | Kali Linux 2024.2      | 192.168.206.235    | Attack simulation                    |
| Victim            | Metasploitable 2       | 192.168.206.239    | Vulnerable target (OWASP Mutillidae) |

- Network: `192.168.206.0/24`
- Adapter type: Bridged
- Snort monitoring interface: `enp0s3` (promiscuous mode enabled)

## 3. Tools & Technologies

- **Snort** version 2.9.20
- Ubuntu Server 24.04 LTS
- Kali Linux 2024.2
- Metasploitable 2 (vulnerable target)
- Nmap (port scanning & version detection)
- OWASP Mutillidae II (vulnerable web application)

## 4. Snort Installation & Configuration

Snort was installed via the package manager and configured as follows:

- Running in **NIDS mode**
- Interface set to promiscuous
- Custom rules file (`local.rules`) included in `snort.conf`
- Configuration validated using:  
  `sudo snort -T -c /etc/snort/snort.conf`

## 5. Custom Rule Development

### 5.1 SQL Injection Detection Rules

Targeted common SQLi patterns including:

- Keyword abuse: `SELECT`, `UNION`
- Tautologies: `OR 1=1`
- Comments: `--`, `/* */`
- Dangerous commands: `DROP`, `INSERT`, `UPDATE`, `DELETE`
- Time-based: `SLEEP()`
- Hex/encoding evasion attempts

### 5.2 Nmap Scan Detection Rules

Covered the most popular Nmap scan types:

- TCP SYN (`-sS`)
- TCP FIN (`-sF`)
- TCP NULL (`-sN`)
- TCP Xmas (`-sX`)
- UDP scan (`-sU`)
- Version detection (`-sV`)

## 6. Attack Simulation Methodology

- **SQL Injection:** Multiple payloads were manually injected via browser and `sqlmap` against Mutillidae
- **Nmap Scanning:** Various scan types executed from Kali:
  - `nmap -sS`, `-sF`, `-sN`, `-sX`, `-sU`, `-sV`, `-A`

## 7. Detection Results

Snort successfully triggered alerts for **all** simulated attacks.

**Alert characteristics observed:**

- Accurate source/destination IP identification
- Rule SID matching
- Payload snippets in alerts
- Timestamps and protocol details

**Detection success rate:** 100% for the tested attack patterns.

## 8. Limitations

- Purely signature-based → cannot detect novel/zero-day attacks
- Potential false positives in high-traffic or legitimate heavy SQL environments
- Performance degradation possible without optimization on high-speed links

## 9. Recommendations & Future Improvements

- Integrate Snort with a SIEM (ELK Stack, Splunk, Graylog) for correlation and visualization
- Add rules for malware C2, DDoS patterns, and credential stuffing
- Implement rule testing automation
- Explore machine learning-based anomaly detection as a complementary layer

## 10. Conclusion

This project successfully demonstrates that **Snort**, when equipped with well-crafted custom rules, remains an effective, lightweight, and highly customizable solution for detecting common web application attacks and network reconnaissance in small-to-medium environments.

Proper rule tuning and periodic validation are key to maintaining detection quality.

---
**End of Report**
