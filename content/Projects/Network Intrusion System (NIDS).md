---
title: Network Intrusion System
tags:
  - java
  - networking
  - mysql
  - cyber-security
---
## Introduction

With the rise of advanced cyber threats such as **DDoS, malware, brute force attacks, and data exfiltration**, traditional monitoring tools often fail to provide **real-time detection and deep traffic insights**.  
This project bridges that gap by offering:

- Real-time **packet capture and analysis**
- **Database-driven traffic storage** using MySQL
- **Interactive visualization** with JavaFX
- **Automated alerts & reporting** for anomalies
---

## Problem Statement

Modern networks face challenges like:

- Increasing cyber threats & attack sophistication
- Lack of real-time visualization in legacy tools
- Expensive and complex commercial IDS solutions

***Our solution:***  
A **Java-based Network Traffic Analysis & Visualization Tool** that provides a **cost-effective, user-friendly, and intelligent** way for IT admins and cybersecurity professionals to:

- Monitor live traffic
- Detect suspicious patterns
- Store & analyze historical logs
- Generate forensic reports

---

## System Architecture

### **1. Data Collection Layer**

- **Packet Sniffer (Pcap4J)** → Captures live packets
- **Network Interface Monitor** → Detects active interfaces
- **Raw Packet Storage** → Temporary buffer for captured traffic

### **2. Data Processing Layer**

- **Packet Parser** → Extracts metadata
- **Traffic Categorizer** → Identifies protocols (TCP, UDP, HTTP, etc.)
- **Anomaly Detection Engine** → Detects DDoS, malware, brute force, port scanning, data exfiltration
- **Firewall & Blacklist Validator** → Matches against IP blocklists

### **3. Data Storage Layer**

- **MySQL Database** → Stores traffic metadata, alerts, logs
- **Firewall Rules DB** → Security rules & blacklists
- **Activity Logs** → User/system interaction history

### **4. Visualization & Reporting Layer**

- **JavaFX Dashboard** → Interactive real-time monitoring
- **Graphs & Charts** → Protocol distribution, bandwidth usage
- **Alerting System** → Real-time anomaly notifications
- **Report Generator** → Exports CSV/PDF summaries

---

## Functional Requirements

- **User Authentication** (Admin, Analyst, Viewer roles)
- **Packet Capture & Storage** with filtering options
- **Anomaly Detection** (DDoS, brute force, port scans, data exfiltration, malware traffic)
- **Database Management** (historical queries, log retrieval)
- **Real-Time Alerts & Notifications**
- **Custom Reports Export** (CSV, PDF)
- **Interactive Visualization** (graphs, pie charts, tables)

---

## Database Design

Key Entities & Attributes:

- **Users** → Authentication & roles
- **Packets** → Traffic metadata (IP, port, protocol, size)
- **Protocols** → Protocol type & description
- **Anomalies** → Detected attacks with details
- **Devices** → Network devices metadata
- **Logs & Reports** → User/system activity and generated reports

---

## Relational Schema

```bash
Users(User_ID, Email, Hashed_Password);   Activity_Logs(Log_ID, User_ID, Timestamp, Action);   Reports(Report_ID, User_ID, Report_Data, Timestamp);   Protocol(Protocol_ID, Protocol_Name, Description);   Packets(Packet_ID, Protocol_ID, Device_ID, Source_IP, Dest_IP, Packet_Size, Payload, Timestamp, Source_Port, Dest_Port);   Latency_Logs(Latency_ID, Source_IP, Dest_IP, Latency_ms, Timestamp);   AI_Anomaly_Detection(Anomaly_ID, Packet_ID, Timestamp, Category, Detection_confidence);   DDoS_Attack(Anomaly_ID, DDoS_Type, Target_IP, Attempt_Count, Request_Rate);   Brute_Force_Attack(Anomaly_ID, Target_username, Request_Rate);   Data_Exfiltration(Anomaly_ID, Source_IP, Attacker_IP);   Port_Scanning(Anomaly_ID, Open_Ports_detected);   Blacklisted_IPs(Anomaly_ID, IP_Address, Reason);   Malware_Traffic(Anomaly_ID, Malware_Name, Malicious_IP, File_Hash);   Network_Devices(Device_ID, Device_Name, Device_Type, Mac_Address, IP_Address, Location);   Bandwidth_Usage(Bandwidth_ID, Download_Speed, Upload_Speed, Timestamp, Device_ID);
```

