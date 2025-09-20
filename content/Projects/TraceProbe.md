---
title: TraceProbe
tags:
  - IPDR
  - Investigation
  - ElasticSearch
  - Kafka
  - React
  - Docker
draft: false
---
**GitHub Link**: https://github.com/Reeti05Agarwal/TraceProbe 

## 📖 About The Project
 
In digital forensics, investigators often face the monumental task of sifting through millions of Internet Protocol Detail Record (IPDR) logs to find evidence. This process is manual, time-consuming, and prone to error.

**IPDR FlowAnalyzer** was built to solve this problem. It is an intelligent, real-time data processing pipeline that ingests raw IPDR logs and automatically maps communication flows between an initiator (**A-Party**) and a recipient (**B-Party**). By identifying connections and flagging anomalies in real-time, our tool provides law enforcement with actionable intelligence, significantly reducing investigation time and increasing the efficiency of digital forensic support by over 30%.

### Key Features
 
- **Log Ingestion & Normalization:** Ingests high-volume IPDR streams using Apache Kafka without data loss and Supports multiple formats (CSV, JSON, XML).
- **A-Party to B-Party Mapping:** Intelligently parses complex logs to identify and map initiator vs. recipient communications.
- **Automated Anomaly Detection:** Utilizes Apache Flink for complex event processing to flag suspicious patterns, such as connections to known malicious IPs, unusual data transfer volumes, DNS record frequency counts, Fake ID detection (geo mismatch, entropy analysis).
- **Interactive Visualization:** A user-friendly dashboard featuring:
    - **Session timelines**
    - **Protocol Analysis**
    - **Geographical Map View:** To visualize the physical locations of communicating parties.
    - **Graph-Based Network View:** To explore relationships and connections between different entities.
- **Advanced Query & Search:** A powerful search interface for investigators to filter and query specific sessions, IPs, or timeframes.
- **Data Normalization:** Handles various IPDR formats by normalizing them into a unified schema for consistent analysis.
- **Security & Compliance:**
    - **Role-Based Access Control (RBAC)**
    - **TLS encryption for secure communication**
    - **Index-level security & audit logging**

---

## 🏛️ Architecture
 
