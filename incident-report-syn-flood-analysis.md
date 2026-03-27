# 🚨 Cybersecurity Incident Report: SYN Flood Attack Analysis

## 1. Overview
This report analyzes a network interruption affecting a company web server. Users experienced connection timeout errors when attempting to access the website.

---

## 2. Identified Attack Type
**Denial of Service (DoS) – SYN Flood Attack**

### Evidence:
- High volume of repeated TCP SYN packets
- Requests originating from a single IP address (203.0.113.0)
- Incomplete TCP handshakes
- Server resource exhaustion

---

## 3. Log Analysis Summary
Analysis of the TCP log revealed:

- Continuous SYN requests without completing the handshake  
- Normal traffic initially succeeds, then begins to fail  
- Increase in:
  - `RST, ACK` responses  
  - `504 Gateway Timeout` errors  
- Eventually, only attacker traffic remains  

**Conclusion:**  
The web server became overwhelmed and unable to process legitimate requests.

---

## 4. Technical Explanation: TCP Three-Way Handshake

A normal TCP connection is established through the following steps:

1. **SYN** → Client sends a request to initiate a connection  
2. **SYN-ACK** → Server acknowledges and reserves resources  
3. **ACK** → Client confirms and the connection is established  

### Attack Behavior:
- The attacker sends a large number of SYN requests  
- The server allocates resources for each request  
- The attacker does **not** complete the handshake  
- Resources remain tied up, exhausting server capacity  

---

## 5. Impact on the System

The attack resulted in:

- Website downtime  
- Connection timeout errors  
- Failed legitimate user requests  
- Degraded server performance  

---

## 6. Root Cause

The issue was caused by:

> A SYN flood DoS attack overwhelming the server’s connection handling capacity.

---

## 7. Mitigation Steps Taken

- Server temporarily taken offline  
- Malicious IP address blocked  

---

## 8. Recommended Improvements

To prevent future incidents:

- Implement SYN cookies  
- Apply rate limiting on incoming connections  
- Deploy IDS/IPS (Intrusion Detection/Prevention Systems)  
- Configure firewall rules for abnormal traffic patterns  
- Use load balancing and DDoS protection services  

---

## 9. Key Skills Demonstrated

- Network traffic analysis  
- TCP/IP protocol understanding  
- Wireshark log interpretation  
- Attack identification (DoS / SYN flood)  
- Incident reporting and documentation  

---

## 10. Supporting Materials

- Cybersecurity incident report template  
- Wireshark TCP/HTTP log analysis  

---

## 11. Summary

This analysis identified a SYN flood DoS attack as the root cause of the network disruption. The attack exploited the TCP handshake process to exhaust server resources, preventing legitimate users from accessing the website. Appropriate mitigation and preventive strategies were recommended to improve resilience against future attacks.
