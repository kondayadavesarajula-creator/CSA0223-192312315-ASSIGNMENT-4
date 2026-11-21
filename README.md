# Computer Networks - Common Assignment (CSA0712)

**Student:** K. VAMSI KUMAR REDDY  
**Register Number:** 192312670L  
**Course:** CSA0712 - Computer Networks  
**Semester:** SEP-DEC SLOTS  
**Marks:** 100 (Internal Assessment)

---

## 📋 Assignment Overview

This repository contains the complete solution for the **Network Security and Firewall Monitoring System** Common Assignment (CSA0712).

### Problem Statement
Design and develop a Network Security and Firewall Monitoring System to demonstrate basic network security concepts. The system should:
- Monitor incoming and outgoing network traffic and identify unauthorized access attempts
- Allow administrators to configure firewall rules based on IP addresses, port numbers and protocols
- Classify network traffic as permitted or blocked
- Maintain a security log
- Detect suspicious activity (DoS, port scanning)
- Generate security alerts
- Provide a network traffic dashboard

---

## 📁 Repository Structure

```
ca/
├── network_firewall_monitor/       # Main firewall monitoring system (Python)
│   ├── __init__.py                 # Package exports
│   ├── __main__.py                 # CLI entry point
│   ├── app.py                      # Main application (run/simulate modes)
│   ├── models.py                   # Packet, Rule, Log, Alert data models
│   ├── rule_engine.py              # First-match-wins packet filter
│   ├── logger.py                   # Persistent security log (JSONL)
│   ├── detector.py                 # DoS & port-scan detection
│   ├── alerts.py                   # Alert management system
│   ├── dashboard.py                # Terminal traffic dashboard
│   ├── requirements.txt            # Dependencies
│   ├── README.md                   # Detailed project documentation
│   ├── .gitignore                  # Git ignore rules
│   └── tests/                      # Unit tests (35 passing)
│       ├── test_models.py
│       ├── test_rule_engine.py
│       └── test_logger.py
│
├── K.VAMSI KUMAR REDDY_192312670L.odt   # 6-page ODF report
├── K.VAMSI KUMAR REDDY_192312670L.pdf   # PDF version of report
├── Common Assignment CSA0712.pdf        # Original assignment PDF
│
├── Task1.pdf                         # Task 1: Data Design Review
├── Task2.pdf                         # Task 2: Nested Structures for Parcels
├── Task3.pdf                         # Task 3: Unions and Memory Layout
├── Task4.pdf                         # Task 4: Structure Forensics
├── Task5.pdf                         # Task 5: Storage Classes
├── Task6.pdf                         # Task 6: Canteen Inventory & Billing
```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.10+

### Installation
```bash
cd network_firewall_monitor
pip install -r requirements.txt
```

### Run Interactive Demo
```bash
python -m network_firewall_monitor run --steps 10
```

### Run Batch Simulation (with attacks)
```bash
python -m network_firewall_monitor simulate --count 200 --attacks
```

---

## 🔧 Features Implemented

| Feature | Description |
|---------|-------------|
| **Packet Filtering** | Rules match on src/dst IP, port, protocol (TCP/UDP/ICMP), traffic type |
| **First-Match-Wins** | Rules evaluated in priority order; implicit deny-all fallback |
| **CIDR Support** | Rules can match entire subnets (e.g., `192.168.1.0/24`) |
| **Security Logging** | Every decision logged; persisted to JSONL file |
| **Suspicious Detection** | DoS floods (>100 blocked/30s), port scans (>8 ports) |
| **Alert System** | Severity-based alerts (INFO/WARNING/CRITICAL) |
| **Traffic Dashboard** | Terminal-based live overview |
| **Traffic Simulator** | Normal traffic + attack patterns (DoS, port scan, blocked IPs) |
| **Unit Tests** | 35 tests covering all components |

---

## 📄 Reports

| File | Description |
|------|-------------|
| `K.VAMSI KUMAR REDDY_192312670L.odt` | 6-page ODF report (main submission) |
| `K.VAMSI KUMAR REDDY_192312670L.pdf` | PDF version of report |
| `Task1.pdf` – `Task6.pdf` | Individual task PDFs from C Programming Assignment 4 |

---

## 🌐 GitHub Repository

**Main Repo:** https://github.com/vamsikumarreddy029-bot/CSA07-192312670L-Common_Assignment

---

## 📚 Additional Resources

Cloned reference repositories (stored separately):
- `../konda files/CSA02-1912260532-Assignment1` — 12 tasks with code & PDFs
- `../konda files/Assignment 2/CSA02-1925260228-Assignment-2` — 7 PDF tasks

---

## ✅ Submission Checklist

- [x] Python firewall monitoring system with all required features
- [x] 6-page ODF report with name, register number, title on page 1
- [x] GitHub link included in report
- [x] Individual task PDFs (Task1.pdf – Task6.pdf)
- [x] Unit tests passing (35/35)
- [x] Interactive demo and batch simulation working

---

*Generated for CSA0712 Common Assignment — Computer Networks*