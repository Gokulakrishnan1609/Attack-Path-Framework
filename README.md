# Attack Path Discovery and Severity Assessment Framework

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-Backend-green.svg">
  <img src="https://img.shields.io/badge/React-Frontend-blue.svg">
  <img src="https://img.shields.io/badge/Neo4j-GraphDB-brightgreen.svg">
  <img src="https://img.shields.io/badge/Cybersecurity-Offensive%20Security-red.svg">
</p>

---

# Overview

Traditional vulnerability scanners identify individual vulnerabilities but fail to explain **how attackers chain multiple weaknesses together** to compromise an enterprise network.

The **Attack Path Discovery and Severity Assessment Framework** bridges this gap by integrating multiple cybersecurity tools into a unified platform that automatically discovers attack paths, correlates vulnerabilities, and prioritizes risks using graph-based analysis.

Unlike conventional vulnerability scanners, this framework models enterprise infrastructure as an attack graph, enabling security analysts to visualize privilege escalation, lateral movement, and attack progression without performing exploitation.

---

# Key Features

- Automated Network Discovery
- Vulnerability Assessment
- Exploit Intelligence Mapping
- Privilege Escalation Analysis
- Active Directory Attack Path Analysis
- Graph-based Attack Path Discovery
- Severity Assessment
- Interactive Graph Visualization
- Secure Authentication (JWT)
- Role-Based Access Control
- Scan History Management
- Report Generation

---

# Architecture

```
                 User
                   │
             React Dashboard
                   │
           Node.js / Express API
                   │
        Correlation Engine (Core)
                   │
     ┌──────────┬────────────┬────────────┐
     │          │            │            │
   Nmap     OpenVAS    SearchSploit   LinPEAS
     │          │            │            │
     └──────────┴────────────┴────────────┘
                   │
             BloodHound
                   │
           CrackMapExec
                   │
           Attack Graph Engine
                   │
               Neo4j Graph DB
                   │
      Graph Visualization & Reports
```

---

# Workflow

```
Target IP / Domain
        │
        ▼
Network Scan (Nmap)
        │
        ▼
Vulnerability Assessment (OpenVAS)
        │
        ▼
Exploit Mapping (SearchSploit)
        │
        ▼
Privilege Escalation Analysis
        │
        ▼
Active Directory Enumeration
        │
        ▼
Correlation Engine
        │
        ▼
Attack Path Generation
        │
        ▼
Severity Ranking
        │
        ▼
Interactive Attack Graph
```

---

# Tech Stack

## Frontend

- React.js
- Axios
- Cytoscape.js

## Backend

- Node.js
- Express.js
- JWT Authentication
- Child Process API

## Database

- Neo4j
- MongoDB / JSON Storage

## Cybersecurity Tools

- Nmap
- OpenVAS
- SearchSploit
- LinPEAS
- BloodHound
- CrackMapExec

---

# Core Modules

## Authentication

- JWT Authentication
- Bcrypt Password Hashing
- Role-Based Access Control

---

## Network Scanning

- Detect Open Ports
- Service Enumeration
- OS Fingerprinting

---

## Vulnerability Assessment

- CVE Mapping
- Vulnerability Classification
- Severity Analysis

---

## Exploit Intelligence

- SearchSploit Integration
- Exploit Availability
- Reference Mapping

---

## Attack Path Discovery

The framework automatically correlates:

```
Open Port
      │
      ▼
Running Service
      │
      ▼
Known CVE
      │
      ▼
Available Exploit
      │
      ▼
Lateral Movement
      │
      ▼
Critical Asset
```

---

# Severity Assessment

The framework evaluates attack paths based on:

- Vulnerability Severity
- Exploit Availability
- Distance to Critical Assets
- Attack Complexity
- Lateral Movement Risk

---

# Graph Visualization

Interactive attack graph displaying:

- Hosts
- Services
- Vulnerabilities
- Exploits
- Attack Chains

---

# Reports

Generate reports including:

- Vulnerability Summary
- Attack Paths
- Risk Ranking
- Severity Analysis
- Remediation Recommendations

Supported formats:

- JSON
- PDF
- DOC
- TXT

---

# Security Features

- JWT Authentication
- Role-Based Access Control
- Input Validation
- Secure File Upload
- Logging & Monitoring
- Error Handling
- CORS Protection

---

# Project Structure

```
Attack-Path-Framework/

│
├── backend/
│   ├── auth/
│   ├── routes/
│   ├── scanners/
│   ├── parsers/
│   ├── correlation/
│   ├── graph/
│   ├── reports/
│   └── utils/
│
├── frontend/
│
├── database/
│
├── docs/
│   ├── architecture.png
│   ├── workflow.png
│   ├── attack-graph.png
│   ├── er-diagram.png
│   └── screenshots/
│
├── reports/
│
├── README.md
│
└── package.json
```

# Future Enhancements

- AI-powered Attack Path Prediction
- CVSS v4 Risk Scoring
- MITRE ATT&CK Mapping
- Threat Intelligence Integration
- Kubernetes Attack Graphs
- Cloud Security Support (AWS, Azure, GCP)
- Continuous Monitoring
- Docker Deployment

---

# Demo

🎥 Proof of Concept (POC)

```
https://youtu.be/YOUR_VIDEO_LINK
```

---

# Disclaimer

This project is intended **only for educational purposes, cybersecurity research, and authorized security assessments**.

The framework **does not perform automated exploitation**. It analyzes vulnerabilities and simulates potential attack paths to support defensive security operations.

---

# Author

**Gokulakrishnan P**

Cybersecurity Enthusiast | eJPT Certified | Penetration Tester | Full Stack Developer

# Project Implementation Steps

This project has:
- `backend/`: Express + Socket.IO API
- `frontend/`: React + Vite UI

## Prerequisites

- Node.js 18+ and npm
- Neo4j (default: `bolt://localhost:7687`)
- MongoDB (default: `mongodb://localhost:27017`)

## Run the project locally

1. Install backend dependencies and configure environment:

```bash
cd backend
npm install
cp .env.example .env
```

2. Update `backend/.env` with your Neo4j credentials:

```env
PORT=4000
NODE_ENV=development
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=your_password_here
NEO4J_DATABASE=neo4j
NVD_API_KEY=
SCAN_TIMEOUT_MS=120000
MOCK_MODE=false
```

3. Start the backend:

```bash
npm run dev
```

4. In a new terminal, install frontend dependencies and start the UI:

```bash
cd frontend
npm install
npm run dev
```

5. Open the app:
- Frontend: `http://localhost:5173`
- Backend API health: `http://localhost:4000/api`

## Optional production commands

### Backend
```bash
cd backend
npm start
```

### Frontend
```bash
cd frontend
npm run build
npm run preview
```
