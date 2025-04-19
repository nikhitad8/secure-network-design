# 🛡️ Secure Network Design for a Mid-Size Company

This project presents a secure network architecture tailored for a mid-size enterprise. It addresses multiple user scenarios—VLAN users, remote employees using VPN, and cloud service users—while integrating comprehensive security controls at each layer.

## 📌 Objective

Design a layered, defense-in-depth network that ensures secure connectivity, authorized access, and strong threat prevention for internal, remote, and cloud-based operations.

## 🧩 Key Security Design Components

### 🔐 Remote VPN Users
- VPN with **Multi-Factor Authentication (MFA)** for access control
- VPN traffic flows through **IDS/IPS**, **external and internal firewalls**
- Suspicious traffic diverted to a **honeypot server**
- **IP-based and Certificate-based VPN rules** enhance connection security

### 🌐 General Internet Users
- Users access through **two firewall layers** (external + internal)
- **ACLs** and **whitelisting** applied for access restriction
- User accounts are **least-privilege** based on job function

### 📶 Wi-Fi Network
- Use of **multiple SSIDs** with ACL-based restrictions
- **MAC binding and authentication** to control device access

### ☁️ Cloud Services
- **IAM protocols**, **API tokens**, and **access keys** used to secure service access
- Only essential cloud services are granted access to the network

### 🖥️ Internal Network
- **MFA for LAN access**, scanned by **IDS/IPS** and firewalls
- **VLAN segregation** for each team with UTM/Firewall rules
- **MAC binding** for endpoint-device control
- **Enterprise Antivirus** for real-time protection and centralized threat management

### 🧪 Server Protection
- Includes file, mail, FTP, database, and directory servers
- Controlled access through **permissions, tokens, and IDS/IPS monitoring**

### ⚙️ Additional Security Measures
- **Unified Threat Management (UTM)**: Anti-virus, anti-spam, filtering
- **Endpoint antivirus** with centralized updates and policy enforcement
- **Remote wipe capabilities** for compromised machines
- **Mandatory security training** and **physical security protocols**

## 📰 Security Case Study

### Vanderbilt University Medical Center (VUMC) Breach (2023)
A database breach—allegedly caused by the Meow ransomware gang—highlights risks in healthcare IT infrastructure. The report evaluates root causes such as legacy systems and the growing threat of ransomware.

### Recommendations:
- Infrastructure modernization
- Stronger access controls and MFA
- Regular staff cybersecurity training

### Broader Implications:
- Patient privacy, system disruptions, and data monetization raise concerns about healthcare cybersecurity resilience.

## 📄 File Structure

```
secure-network-design/
├── network_diagram.pdf        # The network design report with diagrams and explanation
├── README.md                  # This file
```

## 🧠 Summary

This secure network design represents best practices in cybersecurity architecture, including threat detection, access control, and proactive prevention. It demonstrates layered security and policy enforcement across physical and virtual environments.