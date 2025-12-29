
##  Stack Overview

| Component     | Role                                     |
| ------------- | ---------------------------------------- |
| Prometheus    | Metrics scraper and time-series database |
| Node Exporter | Collects host-level Linux system metrics |
| Grafana       | Visualization and dashboarding           |

---

##  Getting Started

### Prerequisites

* Docker
* Docker Compose

### Clone the Repository

```bash
git clone https://github.com/mikecozier/Grafana_Prometheus_Setup.git
cd Grafana_Prometheus_Setup
```

### Run the Stack

```bash
docker compose up -d
```

---

##  Access the Services

* **Grafana:** [http://localhost:3000](http://localhost:3000)
* **Prometheus:** [http://localhost:9090](http://localhost:9090)
* **Node Exporter:** [http://localhost:9100/metrics](http://localhost:9100/metrics)

### Default Grafana Credentials

```
Username: admin
Password: admin
```

>  **Change the default password immediately in production environments**

---

##  Dashboards

Import the following Grafana dashboards to visualize system metrics:

* **Linux Node Overview** — Dashboard ID: `10301`
* **Server Metrics** — Dashboard ID: `15334`

Dashboards can be imported via **Grafana → Dashboards → Import** using the IDs above.

---

##  Configuration Details

### `docker-compose.yml`

This stack includes:

* Prometheus exposed on **port 9090**
* Grafana exposed on **port 3000**
* Node Exporter exposed on **port 9100**
* Persistent storage for Prometheus and Grafana data

### `prometheus.yml`

Prometheus is configured to scrape Node Exporter metrics:

```yaml
- job_name: "node_exporter"
  static_configs:
    - targets: ["192.168.1.234:9100"]
```

---

##  Project Structure

```
.
├── docker-compose.yml
├── prometheus.yml
├── grafana/
│   └── (optional provisioning / dashboards)
```

---

##  Why This Project?

* Fully containerized monitoring stack
* No manual system installs required
* Live metrics with low scrape latency
* Easily extensible for multi-host environments
* Mirrors real-world DevOps monitoring patterns

---

##  Security Notes

* Change Grafana default credentials
* Restrict exposed ports if deploying publicly
* Consider reverse proxy + TLS for production use

---

##  Contact

Built and maintained by **Michael Cozier**
DevOps | Linux | Monitoring | Automation

---


