# Linux Server Monitoring Automation Project

## Project Overview


This project is a hands-on Linux and DevOps monitoring setup built using **Prometheus**, **Node Exporter**, **Grafana**, and **Ansible**.

The project demonstrates how a Linux server can be monitored in real time by collecting system metrics such as CPU usage, memory usage, disk usage, uptime, and network traffic. The installation and configuration process is automated using Ansible playbooks.

---
=======
This project demonstrates a Linux server monitoring setup using Prometheus, Node Exporter and Grafana.

The monitoring server runs Prometheus and Grafana.  
The target Linux server runs Node Exporter.  
Prometheus collects system metrics from Node Exporter, and Grafana visualizes those metrics using dashboards.

## Tools Used

- Linux
- Prometheus
- Node Exporter
- Grafana
- Ansible
- Git
- systemd
- Firewall management

## Architecture



+--------------------------------+
| Monitoring Server              |
|                                |
| Prometheus :9090               |
| Grafana    :3000               |
+---------------+----------------+
                |
                | Scrapes metrics
                |
+---------------v----------------+
| Target Linux Server            |
|                                |
| Node Exporter :9100            |
| Linux System Metrics           |
+--------------------------------+
```

---

## Tools Used

* Linux
* Ansible
* Prometheus
* Node Exporter
* Grafana
* Git
* GitHub
* systemd

---

## Project Features

* Automated installation of Node Exporter using Ansible
* Automated installation of Prometheus using Ansible
* Automated installation of Grafana using Ansible
* Prometheus configured to scrape metrics from Node Exporter
* Grafana connected with Prometheus as a data source
* Dashboard created for Linux server monitoring
* Services managed using systemd
* Project documented with screenshots and configuration files

---

## Folder Structure


linux-monitoring-automation/
├── ansible/
│   ├── inventory.ini
│   ├── install_node_exporter.yml
│   ├── install_prometheus.yml
│   └── install_grafana.yml
│
├── prometheus/
│   └── prometheus.yml
│
├── grafana/
│   └── dashboard-queries.md
│
├── screenshots/
│   ├── prometheus-targets-up.png
│   ├── grafana-dashboard.png
│   └── node-exporter-metrics.png
│
└── README.md
```

---

## Server Roles

| Server            | Service                |
| ----------------- | ---------------------- |
| Monitoring Server | Prometheus and Grafana |
| Target Server     | Node Exporter          |

---

## Important Ports

| Service       | Port |
| ------------- | ---- |
| Prometheus    | 9090 |
| Grafana       | 3000 |
| Node Exporter | 9100 |

---

## Ansible Automation

The project includes separate Ansible playbooks for each service:

```text
ansible/install_node_exporter.yml
ansible/install_prometheus.yml
ansible/install_grafana.yml
```

These playbooks automate:

* package installation
* service user creation
* binary installation
* configuration file creation
* systemd service setup
* service enable and start process

---

## Prometheus Configuration

Prometheus is configured to scrape metrics from:

* Prometheus itself
* Node Exporter running on the target Linux server

Example target configuration:

```yaml
scrape_configs:
  - job_name: "prometheus"
    static_configs:
      - targets: ["localhost:9090"]

  - job_name: "node_exporter"
    static_configs:
      - targets: ["TARGET_SERVER_IP:9100"]
```

---

## Grafana Dashboard Metrics

The Grafana dashboard includes panels for:

* CPU usage
* Memory usage
* Disk usage
* Server uptime
* Network receive traffic
* Network transmit traffic


---

## Validation

The setup was verified using:

```bash
systemctl status node_exporter
systemctl status prometheus
systemctl status grafana-server
```

Prometheus target health was checked from the Prometheus web interface, and Grafana dashboard panels were created using PromQL queries.

---

## What I Learned

Through this project, I learned:

* how Prometheus collects Linux system metrics
* how Node Exporter exposes server metrics
* how Grafana visualizes monitoring data
* how to automate Linux service setup using Ansible
* how to manage services using systemd
* how to document a DevOps project for GitHub and resume use

---


---

## Author

Created as a hands-on DevOps and Linux administration project.


| Monitoring Server          |

                         
| Prometheus :9090           |


| Grafana    :3000           |
              

| Scrapes metrics            |


Target Linux Server     
Node Exporter :9100        


