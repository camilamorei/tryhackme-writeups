# Splunk: Data Manipulation

## Overview

This room explores how Splunk ingests, parses, transforms, and structures machine-generated data. It focuses on using configuration files to control data processing, define event boundaries, handle multi-line logs, mask sensitive information, and extract custom fields.

## Objectives

- Understand how Splunk processes incoming data.
- Configure Splunk inputs and parsing rules.
- Work with Splunk configuration files.
- Create a custom Splunk application.
- Configure event boundaries for different log formats.
- Handle multi-line events.
- Mask sensitive information.
- Extract custom fields using regular expressions.

## Topics Covered

### Splunk Configuration Files

The room introduces several configuration files used to control how Splunk handles data:

- `inputs.conf`: Defines which data Splunk collects and how it is ingested.
- `props.conf`: Controls parsing properties, timestamps, event boundaries, and transformations.
- `transforms.conf`: Defines field extractions and data transformations.
- `fields.conf`: Defines how custom fields behave.
- `indexes.conf`: Manages index configuration and data storage.
- `outputs.conf`: Specifies destinations for forwarding data.

### Creating a Splunk App

A custom application named `DataApp` was created to organize configuration files and scripts.

The application directory contains:

- `bin`: Stores scripts and executables.
- `default`: Contains default configuration files.
- `local`: Stores custom configuration files.
- `metadata`: Contains application permissions and metadata.

### Event Boundary Configuration

Event breaking determines how Splunk separates raw log data into individual events.

Using `props.conf`, it is possible to define rules that identify where an event ends or where a new event begins.

The room covered the use of:

- `SHOULD_LINEMERGE`
- `MUST_BREAK_AFTER`
- `BREAK_ONLY_BEFORE`

Regular expressions were used to identify event boundaries in VPN and authentication logs.

### Multi-Line Event Parsing

Some log sources generate events that span multiple lines. Splunk can combine these lines into a single event using `SHOULD_LINEMERGE`.

The `BREAK_ONLY_BEFORE` setting allows Splunk to identify the beginning of a new event using a specified pattern.

### Sensitive Data Masking

The room demonstrated how to protect sensitive information, such as credit card numbers, using the `SEDCMD` setting in `props.conf`.

Regular expression substitution was used to replace sensitive digits with `X` characters, supporting compliance with PCI DSS requirements.

### Custom Field Extraction

Custom fields were extracted from VPN and purchase logs using regular expressions and Splunk configuration files.

The process involved:

- Defining extraction rules in `transforms.conf`.
- Referencing transformations in `props.conf`.
- Configuring extracted fields in `fields.conf`.

This allowed relevant information, such as usernames, servers, actions, and credit card numbers, to become searchable in Splunk.

## Key Takeaways

- Splunk configuration files control how data is collected, parsed, and transformed.
- Correct event boundaries are essential for accurate log analysis.
- Multi-line logs require appropriate parsing configurations.
- Sensitive information can be masked during data processing.
- Regular expressions are useful for extracting custom fields.
- Properly structured data improves search accuracy and security monitoring.

## Conclusion

This room provided practical experience with Splunk data manipulation, from initial ingestion to parsing, masking, and custom field extraction.

Understanding these processes is important for security analysts because properly structured and protected log data improves visibility, supports investigations, and helps identify suspicious activity.
