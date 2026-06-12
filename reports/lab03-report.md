# Lab 03 Incident Report – Registry Persistence Detection

## Executive Summary

A registry-based persistence technique was simulated by creating a Run key within the Windows Registry. Wazuh successfully detected the registry modification and generated persistence-related alerts.

## Environment

| Component      | Role               |
| -------------- | ------------------ |
| Windows 11 Pro | Victim Endpoint    |
| Sysmon         | Endpoint Telemetry |
| Wazuh Agent    | Event Collection   |
| Wazuh Manager  | Detection Platform |

## Attack Simulation

A registry entry was created under:

HKCU\Software\Microsoft\Windows\CurrentVersion\Run

The value was configured to execute notepad.exe during user logon.

### Objective

Validate Wazuh's ability to detect registry-based persistence mechanisms.

## Detection Details

### Rule 92302

Registry entry to be executed on next logon was modified using command line application reg.exe

### Rule 92041

Value added to registry key has Base64-like pattern

## Investigation

The following information was analyzed:

* Registry Path
* Registry Value
* Command Executed
* Timestamp
* Endpoint Name
* Alert Severity

### Findings

The Run registry key was successfully modified.

Wazuh generated persistence-related alerts indicating suspicious modification of an auto-start location.

The technique closely resembles persistence methods commonly used by malware.

## MITRE ATT&CK Mapping

### TA0003 - Persistence

### T1547.001 - Registry Run Keys / Startup Folder

## Lessons Learned

* Registry Run keys are a common persistence mechanism.
* Registry monitoring is critical for detecting endpoint compromise.
* Wazuh can effectively identify suspicious modifications to auto-start locations.

## Outcome

Successfully validated registry persistence detection and demonstrated Wazuh's ability to identify persistence-related activity.
