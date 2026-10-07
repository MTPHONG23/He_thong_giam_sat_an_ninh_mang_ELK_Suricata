# Network Security Monitoring System with ELK Stack & Suricata

> Graduation Thesis project (DATN) at Post and Telecommunications Institute of Technology (PTIT).

## 📋 Overview
An enterprise-grade Network Security Monitoring (NSM) and SIEM solution designed to collect, parse, store, and visualize security events and network telemetry in real-time[cite: 4]. The system integrates perimeter defense, IDS/IPS, WAF, and centralized log management to detect and respond to cyber threats (such as Port Scanning, SQL Injection, and XSS)[cite: 4].

---

## 🏗️ System Architecture & Topology
The lab environment is structured into multi-zones using VMware Workstation[cite: 4]:
* **WAN:** Simulates the Internet environment / Attacker source[cite: 4].
* **Perimeter Defense:** **pfSense Firewall** integrated with **Suricata (IDS/IPS)** for deep packet inspection and traffic blocking[cite: 4].
* **DMZ (Demilitarized Zone):** Web Server (**Apache** & **DVWA**) protected by **ModSecurity WAF**[cite: 4].
* **LAN:** User client simulation (**Windows 7**)[cite: 4].
* **Management Network:** Centralized **ELK Stack** server for log aggregation and **MikroTik Router** for internal routing & SNMP monitoring[cite: 4].

---

## 🛠️ Tech Stack & Components
* **Firewall & Routing:** pfSense, MikroTik RouterOS[cite: 4]
* **IDS/IPS & WAF:** Suricata, ModSecurity[cite: 4]
* **Log Management & SIEM:** ELK Stack (Elasticsearch, Logstash, Kibana)[cite: 4]
* **Data Shippers:** Filebeat, Rsyslog[cite: 4]
* **Web Environment:** Apache, PHP, DVWA (Damn Vulnerable Application)[cite: 4]
* **Simulation & Testing Tools:** Kali Linux (Nmap, Hydra, Hping3)[cite: 4]

---

## ⚙️ Key Features & Implementation
1. **Centralized Log Collection:** Collects multi-source logs from pfSense, Suricata (`eve.json`), ModSecurity, Apache access logs, and MikroTik syslog/SNMP[cite: 4].
2. **Log Normalization & Parsing:** Utilizes Logstash filters and Grok patterns to structure raw logs into clean, searchable JSON documents[cite: 4].
3. **Real-time Threat Detection:** Suricata detects intrusions and triggers alerts based on signature rules, mapped directly to Elasticsearch[cite: 4].
4. **Interactive Dashboards (Kibana):** Built custom dashboards for traffic overview, top attack IPs, GeoIP location tracking, and ModSecurity SQLi/XSS breakdown[cite: 4].
5. **Automated Alerting:** Configured Kibana Watcher/Alerts to send real-time email notifications when critical attack thresholds (e.g., SQL Injection spikes) are exceeded[cite: 4].

---

## 📊 Dashboards & Results Preview
* **Suricata Monitoring:** Tracks protocol distributions, alert severities, and attacker geo-locations[cite: 4].
* **ModSecurity & WAF:** Filters attack types and monitors request URIs for web application vulnerabilities[cite: 4].
* **Network Health:** Monitors interface states and traffic flow from MikroTik routers via SNMP[cite: 4].

---

## 👥 Authors
* **Mạch Thế Phong** (Author)[cite: 4]
* **Thái Anh Quân** (Co-author)[cite: 4]
* **Instructor:** ThS. Phan Thanh Toản[cite: 4]
