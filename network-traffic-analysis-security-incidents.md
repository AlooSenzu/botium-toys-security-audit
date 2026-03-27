# 🔍 Network Traffic Analysis & Security Incident Investigation

## 📌 Overview
This document presents two cybersecurity case studies involving network disruptions. Each case demonstrates the use of network traffic analysis to identify root causes, interpret protocol behavior, and assess the impact on business operations.

The analysis focuses on DNS failures and denial-of-service attacks using packet-level data.

---

## 🧪 Case Study 1: DNS Failure (ICMP Port Unreachable)

### 📍 Scenario
Users were unable to access a website and received the error:
> “destination port unreachable”

Network logs were captured using a packet analyzer to investigate the issue.

---

### 🔎 Log Analysis Findings
- DNS queries were sent using **UDP protocol**
- Destination port: **53 (DNS service)**
- The DNS server responded with:
  - **ICMP error messages**
  - Message: `udp port 53 unreachable`
- Multiple repeated failed attempts were observed

---

### 🧠 Root Cause
The DNS server was not listening on port 53, meaning no service was available to process DNS requests.

---

### ⚠️ Impact
- Domain name resolution failed  
- Users could not access the website  
- Business services were disrupted  

---

### 🛠️ Recommended Actions
- Ensure DNS service is running and correctly configured  
- Verify port 53 is open and accessible  
- Check firewall rules for blocked DNS traffic  
- Monitor DNS server health and availability  

---

## 🚨 Case Study 2: SYN Flood Denial of Service (DoS) Attack

### 📍 Scenario
A company web server became slow and unresponsive. Users experienced connection timeouts when attempting to access the website.

Packet analysis revealed abnormal traffic patterns.

---

### 🔎 Log Analysis Findings
- High volume of **TCP SYN requests**
- Requests originated from a single IP address: `203.0.113.0`
- Many incomplete TCP handshakes
- Increase in:
  - `RST, ACK` responses  
  - `504 Gateway Timeout` errors  
- Legitimate traffic began failing over time  

---

### 🧠 Technical Explanation: TCP Handshake

A normal TCP connection involves:

1. **SYN** → Client initiates connection  
2. **SYN-ACK** → Server acknowledges request  
3. **ACK** → Client confirms connection  

---

### 🚨 Attack Behavior
- Attacker floods the server with SYN packets  
- Server allocates resources for each request  
- Handshakes are never completed  
- Server resources become exhausted  

---

### 🧠 Root Cause
A **SYN flood DoS attack** overwhelmed the server’s ability to process incoming connections.

---

### ⚠️ Impact
- Website downtime  
- Connection timeouts  
- Failed legitimate user access  
- Server performance degradation  

---

### 🛠️ Mitigation Steps Taken
- Server temporarily taken offline  
- Malicious IP address blocked  

---

### 🔐 Recommended Improvements
- Implement SYN cookies  
- Apply rate limiting on incoming traffic  
- Deploy IDS/IPS systems  
- Configure firewall rules for abnormal traffic  
- Use load balancing and DDoS protection services  

---

## 🧠 Skills Demonstrated

- Network traffic analysis  
- TCP/IP and DNS protocol understanding  
- Packet log interpretation (Wireshark / tcpdump)  
- Incident investigation and root cause analysis  
- Identification of denial-of-service attacks  
- Cybersecurity reporting  

---

## 📌 Key Takeaways

- Log data is essential for identifying both failures and attacks  
- Network protocols reveal the root cause of issues  
- Abnormal traffic patterns indicate potential security threats  
- Proper mitigation strategies are critical for maintaining system availability  

---

## 📊 Summary

This analysis demonstrated how network traffic data can be used to diagnose both operational failures and malicious attacks. The DNS failure highlighted the importance of service availability, while the SYN flood attack illustrated how protocol misuse can disrupt business operations.

Together, these case studies showcase practical skills in cybersecurity analysis and incident investigation.
