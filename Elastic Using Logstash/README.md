# Elastic: Using Logstash

## Overview

This room explores Logstash, an open-source data processing pipeline used to collect, transform, enrich, and forward data from different sources.

It focuses on building Logstash pipelines using input, filter, and output plugins, as well as processing Linux authentication logs and sending structured events to Elasticsearch for investigation in Kibana.

## Objectives

- Install and configure Logstash.
- Understand the input, filter, and output pipeline architecture.
- Explore different Logstash plugins.
- Process unstructured log data using Grok.
- Modify and normalize event fields.
- Ingest Linux authentication logs.
- Forward processed events to Elasticsearch.
- Investigate authentication activity in Kibana.

## Topics Covered

### Logstash Architecture

Logstash processes data through three main pipeline components:

- Input: Collects data from sources such as files, TCP, UDP, Beats, and HTTP.
- Filter: Parses, transforms, enriches, and modifies events.
- Output: Sends processed events to destinations such as Elasticsearch, files, and remote services.

### Input Plugins

Input plugins define where Logstash collects data.

Some commonly used plugins include:

- File
- Beats
- TCP
- UDP
- HTTP

The File input plugin is particularly useful for monitoring local log files.

### Filter Plugins

Filter plugins transform incoming events into structured and useful data.

Important filters explored in this room include:

- Grok: Extracts structured fields from unstructured log messages.
- Mutate: Renames, adds, removes, and modifies event fields.
- Date: Parses timestamps and updates the event timestamp.
- Prune: Removes unwanted fields.
- Drop: Discards events based on specified conditions.
- KV: Extracts key-value pairs from log messages.

### Output Plugins

Output plugins determine where processed events are sent.

Examples covered include:

- Elasticsearch
- File
- Logstash
- TCP
- RabbitMQ
- Syslog
- Stdout

The Elasticsearch output plugin allows processed events to be indexed and searched through Kibana.

### Linux Authentication Log Ingestion

The practical exercise involves collecting Linux authentication logs from:

`/var/log/auth.log`

A custom pipeline is created to:

1. Read authentication events using the File input plugin.
2. Extract structured information using Grok.
3. Parse timestamps using the Date filter.
4. Forward processed events to Elasticsearch.
5. Create a Kibana data view to investigate the collected logs.

### Log Analysis in Kibana

After ingestion, authentication events can be investigated through Kibana Discover.

This provides visibility into activities such as:

- User creation.
- Password changes.
- Authentication attempts.
- Privilege-related activity.

## Key Takeaways

- Logstash provides a flexible way to collect and process data from different sources.
- Input, filter, and output plugins form the foundation of Logstash pipelines.
- Grok is useful for extracting structured information from unstructured logs.
- Mutate and other filters help normalize event data.
- Proper timestamp parsing improves event correlation and investigation.
- Linux authentication logs provide valuable information about user and authentication activity.
- Elasticsearch and Kibana make processed logs searchable and easier to analyze.

## Conclusion

This room provided practical experience with Logstash installation, pipeline configuration, plugin usage, and log ingestion.

By building a custom pipeline for Linux authentication logs, it demonstrated how raw system logs can be transformed into structured events and made available for security monitoring and investigation.
