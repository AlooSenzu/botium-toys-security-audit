# Network Traffic Incident Report  
**Botium Toys – Cybersecurity Analysis**

---

## Overview
This report analyzes a network connectivity issue affecting access to the website **www.yummyrecipesforme.com**. Using a network protocol analyzer (tcpdump), DNS and ICMP traffic were examined to identify the root cause of the incident.

---

## Part 1: Summary of the Problem

The analysis of network traffic indicates that DNS resolution requests were unsuccessful.

- **Protocol used:** UDP (for DNS queries)  
- **Observed error:** ICMP response — *“UDP port 53 unreachable”*  
- **Affected service:** DNS (Domain Name System)  

### Key Interpretation
Port **53** is used for DNS services. The ICMP error indicates that DNS queries sent via UDP were not successfully received or processed by the DNS server.

### Conclusion
The failure to resolve the domain name prevented the browser from obtaining the IP address of the web server, making the website inaccessible.

---

## Part 2: Analysis of the Incident

### Time of Incident
The issue was first observed at approximately:  
**13:24:32** (based on tcpdump log timestamps)

---

### Incident Detection
The IT team became aware of the issue after users reported:
- Inability to access the website  
- Error message: *“destination port unreachable”*

---

### Investigation Actions
The IT team performed the following steps:
- Attempted to access the website manually  
- Captured network traffic using **tcpdump**  
- Analyzed DNS requests and ICMP responses  
- Reviewed source and destination IP addresses  
- Observed repeated failed DNS queries  

---

### Key Findings

- DNS queries were sent from:
  - **Source IP:** 192.51.100.15 (client)
  - **Destination IP:** 203.0.113.2 (DNS server)

- Queries used:
  - **UDP protocol (port 53)**

- Responses received:
  - **ICMP error messages:** “UDP port 53 unreachable”

- The failure occurred repeatedly across multiple attempts

---

### Likely Cause of the Incident

The most probable cause is that **port 53 on the DNS server is not accessible**, due to one or more of the following:

- DNS service is down or not running  
- Firewall is blocking UDP port 53  
- DNS server misconfiguration  
- Network connectivity issues to the DNS server  

---

## Impact

- Users were unable to access the website  
- DNS resolution failed, preventing web requests from completing  
- Business operations dependent on the website were disrupted  

---

## Recommended Next Steps

- Verify that the DNS server is operational  
- Check firewall rules for UDP port 53  
- Confirm DNS service configuration  
- Test DNS resolution using alternative DNS servers  
- Monitor network traffic for continued ICMP errors  

---

## Conclusion

This incident was caused by a failure in DNS communication, specifically related to UDP port 53 being unreachable. By analyzing network traffic using tcpdump, the issue was traced to a breakdown in DNS service availability or accessibility. Addressing DNS server configuration and firewall settings will be critical to restoring service.

---
