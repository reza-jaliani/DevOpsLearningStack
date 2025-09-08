# PLPG Stack (Prometheus, Loki, Promtail, Grafana)

This project demonstrates how to deploy a **centralized monitoring and logging stack** using **Prometheus**, **Loki**, **Promtail**, and **Grafana** (PLPG) with **Docker Compose** and **Ansible**.

---

## 📖 Introduction
The PLPG stack combines metrics and logs into a unified system:

- **Prometheus**: Collects and stores time-series metrics from targets like Docker and other exporters.
- **Loki**: A log aggregation system, optimized for storing and querying logs efficiently.
- **Promtail**: An agent that ships container logs to Loki.
- **Grafana**: A visualization platform that integrates both Prometheus metrics and Loki logs into powerful dashboards.

This project is part of my DevOps learning journey. You can find the full code in the GitHub repository:  
👉 [DockerizedZabbixPrj - Phase 4 Logging](https://github.com/reza-jaliani/DockerizedZabbixPrj/tree/phase-4-logging)

---

## 📂 Project Structure
```
Phase-4-Logging/
│
├── playbooks/
│   ├── plpg/
│   │   ├── defaults/
│   │   │   └── main.yml
│   │   ├── tasks/
│   │   │   └── main.yml
│   │   └── templates/
│   │       ├── docker-compose.yml.j2
│   │       ├── prometheus.yml.j2
│   │       └── promtail-config.yml.j2
│   └── setup-plpg.yml
│
└── README.md   <-- (this file)
```

---

## 🚀 Deployment Steps

### 1. Requirements
- Docker & Docker Compose installed on target machine  
- Ansible installed on controller machine

### 2. Configure Inventory
Example `inventory/hosts`:
```ini
[plpg]
192.168.174.129 ansible_user=reza
```

### 3. Run Ansible Playbook
From the controller node:
```bash
ansible-playbook -i inventory/hosts playbooks/setup-plpg.yml --ask-become-pass
```

This will:
- Create necessary directories under `/opt/plpg`
- Deploy configuration files for Prometheus and Promtail
- Bring up the stack with Docker Compose

---

## 🔧 Prometheus Configuration
Default scrape jobs include:
- `prometheus:9090`
- `loki:3100`
- `promtail:9080`
- Docker metrics (`<your-server-ip>:9323`)

Prometheus config file path (inside container):  
`/etc/prometheus/prometheus.yml`

---

## 📊 Grafana Dashboards
Grafana is exposed at **http://<server-ip>:3000**  
Default credentials:
```
username: admin
password: admin
```

You can import dashboards from [Grafana.com](https://grafana.com/grafana/dashboards/) such as:
- Prometheus Node Exporter Full (ID: 1860)
- Docker Monitoring (ID: 193)
- Loki / Promtail Dashboards

---

## ✅ Verification

### Check Prometheus Targets
Visit: `http://<server-ip>:9090/targets`  
All targets (Prometheus, Loki, Promtail, Docker) should be **UP**.

### Check Loki API
```bash
curl http://<server-ip>:3100/ready
```
Should return `ready`.

### Check Promtail Logs
```bash
docker logs promtail
```
Promtail should report that it is watching container log files.

---

## 🤝 Contribution
This project is part of my DevOps learning journey. Feedback and suggestions are welcome!

GitHub Repository:  
👉 [DockerizedZabbixPrj - Phase 4 Logging](https://github.com/reza-jaliani/DockerizedZabbixPrj/tree/phase-4-logging)

---

## 📌 License
MIT License
