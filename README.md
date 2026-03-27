# 🔐 Botium Toys Security Audit
## 📄 Full Audit Report
[Download the full security audit](./Botium-Toys-Security-Audit.pdf)


# 🔍 Network Traffic Analysis & Security Incident Investigation

This project demonstrates practical cybersecurity and network analysis skills through real-world case studies involving network disruptions and security incidents.

The analysis focuses on identifying root causes using log data, understanding protocol behavior, and applying security reasoning to diagnose and mitigate issues.

---

## 📄 Full Case Study

👉 [View Full Analysis](./network-traffic-analysis-security-incidents.md)

---


---

## 🧪 Case Study 1: DNS Failure (ICMP Port Unreachable)

### 📌 Scenario
Users were unable to access a website and received a **“destination port unreachable”** error.

### 🔎 Key Findings
- DNS queries were sent over **UDP (port 53)**  
- The DNS server returned **ICMP error messages**  
- Error: `udp port 53 unreachable`  

### 🧠 Root Cause
The DNS server was not responding on port 53, preventing domain name resolution.

### ⚠️ Impact
- Website inaccessible  
- DNS resolution failure  
- Business disruption  

---

## 🚨 Case Study 2: SYN Flood DoS Attack

### 📌 Scenario
A web server became unresponsive due to abnormal traffic patterns.

### 🔎 Key Findings
- High volume of repeated **TCP SYN packets**  
- Traffic from a single IP address (`203.0.113.0`)  
- Incomplete TCP handshakes  
- Increase in:
  - `RST, ACK` responses  
  - `504 Gateway Timeout` errors  

### 🧠 Root Cause
A **SYN flood Denial of Service (DoS) attack** overwhelmed server resources.

### ⚠️ Impact
- Website downtime  
- Failed user connections  
- Server resource exhaustion  

---

## 🧠 Skills Demonstrated

- Network traffic analysis  
- TCP/IP and DNS protocol understanding  
- Packet log interpretation (Wireshark / tcpdump)  
- Incident investigation and root cause analysis  
- Identification of DoS (SYN flood) attacks  
- Cybersecurity reporting and documentation  

---

## 🛠️ Tools & Concepts Used

- Packet analysis (tcpdump / Wireshark)  
- TCP three-way handshake  
- DNS resolution process  
- ICMP error analysis  
- Denial of Service (DoS) attacks  

---

## 🔐 Key Learnings

- Log data is critical for identifying both failures and attacks  
- Network protocols reveal root causes of issues  
- Attack patterns can be distinguished from normal traffic  
- Preventive controls are essential for maintaining availability  

---

## 🚀 Future Improvements

- Implement intrusion detection/prevention systems (IDS/IPS)  
- Apply rate limiting and SYN cookies  
- Configure firewall rules for abnormal traffic  
- Use load balancing and DDoS protection services  

---

## 📌 Summary

This project highlights the importance of network monitoring and cybersecurity analysis in identifying and responding to both operational failures and malicious attacks. It demonstrates the ability to interpret technical logs and translate findings into actionable security insights.

---

## 🚀 Author
Aspiring cybersecurity analyst with a multidisciplinary background in Informatics, Sociology, and Digital Marketing, focused on risk analysis, security controls, and data protection.

---