The system is designed as a distributed, scalable pipeline to handle massive data loads. [![architecture](https://private-user-images.githubusercontent.com/89301880/484723337-c53e246a-cd1a-4cb5-8d60-e66eeee98c3e.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgzODI3OTAsIm5iZiI6MTc1ODM4MjQ5MCwicGF0aCI6Ii84OTMwMTg4MC80ODQ3MjMzMzctYzUzZTI0NmEtY2QxYS00Y2I1LThkNjAtZTY2ZWVlZTk4YzNlLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNTA5MjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjUwOTIwVDE1MzQ1MFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPThmOWYwNTc0ODliYzg5YTczNjVmYTExOGUxYWNlMzVmOTJhMDYwZmNmNzRhMjJhMmNiODJhN2MwNDIwNmY5Y2YmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.0qdwB5AT6HljDPG3GcCmdFGqZK6uHm27yeVqX4cgbQ0)](https://private-user-images.githubusercontent.com/89301880/484723337-c53e246a-cd1a-4cb5-8d60-e66eeee98c3e.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgzODI3OTAsIm5iZiI6MTc1ODM4MjQ5MCwicGF0aCI6Ii84OTMwMTg4MC80ODQ3MjMzMzctYzUzZTI0NmEtY2QxYS00Y2I1LThkNjAtZTY2ZWVlZTk4YzNlLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNTA5MjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjUwOTIwVDE1MzQ1MFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPThmOWYwNTc0ODliYzg5YTczNjVmYTExOGUxYWNlMzVmOTJhMDYwZmNmNzRhMjJhMmNiODJhN2MwNDIwNmY5Y2YmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.0qdwB5AT6HljDPG3GcCmdFGqZK6uHm27yeVqX4cgbQ0)

---

## 🛠️ Tech Stack
 
This project leverages a modern, high-performance technology stack for real-time data processing and analysis.

|Component|Technology|
|---|---|
|**Data Streaming**|[![Apache Kafka](https://camo.githubusercontent.com/a2f68f00b9e7780f5c7d631b56507012bd874959fe52515151172ac734d02940/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4170616368652d4b61666b612d626c61636b2e737667)](https://camo.githubusercontent.com/a2f68f00b9e7780f5c7d631b56507012bd874959fe52515151172ac734d02940/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4170616368652d4b61666b612d626c61636b2e737667)|
|**Stream Processing**|[![Apache Flink](https://camo.githubusercontent.com/4bb3edcf046edd831b714907362b89e55f31c12cb3d63c3148bc1313d43c0058/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4170616368652d466c696e6b2d6f72616e67652e737667)](https://camo.githubusercontent.com/4bb3edcf046edd831b714907362b89e55f31c12cb3d63c3148bc1313d43c0058/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4170616368652d466c696e6b2d6f72616e67652e737667)|
|**Backend & Logic**|[![Python](https://camo.githubusercontent.com/885d1723b4e4e59292947ee6a79480e1c0bdbab728d35839f6eeb5eabd1613cc/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f507974686f6e2d332e392532422d626c75652e737667)](https://camo.githubusercontent.com/885d1723b4e4e59292947ee6a79480e1c0bdbab728d35839f6eeb5eabd1613cc/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f507974686f6e2d332e392532422d626c75652e737667)|
|**Frontend**|[![React](https://camo.githubusercontent.com/3467eb8e0dc6bdaa8fa6e979185d371ab39c105ec7bd6a01048806b74378d24c/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f52656163742d3230323332413f7374796c653d666f722d7468652d6261646765266c6f676f3d7265616374266c6f676f436f6c6f723d363144414642)](https://camo.githubusercontent.com/3467eb8e0dc6bdaa8fa6e979185d371ab39c105ec7bd6a01048806b74378d24c/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f52656163742d3230323332413f7374796c653d666f722d7468652d6261646765266c6f676f3d7265616374266c6f676f436f6c6f723d363144414642)|
|**Database**|[![Elasticsearch](https://camo.githubusercontent.com/2eeed11b47db6ff26747467f6c025a367cb19db2dbc88465f980b085da407572/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f456c61737469637365617263682d3030353537313f7374796c653d666f722d7468652d6261646765266c6f676f3d656c6173746963736561726368266c6f676f436f6c6f723d7768697465)](https://camo.githubusercontent.com/2eeed11b47db6ff26747467f6c025a367cb19db2dbc88465f980b085da407572/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f456c61737469637365617263682d3030353537313f7374796c653d666f722d7468652d6261646765266c6f676f3d656c6173746963736561726368266c6f676f436f6c6f723d7768697465) / [![PostgreSQL](https://camo.githubusercontent.com/4aed80090cf6326364d8fbc173e9d307293da717b071823b37d3514afcbcd98e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f506f737467726553514c2d3331363139323f7374796c653d666f722d7468652d6261646765266c6f676f3d706f737467726573716c266c6f676f436f6c6f723d7768697465)](https://camo.githubusercontent.com/4aed80090cf6326364d8fbc173e9d307293da717b071823b37d3514afcbcd98e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f506f737467726553514c2d3331363139323f7374796c653d666f722d7468652d6261646765266c6f676f3d706f737467726573716c266c6f676f436f6c6f723d7768697465)|
|**Containerization**|[![Docker](https://camo.githubusercontent.com/a1b0d308fd81d69d6cb59b067d1aa0d24ad250494bbe15d7e00086315e77ce59/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f636b65722d3234393645443f7374796c653d666f722d7468652d6261646765266c6f676f3d646f636b6572266c6f676f436f6c6f723d7768697465)](https://camo.githubusercontent.com/a1b0d308fd81d69d6cb59b067d1aa0d24ad250494bbe15d7e00086315e77ce59/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f636b65722d3234393645443f7374796c653d666f722d7468652d6261646765266c6f676f3d646f636b6572266c6f676f436f6c6f723d7768697465)|

---

## 🚀 Getting Started

To get a local copy up and running, follow these simple steps.
### Prerequisites

- Docker and Docker Compose
- Python 3.9+
- Node.js and npm (for the frontend)

### Installation & Setup

1. **Clone the repository:**
    
    ```shell
    git clone [https://github.com/your_username/ipdr-flowanalyzer.git](https://github.com/your_username/ipdr-flowanalyzer.git)
    cd ipdr-flowanalyzer
    ```
    
2. **Set up environment variables:**
    
    - Create a `.env` file from the `env.example`.
    - Fill in the necessary configuration details.
3. **Launch services with Docker Compose:**
    
    - This will start Kafka, Flink, and the required databases.
    
    ```shell
    docker-compose up -d
    ```
    
4. **Set up the Backend:**
    
    ```shell
    cd backend
    pip install -r requirements.txt
    python app.py
    ```
    
5. **Set up the Frontend:**
    
    ```shell
    cd frontend
    npm install
    npm start
    ```
    

---

## 📈 Usage

Once all services are running:

1. **Open the application:** Navigate to `http://localhost:3000` in your browser.
2. **Feed data into Kafka:** Use the provided Python scripts in the `/scripts` directory to simulate an IPDR log stream.
    
    ```shell
    python scripts/produce_logs.py --file data/sample_ipdr.csv
    ```
    
3. **View the Dashboard:** Watch as the dashboard populates with real-time connections, and see anomalies being flagged as they are detected by the Flink job.

[![WhatsApp Image 2025-09-01 at 20 27 04](https://private-user-images.githubusercontent.com/89301880/484722793-791298b6-d061-4238-833b-e05174675780.jpeg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgzODI3OTAsIm5iZiI6MTc1ODM4MjQ5MCwicGF0aCI6Ii84OTMwMTg4MC80ODQ3MjI3OTMtNzkxMjk4YjYtZDA2MS00MjM4LTgzM2ItZTA1MTc0Njc1NzgwLmpwZWc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTIwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkyMFQxNTM0NTBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT05MDUyZmM1MTg2NDY4YzkyMWEzNDk1ZGI1OTMwMGIzZmYyZTk0MWE3YzA1MWMwNDcxZThlY2UwOWY5YzhhYTY3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.XEJrBD8YuLQ0HR3QK8h1MZf03AP0-tnbwVsSEwETYUI)](https://private-user-images.githubusercontent.com/89301880/484722793-791298b6-d061-4238-833b-e05174675780.jpeg?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTgzODI3OTAsIm5iZiI6MTc1ODM4MjQ5MCwicGF0aCI6Ii84OTMwMTg4MC80ODQ3MjI3OTMtNzkxMjk4YjYtZDA2MS00MjM4LTgzM2ItZTA1MTc0Njc1NzgwLmpwZWc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwOTIwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDkyMFQxNTM0NTBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT05MDUyZmM1MTg2NDY4YzkyMWEzNDk1ZGI1OTMwMGIzZmYyZTk0MWE3YzA1MWMwNDcxZThlY2UwOWY5YzhhYTY3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.XEJrBD8YuLQ0HR3QK8h1MZf03AP0-tnbwVsSEwETYUI)