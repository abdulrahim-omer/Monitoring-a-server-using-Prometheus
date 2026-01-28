# Prometheus Server Monitoring

This repository provides a complete stack to monitor Linux server metrics using Prometheus and Node Exporter.

## Project Structure
- prometheus/prometheus.yml: Configuration for targets and scrape intervals.
- docker-compose.yml: Docker setup for Prometheus and Node Exporter services.

## Setup Instructions

1. Run the stack:
   ```bash
   docker-compose up -d
2.Accessing the Tools
 prometheus localhost:9090
 node exporter localhost:9100

3.Sample Queries (PromQL)
- cpu usage : 100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)
- memory usage : (node_memory_MemTotal_bytes - node_memory_MemAvailable_bytes) / 1024 / 1024 / 1024
- disk usage : 100 - (node_filesystem_avail_bytes{mountpoint="/"} / node_filesystem_size_bytes{mountpoint="/"} * 100)
