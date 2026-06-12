# Lab 01 Incident Report – Failed Login Detection

## Executive Summary

A series of failed authentication attempts were generated on the Windows 11 endpoint to validate Windows Security Log collection and Wazuh detection capabilities. The activity successfully generated Event ID 4625 and was observed through the Wazuh Threat Hunting dashboard.

## Environment

| Component      | Role               |
| -------------- | ------------------ |
| Windows 11 Pro | Victim Endpoint    |
| Ubuntu Server  | Wazuh Manager      |
| Kali Linux     | Attacker VM        |
| Sysmon         | Endpoint Telemetry |
| Wazuh Agent    | Log Collection     |

## Attack Simulation

Multiple failed logon attempts were intentionally performed using invalid credentials.

### Objective

Generate Windows Security Event ID 4625 and validate centralized detection.

## Detection Details

### Windows Event

| Field      | Value                |
| ---------- | -------------------- |
| Event ID   | 4625                 |
| Event Name | Failed Logon         |
| Source     | Windows Security Log |

### Wazuh Detection

The event was successfully collected and displayed within the Wazuh Threat Hunting dashboard.

## Investigation

The following information was reviewed:

* Username
* Timestamp
* Logon Type
* Failure Reason
* Endpoint Name

### Findings

Multiple failed authentication attempts were detected.

No successful authentication was observed during the attack simulation.

The activity is consistent with password guessing or invalid credential usage.

## MITRE ATT&CK Mapping

### TA0006 - Credential Access

### T1110.001 - Password Guessing

## Lessons Learned

* Windows Security Logs provide valuable authentication telemetry.
* Event ID 4625 is a key indicator for brute-force investigations.
* Wazuh successfully collects and displays authentication events for analysis.

## Outcome

Successfully validated failed login detection and authentication monitoring capabilities within the Home SOC Lab.