---

## Application of Codd’s Rules

- ✅ Information Rule → All data stored in tables (MySQL)
- ✅ Guaranteed Access Rule → Queryable via table, PK, attribute
- ✅ Systematic NULL Handling → Proper NULL semantics maintained
- ✅ Comprehensive Sub-Language Rule → SQL supported for DDL/DML
- ✅ Physical Data Independence → Application unaffected by storage changes
- ❌ Logical Data Independence → Schema changes may affect app
- ❌ View Updating Rule → Limited support in MySQL
- ❌ Distribution Independence → Not fully supported by MySQL

---

## 🔮 Future Enhancements

- Integration with **SIEM tools** for enterprise-scale monitoring
- Advanced **AI/ML models** for adaptive anomaly detection
- **Cloud-based dashboard** for distributed networks
- Integration with **threat intelligence feeds**

---

## Installation & Setup

### **Prerequisites**

- Java 17+
- MySQL 8.0+
- Pcap4J library
- JavaFX SDK

### **Steps**

1. Clone the repository:

```bash
git clone https://github.com/your-username/nids-project.git cd nids-project
```

2. Import MySQL schema:    

```bash
mysql -u root -p < schema.sql
```

3. Configure database connection in `config.properties`.
4. Build and run the project:    

```bash
mvn clean install java -jar target/nids.jar
```



---

## Usage

- **Admin Login** → Manage users, rules, reports
- **Analyst Login** → Monitor traffic, review alerts
- **Viewer Login** → Read-only access to logs and visualizations
- **Dashboard** → Real-time packet graphs, anomaly alerts, bandwidth monitoring
- **Reports** → Export traffic analysis in PDF/CSV formats



A **Java + MySQL based real-time Network Intrusion Detection System (NIDS)** with interactive **JavaFX dashboard**.  
Captures live packets, stores them in a relational database, detects anomalies, and generates alerts & forensic reports.

---

## 🚀 Features

- ✅ Real-time **Packet Capture & Parsing** (Pcap4J)
    
- ✅ **Database-Driven Storage** (MySQL)
    
- ✅ **Anomaly Detection** (DDoS, malware, brute force, port scanning, data exfiltration)
    
- ✅ **Interactive Dashboard** (JavaFX) with graphs, charts, alerts
    
- ✅ **Role-based Authentication** (Admin, Analyst, Viewer)
    
- ✅ **Reports Export** (CSV, PDF, JSON)
    

---

## 📂 Project Structure

`/src   /capture       → Packet sniffing and parsing   /db            → Database handlers (MySQL)   /ui            → JavaFX dashboard   /anomaly       → Anomaly detection modules   /reporting     → Report generation utilities /schema.sql      → MySQL database schema /config.properties → Database configuration`

---

## ⚡ Installation & Setup

### Prerequisites

- Java 17+
    
- MySQL 8.0+
    
- Pcap4J library
    
- JavaFX SDK
    

### Steps

`# Clone repo git clone https://github.com/your-username/nids-project.git cd nids-project  # Setup MySQL mysql -u root -p < schema.sql  # Configure DB in config.properties  # Build & run mvn clean install java -jar target/nids.jar`

---

## 📊 Dashboard Preview

- **Live Traffic Graphs** (line chart of bandwidth, protocol pie chart)
    
- **Anomaly Alerts** (highlight suspicious traffic in real time)
    
- **Reports** (download logs in PDF/CSV)
    

---

## 🔮 Roadmap

-  Integration with **cloud-based SIEM systems**
    
-  Advanced ML-based anomaly detection
    
-  Threat intelligence feed integration
    
-  Dockerized deployment
    

---

## 👨‍💻 Authors

- Reeti Agarwal
    
- Ria Vinod
    
- Rishika Arora
    
- Sanidhya Awasti