# Lab 01 – Failed Login Detection

## Objective

Detect and investigate failed Windows authentication attempts using Wazuh SIEM.

## Environment

* Windows 11 Pro ARM64 (Victim Endpoint)
* Ubuntu Server (Wazuh Manager)
* Wazuh Agent
* Sysmon
* Kali Linux (Attacker VM)

## Attack Simulation

Multiple failed login attempts were generated on the Windows endpoint using incorrect credentials.

## Detection

Windows Security Event ID 4625 (An account failed to log on) was generated and collected by the Wazuh agent.

## Investigation

The following information was reviewed:

* Username
* Timestamp
* Logon Type
* Failure Reason
* Endpoint Name

## MITRE ATT&CK Mapping

### TA0006 - Credential Access

### T1110.001 - Password Guessing

## Outcome

Successfully validated Windows authentication monitoring and centralized log collection through Wazuh SIEM.

## Skills Demonstrated

* Windows Event Log Analysis
* Authentication Monitoring
* Security Event Investigation
* Wazuh Threat Hunting
* MITRE ATT&CK Mapping
