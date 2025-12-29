#  Linux Server Monitoring with Prometheus + Grafana (Dockerized)

This project runs a full-featured system monitoring stack using **Prometheus** and **Grafana** in Docker containers. It collects and visualizes real-time Linux server metrics including CPU, memory, disk I/O, and network activity.

##  Stack Overview

| Component    | Role                              |
|--------------|-----------------------------------|
| **Prometheus** | Metrics scraper and time-series database |
| **Node Exporter** | Collects host-level metrics from the Linux server |
| **Grafana**     | Visualizes metrics through dashboards |

##  Getting Started

### Prerequisites

- Docker
- Docker Compose

### Clone the Repository

```bash
git clone https://github.com/mikecozier/Grafana_Prometheus_Setup.git
cd Grafana_Prometheus_Setup
```

### Run the Stack

```bash
docker-compose up -d
```

Access Grafana:
```
http://localhost:3000
```

Default credentials:
- **Username:** `admin`
- **Password:** `admin`

##  Dashboards

Import the following Grafana dashboards to visualize metrics:

- **Server Metrics** (ID: `15334`)
- **Linux Node Overview** (ID: `10301`)

You can import these via Grafana's **"Import Dashboard"** feature using the IDs above.

##  Configuration

### docker-compose.yml

This stack includes:

- Prometheus (port `9090`)
- Node Exporter (port `9100`)
- Grafana (port `3000`)

### prometheus.yml

Prometheus is pre-configured to scrape metrics from:

```yaml
- job_name: 'node_exporter'
  static_configs:
    - targets: ['node-exporter:9100']
```

##  File Structure

```
.
├── docker-compose.yml
├── prometheus/
│   └── prometheus.yml
└── grafana/
    └── (provisioning + dashboards optional)
```

##  Why This?

- Fast, portable monitoring with **no manual installs**
- Live stats every 5s
- Ready-to-go dashboards
- Works great for DevOps, homelabs, and production nodes

##  Security

Don't forget to change the default Grafana password in a production environment.

---

## 📫 Contact

Built and maintained by [Michael Cozier](https://github.com/mikecozier)

---
