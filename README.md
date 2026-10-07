# High-Performance Network Security Monitoring & Log Processing Pipeline

> Graduation Thesis project (DATN) at Post and Telecommunications Institute of Technology (PTIT). Focused on low-latency log ingestion, scalable packet processing, and centralized threat detection.

## 🚀 Overview
An enterprise-grade, distributed security monitoring and telemetry processing system designed to bridge low-level networking with software engineering. The project implements a robust log processing pipeline using the **Elastic Stack (ELK)**, deep packet inspection (**Suricata**), web application security (**ModSecurity**), and network automation primitives to process thousands of security events and network metrics per second with minimal overhead.

---

## 🛠️ Architecture & Tech Stack
* **Systems & Networking:** Linux (Ubuntu/FreeBSD), TCP/IP stack internals, pfSense Gateway, MikroTik RouterOS (SNMP telemetry).
* **Network Security & DPI:** Suricata IDS/IPS (Multi-threaded packet inspection architecture), ModSecurity WAF.
* **Data Pipelines & Ingestion:** Logstash (ETL pipelines, Grok regex parsing, multi-threaded worker tuning), Filebeat (lightweight log shipper with backpressure handling).
* **Storage & Analytics Engine:** Elasticsearch (Distributed NoSQL document store, Inverted Index optimization, Sharding/Replication).
* **Visualization & Alerting:** Kibana (KQL filtering, custom security dashboards, threshold-based automated alerting webhooks).
* **Simulation & Testing Environment:** VMware multi-zone virtualization (WAN, LAN, DMZ, Management), Kali Linux (Red Team simulation: Nmap, SQLi/XSS scripts).

---

## 💻 Software & Engineering Highlights
1. **High-Throughput Log Ingestion Pipeline:** 
   * Designed optimized Logstash input/filter pipelines leveraging custom **Grok patterns** and conditional event routing to parse unstructured raw traffic and security logs into structured JSON documents at scale.
   * Implemented efficient field normalization, GeoIP enrichment plugins, and date filters to ensure accurate temporal sequencing for security analysis.
2. **Asynchronous & Lightweight Data Shipping:** 
   * Deployed Filebeat on network gateways to monitor Suricata’s high-frequency `eve.json` output, utilizing built-in **Backpressure-sensitive spooling** to prevent packet loss during traffic spikes.
3. **Deep Packet Inspection (DPI) & Threat Telemetry:** 
   * Integrated multi-threaded Suricata engine rules to process network traffic flows, extracting application-layer metadata (HTTP, TLS, DNS) and mapping them into high-performance search indices.
4. **Automated Incident Alerting Engine:** 
   * Configured custom threshold-based detection rules in Elasticsearch/Kibana to continuously evaluate streaming log aggregations and trigger instant email/webhook notifications upon detecting anomaly spikes (e.g., automated SQL Injection or brute-force attempts).

---

## 📊 System Topology & Zones
* **WAN / Edge:** pfSense + Suricata (Inline/Passive traffic inspection & packet dropping).
* **DMZ:** Apache Web Server + ModSecurity WAF (OWASP Top 10 mitigation).
* **Management Cluster:** Centralized Elasticsearch, Logstash, and Kibana nodes handling indexing and data visualization.

---

## 👥 Authors
* **Mạch Thế Phong** (Software / Network Security Engineer)
* **Thái Anh Quân** (Co-author)
* **Instructor:** ThS. Phan Thanh Toản
