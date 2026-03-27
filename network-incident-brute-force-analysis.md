# 🔐 Network Incident Report: Website Compromise & Malware Redirection

## 📌 Scenario Summary
This incident involves the compromise of the website **yummyrecipesforme.com**, where users were unknowingly redirected to a malicious website (**greatrecipesforme.com**) and prompted to download malware.

---

## 🔍 Section 1: Network Protocols Identified

The following protocols were observed in the tcpdump log:

- **DNS (Domain Name System)**  
  - Used to resolve domain names to IP addresses  
  - Example: Request for `yummyrecipesforme.com` returned an IP address  

- **HTTP (Hypertext Transfer Protocol)**  
  - Used for communication between the browser and web server  
  - Observed during webpage requests and redirection  

- **TCP (Transmission Control Protocol)**  
  - Used to establish reliable connections (3-way handshake)  
  - Observed through SYN, SYN-ACK, and ACK packets  

---

## 📄 Section 2: Incident Description

### 🧠 What Happened
- A **former employee executed a brute force attack** on the administrator account  
- The attacker gained access due to:
  - Weak or default password
  - No brute-force protection mechanisms  

- Once access was gained, the attacker:
  - Logged into the admin panel  
  - Modified the website’s source code  
  - Injected malicious JavaScript  

---

### 🌐 Network Behavior Observed

1. User requests `yummyrecipesforme.com`  
2. DNS resolves the domain to an IP address  
3. Browser sends an HTTP request to the server  
4. Malicious script triggers a file download  
5. Browser is redirected to **greatrecipesforme.com**  
6. Additional DNS and HTTP requests confirm redirection  

---

### ⚠️ Indicators of Compromise

- Unexpected file download prompt  
- Redirection to an unknown domain  
- Slower system performance reported by users  
- Unauthorized changes to website code  
- Inability to access admin account  

---

### 🚨 Root Cause

The primary cause of the incident was:

> **A brute force attack exploiting weak/default administrator credentials and lack of authentication controls**

---

## 🛠️ Section 3: Recommended Remediation

### ✅ Implement Account Lockout Policies

**Description:**  
Limit the number of failed login attempts before temporarily locking the account.

**Why this works:**
- Prevents repeated password guessing attempts  
- Stops brute force attacks early  
- Reduces risk of unauthorized access  

---

### 🔐 Additional Recommended Controls

- Enforce **strong password policies**  
- Enable **multi-factor authentication (MFA)**  
- Monitor and alert on failed login attempts  
- Regularly audit admin account activity  

---

## 📊 Conclusion

This incident highlights how weak authentication controls can lead to full system compromise. The attacker leveraged a brute force attack to gain administrative access, inject malicious code, and redirect users to a harmful website.

Implementing stronger authentication controls and monitoring mechanisms is essential to prevent similar attacks in the future.

---

## ✨ Key Skills Demonstrated

- Network traffic analysis  
- Understanding of TCP/IP protocols  
- Incident investigation and documentation  
- Identification of web-based attacks  
- Security remediation planning  
