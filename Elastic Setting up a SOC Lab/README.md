# Elastic: Setting up a SOC Lab

## Overview

This room explores the Elastic Stack and its application in a Security Operations Center (SOC) environment. It provides hands-on experience deploying Elasticsearch, Kibana, Fleet Server, and Elastic Agent to build a centralized log monitoring environment.

Throughout the room, different log sources are integrated into Elastic, including Linux system logs, Apache web server logs, and custom VPN logs. The collected data is then analyzed through Kibana Discover and visualized using dashboards.

## Objectives

- Understand the core components of the Elastic Stack.
- Install and configure Elasticsearch and Kibana.
- Deploy Fleet Server and Elastic Agent.
- Collect and analyze Linux system logs.
- Integrate Apache HTTP Server logs.
- Configure custom log ingestion using an ingest pipeline.
- Parse custom logs with Grok and Date processors.
- Create dashboards and visualizations in Kibana.

## Topics Covered

### Elastic Stack Architecture

Understanding the main components of the Elastic Stack and how they work together:

- Elasticsearch
- Kibana
- Elastic Agent
- Fleet Server
- Beats
- Logstash
- Integrations

### Elasticsearch and Kibana Deployment

Installing and configuring Elasticsearch and Kibana on a Linux machine, managing services with systemd, configuring memory limits, and completing the initial setup.

### Fleet Server and Elastic Agent

Deploying Fleet Server to centrally manage Elastic Agents, configuring agent policies, and monitoring endpoint telemetry.

### Linux System Log Collection

Using the System integration to collect host-level logs and metrics, including authentication events and system activity.

### Apache HTTP Server Integration

Integrating Apache web server logs into Elastic to monitor HTTP requests, investigate access logs, and analyze user-agent information.

### Custom Log Ingestion

Building an ingest pipeline to process custom VPN logs using:

- Grok processor
- Date processor
- Custom field extraction
- Custom Logs (Filestream) integration

### Dashboards and Visualizations

Creating dashboards in Kibana using saved Discover sessions and visualizations, including:

- Pie charts
- Line charts
- Event counts
- User activity analysis
- VPN connection monitoring
- Geographic region analysis

## Key Takeaways

- Elasticsearch stores and indexes data for fast searching and analysis.
- Kibana provides the interface for searching, investigating, and visualizing logs.
- Fleet Server centralizes Elastic Agent management.
- Elastic Agent collects logs, metrics, and security telemetry from monitored hosts.
- Integrations simplify data collection from different technologies.
- Ingest pipelines allow custom log processing before indexing.
- Grok extracts structured information from unstructured log messages.
- Date processors convert custom timestamps into Elasticsearch-compatible timestamps.
- Dashboards help analysts identify activity patterns and investigate suspicious behavior.

## Conclusion

Completing this room provided practical experience building a SOC lab using the Elastic Stack.

The exercises demonstrated how to deploy and manage Elastic components, collect logs from multiple sources, process custom data, and create visualizations for security monitoring.

These skills are useful for SIEM administration, security monitoring, threat hunting, and incident investigation.
