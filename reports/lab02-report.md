# Lab 02 Incident Report – File Integrity Monitoring (FIM)

## Executive Summary

A File Integrity Monitoring validation exercise was conducted to verify Wazuh's ability to detect file creation, modification, and deletion events on a monitored Windows endpoint.

## Environment

| Component      | Role               |
| -------------- | ------------------ |
| Windows 11 Pro | Monitored Endpoint |
| Wazuh Agent    | FIM Collection     |
| Wazuh Manager  | Alert Processing   |

## Attack Simulation

A file named malware_test.bat was created within the monitored Startup directory.

The file was then modified and later deleted.

### Objective

Validate File Integrity Monitoring functionality and alert generation.

## Detection Details

### File Creation

| Rule ID     | 554                      |
| ----------- | ------------------------ |
| Description | File added to the system |

### File Modification

| Rule ID     | 550                        |
| ----------- | -------------------------- |
| Description | Integrity checksum changed |

### File Deletion

| Rule ID     | 553          |
| ----------- | ------------ |
| Description | File deleted |

## Investigation

The following attributes were reviewed:

* File Name
* File Path
* Timestamp
* Agent Name
* Alert Severity

### Findings

Wazuh successfully detected all stages of file activity:

1. File Creation
2. File Modification
3. File Deletion

This demonstrates the effectiveness of File Integrity Monitoring for detecting unauthorized changes on monitored systems.

## MITRE ATT&CK Mapping

### TA0003 - Persistence

### T1547 - Boot or Logon Autostart Execution

## Lessons Learned

* Startup directories are commonly abused by malware for persistence.
* Wazuh FIM provides visibility into unauthorized file changes.
* Alerting can be used to identify suspicious endpoint activity.

## Outcome

Successfully validated Wazuh File Integrity Monitoring capabilities and demonstrated detection of file-based persistence activity.
