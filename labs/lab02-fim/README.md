# Lab 02 – File Integrity Monitoring (FIM)

## Objective

Validate Wazuh File Integrity Monitoring capabilities by detecting file creation, modification, and deletion events.

## Environment

* Windows 11 Pro ARM64
* Wazuh Agent
* Wazuh Manager

## Attack Simulation

A test batch file named malware_test.bat was placed inside the Windows Startup folder.

The file was:

1. Created
2. Modified
3. Deleted

## Detection

Wazuh generated the following alerts:

### Rule 554

File added to the system

### Rule 550

Integrity checksum changed

### Rule 553

File deleted

## Investigation

The following artifacts were analyzed:

* File Name
* File Path
* Timestamp
* Agent Name
* Rule Information

## MITRE ATT&CK Mapping

### TA0003 - Persistence

### T1547 - Boot or Logon Autostart Execution

## Outcome

Successfully validated Wazuh File Integrity Monitoring functionality and demonstrated detection of unauthorized file activity.

## Skills Demonstrated

* File Integrity Monitoring
* Threat Detection
* Persistence Monitoring
* Alert Investigation
* Wazuh SIEM
