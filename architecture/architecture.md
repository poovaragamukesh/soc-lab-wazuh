# Home SOC Lab Architecture

## Components

### Kali Linux
Acts as the attacker machine used to simulate adversary activity.

### Windows 11 Pro
Acts as the victim endpoint.

Installed Components:
- Wazuh Agent
- Sysmon

### Ubuntu Server
Hosts the Wazuh Manager and Dashboard.

## Data Flow

Kali Linux
→ Generates attack activity

Windows Endpoint
→ Generates Security Logs
→ Generates Sysmon Telemetry

Wazuh Agent
→ Collects endpoint telemetry

Wazuh Manager
→ Receives and analyzes events

Wazuh Dashboard
→ Displays alerts and supports investigation
