# Splunk: Exploring SPL

## Overview

This room introduces Splunk's Search Processing Language (SPL), focusing on searching, filtering, structuring, and transforming log data.

The exercises demonstrate how security analysts can use SPL to investigate Windows events, identify suspicious activity, correlate information, and detect anomalies.

## Learning Objectives

- Understand how SPL processes and filters log data.
- Use search operators and commands.
- Filter and organize search results.
- Build tables and timelines.
- Apply statistical commands to analyze events.
- Identify anomalous activity through log analysis.

## Tools and Technologies

- Splunk
- Search Processing Language (SPL)
- Windows Event Logs
- Sysmon
- VPN Logs

## Tasks

### Task 1 - Introduction

Introduced Splunk as a SIEM platform and explored its role in collecting, searching, and analyzing log data.

### Task 2 - Search & Reporting

Explored the Splunk Search & Reporting interface, including the Search Head, Time Picker, Search History, Data Summary, and Fields Sidebar.

Performed an initial search against the `windowslogs` index:

```spl
index=windowslogs
```

Learned how to inspect event counts and identify frequently occurring field values.

### Task 3 - Search Operators

Practiced SPL search operators to filter events based on specific conditions.

Topics covered:

- Relational operators: `=`, `!=`, `<`, `>`, `<=`, `>=`
- Logical operators: `AND`, `OR`, `NOT`, `IN`
- Wildcards using `*`
- CIDR notation for IP address searches
- Exact phrase searches using quotation marks
- Parentheses for grouping search conditions

Example:

```spl
index=windowslogs AccountName!=SYSTEM AccountName=James
```

### Task 4 - Filtering Results

Learned how to filter and manipulate search results using SPL commands.

Commands covered:

- `fields`: Includes or excludes specific fields.
- `dedup`: Removes duplicate values.
- `rename`: Changes field names.
- `regex`: Filters events using regular expressions.

Example:

```spl
index=windowslogs
| fields EventID User Image Hostname SourceIp
| dedup SourceIp
| rename User as Employee
```

Also practiced using regular expressions to identify executable files:

```spl
index=windowslogs
| regex Image="\.exe$"
```

### Task 5 - Structuring Results

Explored commands used to organize search results and build event timelines.

Commands covered:

- `table`: Displays selected fields in a structured table.
- `head`: Returns the first events.
- `tail`: Returns the last events.
- `sort`: Sorts results.
- `reverse`: Reverses the event order.
- `join`: Combines information from different searches.

Example:

```spl
index=windowslogs Hostname=Salena.Adam
| table _time Hostname EventID Category
| reverse
```

Also explored subsearches to correlate Sysmon process creation events with Windows Security logon events using the `LogonId` field.

### Task 6 - Transforming Commands

Studied commands that transform raw event data into statistical summaries and visualizations.

Commands covered:

- `top`: Identifies the most frequent field values.
- `rare`: Identifies the least frequent field values.
- `highlight`: Highlights selected values.
- `stats`: Calculates statistical information.
- `chart`: Creates statistical tables for visualization.
- `timechart`: Visualizes activity over time.
- `iplocation`: Enriches IP addresses with geographic information.
- `lookup`: Enriches events using external lookup tables.
- `eval`: Creates or modifies fields using expressions.

Example:

```spl
index=windowslogs
| stats count by EventID
| sort EventID
```

Geolocation example:

```spl
index=windowslogs
| iplocation SourceIp
| stats count by Country
```

### Task 7 - Anomaly Detection

Applied statistical analysis to identify unusual VPN login activity.

Investigated uncommon login locations by calculating the frequency of logins from each country for individual users.

```spl
index=vpnlogs
| eventstats count as logins_by_user by user
| eventstats count as logins_by_user_country by user src_country
| eval country_freq=logins_by_user_country/logins_by_user
| where country_freq < 0.1
| table _time user src_ip src_country country_freq
```

Also explored anomaly detection based on login hours using average login times, standard deviation, and Z-scores.

These techniques help identify unusual authentication patterns that may indicate compromised accounts or suspicious access.

### Task 8 - Conclusion

Completed the room and reviewed how SPL can be used to investigate logs, identify suspicious behavior, correlate events, and detect anomalies.

## Key Takeaways

- SPL is essential for searching and investigating large volumes of log data.
- Filtering commands help reduce unnecessary information.
- Transforming commands make it easier to identify patterns and trends.
- Event correlation helps reconstruct user and process activity.
- Statistical analysis can reveal unusual behavior that may otherwise go unnoticed.
- Anomaly detection is useful for identifying potentially compromised accounts.

## References

- [TryHackMe - Splunk: Exploring SPL](https://tryhackme.com/room/splunkexploringspl)
- [Splunk Search Reference](https://help.splunk.com/en/splunk-enterprise/search/spl-search-reference)
