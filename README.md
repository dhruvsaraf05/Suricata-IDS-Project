# Suricata-IDS-Project
Suricata IDS implementation with custom rule detection
# Suricata IDS Project

##  Overview

This project demonstrates the implementation of **Suricata** as a Network Intrusion Detection System (IDS) in a Linux environment. The system monitors real-time network traffic and detects suspicious activity using predefined and custom rules.

---

##  Objectives

* To understand the working of an Intrusion Detection System (IDS)
* To install and configure Suricata on Linux
* To monitor network traffic in real-time
* To detect suspicious activity using rule-based detection
* To implement and test a custom ICMP detection rule

---

##  Tools & Technologies Used

* **Suricata** – Network Intrusion Detection System
* **Ubuntu Linux** – Operating System
* **VirtualBox** – Virtual environment setup
* **Nmap** – Network scanning tool
* Terminal (CLI)

---

##  Installation & Setup

### 1. Update System

```bash
sudo apt update
```

### 2. Install Suricata

```bash
sudo apt install suricata -y
```

### 3. Check Network Interface

```bash
ip a
```

---

##  Running Suricata

```bash
sudo suricata -i enp0s3
```

---

##  Update Rules

```bash
sudo suricata-update
```

---

##  Simulating Attack using Nmap

```bash
sudo apt install nmap -y
sudo nmap -sS localhost
```

---

##  Custom Rule Implementation

A custom rule was created to detect ICMP (ping) packets.

```bash
alert icmp any any -> any any (msg:"Ping Detected"; sid:1000001; rev:1;)
```

---

##  Running Suricata with Custom Rule

```bash
sudo suricata -i enp0s3 -S /etc/suricata/rules/local.rules
```

---

##  Generating Traffic

```bash
ping google.com
```

---

##  Log Analysis

```bash
cat /var/log/suricata/fast.log
```

---

##  Results

* Suricata successfully monitored network traffic
* Alerts were generated for network activity
* Custom ICMP rule successfully detected ping packets
* Logs displayed the message: **"Ping Detected"**

---

##  Conclusion

This project demonstrates the effective use of Suricata as a Network Intrusion Detection System. The implementation shows how network traffic can be monitored and analyzed in real time. The addition of custom rules highlights the flexibility of Suricata in detecting specific types of network activity.

---

##  Future Scope

* Integration with Intrusion Prevention Systems (IPS)
* Deployment in real-world enterprise environments
* Advanced threat detection using updated rule sets
* Integration with SIEM tools for better monitoring

---

