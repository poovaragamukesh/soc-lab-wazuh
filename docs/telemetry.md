# Telemetry Architecture

## Overview

Telemetry is the foundation of the Home SOC Lab. Security data is collected from Windows endpoints and forwarded to the Wazuh SIEM for analysis and investigation.

## Data Sources

### Windows Security Logs

Collected Events:

* Event ID 4624 (Successful Logon)
* Event ID 4625 (Failed Logon)
* Account Activity
* Privilege Changes
* Authentication Events

### Windows System Logs

Collected Events:

* Service Creation
* System Errors
* Driver Events
* Startup Events

### Windows Application Logs

Collected Events:

* Application Errors
* Application Warnings

### Sysmon

Sysmon provides advanced endpoint visibility.

Collected Events:

* Event ID 1 - Process Creation
* Event ID 3 - Network Connections
* Event ID 7 - Image Loading
* Event ID 11 - File Creation
* Event ID 13 - Registry Value Set
* Event ID 22 - DNS Queries

## Data Flow

Kali Linux
→ Generates Attack Activity

Windows Endpoint
→ Security Logs
→ Sysmon Logs

Wazuh Agent
→ Collects Events

Wazuh Manager
→ Processes Events

Wazuh Dashboard
→ Displays Alerts

## Threat Hunting

Threat Hunting is used to:

* Search endpoint events
* Investigate alerts
* Validate detections
* Perform incident analysis

## Current Telemetry Coverage

* Windows Security Events
* Sysmon Telemetry
* File Integrity Monitoring
* Registry Monitoring
* Authentication Monitoring
