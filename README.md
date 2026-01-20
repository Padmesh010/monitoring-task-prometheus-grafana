# Monitoring Task – Prometheus, Grafana, Node Exporter on AWS EC2

## Task Description
Install Prometheus and Grafana on a Linux EC2 machine, connect Prometheus to Grafana, and create a dashboard to view metrics.

## Tech Stack Used
- AWS EC2 (Ubuntu 22.04)
- Prometheus
- Grafana
- Node Exporter

---

## Architecture

Node Exporter → Prometheus → Grafana Dashboard

---

## Implementation Summary

1. Launched an Ubuntu 22.04 EC2 instance on AWS.
2. Installed and configured Node Exporter as a systemd service to expose system metrics.
3. Installed and configured Prometheus to scrape:
   - Itself
   - Node Exporter metrics
4. Installed Grafana and ran it as a systemd service.
5. Connected Prometheus as a data source in Grafana.
6. Imported the official Node Exporter dashboard (ID: 1860).
7. Verified live system metrics in Grafana.

---

## Verification

- Prometheus targets page shows:
  - prometheus → UP  
  - node_exporter → UP  

- Node Exporter metrics accessible at:
  - http://<EC2_PUBLIC_IP>:9100/metrics  

- Grafana dashboard shows live metrics for:
  - CPU
  - Memory
  - Disk
  - Network
  - Load
  - Uptime

---

## Screenshots

All output proof screenshots are available in the `screenshots/` folder:

- EC2 instance running  
- Prometheus UI  
- Prometheus targets (UP)  
- Node Exporter metrics  
- Grafana UI  
- Grafana data source working  
- Grafana dashboard with live metrics

---

## Final Result

A complete monitoring stack was deployed on AWS EC2 using Prometheus, Node Exporter, and Grafana with real-time visualization of Linux system metrics.

