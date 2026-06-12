# Lab 03 – Registry Persistence Detection

## Objective

Detect registry-based persistence mechanisms using Wazuh.

## Environment

* Windows 11 Pro ARM64
* Wazuh Agent
* Wazuh Manager
* Sysmon

## Attack Simulation

A registry Run key was created:

HKCU\Software\Microsoft\Windows\CurrentVersion\Run

The key was configured to execute notepad.exe during user logon.

## Detection

Wazuh generated alerts related to registry modification and persistence activity.

Examples:

### Rule 92302

Registry entry to be executed on next logon was modified using command line application reg.exe

### Rule 92041

Value added to registry key has Base64-like pattern

## Investigation

The following information was analyzed:

* Registry Path
* Command Executed
* Endpoint Name
* Timestamp
* Associated Rule

## MITRE ATT&CK Mapping

### TA0003 - Persistence

### T1547.001 - Registry Run Keys / Startup Folder

## Outcome

Successfully validated detection of registry-based persistence techniques commonly used by malware.

## Skills Demonstrated

* Registry Monitoring
* Persistence Detection
* Threat Hunting
* Wazuh SIEM
* MITRE ATT&CK Mapping
