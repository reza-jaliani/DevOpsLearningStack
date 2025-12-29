##  Contributing & Feedback

This project is part of my DevOps learning journey.  
If this phase-based structure helps you or you have ideas to improve it, feel free to open an issue or a pull request.

---

# DevOps Learning Stack

This repository is a **hands-on DevOps learning project** that started with a Dockerized Zabbix monitoring stack and gradually evolved into a **multi-phase DevOps journey**, covering containerization, monitoring, logging, automation, and infrastructure as code.

The project is intentionally built **step by step**, with each phase adding new tools, concepts, and architectural improvements.

---

##  Project Goals

- Learn DevOps concepts through **real-world practical implementation**
- Build production-like monitoring and logging stacks
- Understand how tools fit together instead of learning them in isolation
- Document each phase clearly for future reference and knowledge sharing

---

##  Project Phases Overview

###  Phase 1 – Docker & Docker Compose Fundamentals
- Docker basics (images, containers, volumes, networks)
- Docker Compose fundamentals
- Running services in containers instead of traditional VM installation

###  Phase 2 – Monitoring Stack (Zabbix + Grafana)
- Dockerized Zabbix Server, Frontend, and Database
- Grafana integration with Zabbix
- Resource monitoring for Docker containers
- Introduction to container observability concepts

###  Phase 3 – Architecture Improvements & Reverse Proxy
- Splitting a single Compose file into multiple stacks
- Nginx Reverse Proxy for service access
- Health checks for containers
- Better project structure and separation of concerns

###  Phase 4 – Logging Stack (Loki & Promtail)
- Centralized logging fundamentals
- Docker container logs collection
- Loki as log storage
- Promtail for log shipping
- Integration with Grafana for log visualization

###  Phase 5 – Infrastructure as Code & EFK Stack (Current Phase)
> **This is the active and ongoing phase**

- EFK Stack implementation:
  - **Elasticsearch** for log storage
  - **Fluentd** for log aggregation and processing
  - **Kibana** for log visualization
- Understanding log pipelines and index management
- Comparing Docker Compose vs Terraform for infrastructure provisioning
- Preparing the stack for VM or cloud deployment
- Writing technical documentation and articles based on real implementation

All previous phases have been **merged into `main`**, and only the current working phase is maintained separately.

---

##  Branch Strategy

- `main`
  - Stable branch
  - Contains the consolidated result of completed phases (1–4)
- `phase-5-terraform`
  - Active development branch
  - Focused on Terraform and EFK stack implementation

Completed phase branches have been merged and removed to keep the repository clean.

---

##  Technologies Used

- Docker & Docker Compose
- Zabbix
- Grafana
- Nginx (Reverse Proxy)
- Loki & Promtail
- Elasticsearch
- Fluentd
- Kibana
- Terraform (current phase)
- Linux (Ubuntu Server)
- Git & GitHub

---

##  Repository Structure (High-Level)

```text
.
├── docker/
│   ├── monitoring/
│   ├── logging/
│   └── reverse-proxy/
├── terraform/          # Phase 5 (IaC)
├── docs/
│   └── articles/
├── README.md


**Reza Jaliani**  
Networking → Monitoring → DevOps

_Last updated: includes Ansible and upcoming IaC strategies._
