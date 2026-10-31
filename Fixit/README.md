# Fixit

## Overview

Fixit is a hands-on Splunk challenge focused on troubleshooting log ingestion and preparing network data for security analysis.

The challenge simulates a SOC Level 2 assessment at MSSP Cybertees Ltd. The objective is to fix incorrectly parsed network logs, extract custom fields, and investigate network activity using Splunk.

## Objectives

- Fix event boundaries in incoming network logs.
- Configure Splunk to correctly parse events.
- Extract custom fields using regular expressions.
- Analyze network activity using SPL queries.
- Identify users, accessed resources, and suspicious activity.

## Topics Covered

### Event Boundary Configuration

The first phase involved correcting how Splunk separates individual events.

The `props.conf` file was configured to recognize the beginning of each network log entry using a regular expression.

The following settings were used:

- `SHOULD_LINEMERGE`: Controls whether multiple lines should be combined into a single event.
- `BREAK_ONLY_BEFORE`: Defines a pattern that identifies where a new event begins.

### Custom Field Extraction

The second phase focused on extracting meaningful information from network logs.

The following fields were extracted:

- `Username`
- `Department`
- `Domain`
- `URI`
- `SourceIP`
- `Country`

Regular expressions were used to identify and extract the relevant values from each event.

The extraction process involved configuring Splunk's `transforms.conf`, `props.conf`, and `fields.conf` files.

### Network Traffic Analysis

After fixing event boundaries and extracting the fields, the final phase involved investigating the network activity.

The analysis focused on:

- Identifying the domain accessed by users.
- Counting extracted usernames and URIs.
- Investigating visits to product pages.
- Finding URIs without file extensions.
- Identifying the most active user.
- Analyzing unique IP ranges.
- Investigating access to sensitive documents.

### SPL Queries

Splunk Processing Language (SPL) was used to analyze the collected network events.

Examples of useful commands include:

```spl
index=main
| stats count by Username
| sort -count
```

```spl
index=main
| stats count by URI
| sort -count
```

```spl
index=main "secret-document.pdf"
```

## Key Takeaways

- Correct event parsing is essential for reliable log analysis.
- Regular expressions allow analysts to extract structured information from raw logs.
- Splunk configuration files work together to control data ingestion and field extraction.
- SPL enables analysts to investigate user activity and network behavior.
- Network logs can reveal suspicious access patterns and potentially sensitive information.

## Conclusion

This challenge provided practical experience troubleshooting Splunk data ingestion and analyzing network activity.

By correcting event boundaries, extracting custom fields, and using SPL queries, it became possible to transform raw network logs into structured information suitable for security investigations.

These techniques are valuable for SOC analysts because accurate log parsing and effective data analysis are essential for identifying suspicious behavior and investigating potential security incidents.
