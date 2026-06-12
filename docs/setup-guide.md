# Home SOC Lab Setup Guide

## Overview

This guide explains how to recreate the Home SOC Lab environment used for security monitoring, threat hunting, and attack simulation.

## Lab Architecture

The environment consists of three virtual machines hosted on a MacBook Air M2 using UTM:

### Windows 11 Pro ARM64

Role: Victim Endpoint

Installed Components:

* Wazuh Agent
* Sysmon

### Ubuntu Server

Role: SIEM Server

Installed Components:

* Wazuh Manager
* Wazuh Dashboard
* Wazuh Indexer

### Kali Linux

Role: Attacker Machine

Used For:

* Network Scanning
* Attack Simulation
* Adversary Emulation

## Network Configuration

All virtual machines are configured on the same virtual subnet.

Example:

* Windows 11: 172.29.x.x
* Ubuntu Server: 172.29.x.x
* Kali Linux: 172.29.x.x

Verify connectivity using:

```bash
ping <target-ip>
```

## Wazuh Installation

Install Wazuh Manager on Ubuntu Server.

Verify services:

```bash
systemctl status wazuh-manager
systemctl status wazuh-dashboard
```

## Windows Agent Installation

Install the Wazuh Agent on Windows.

Configure:

```xml
<address>WAZUH_SERVER_IP</address>
```

Restart the service:

```powershell
net stop WazuhSvc
net start WazuhSvc
```

## Sysmon Installation

Install Sysmon using:

```powershell
sysmon -accepteula -i sysmonconfig-export.xml
```

Verify:

```powershell
Get-WinEvent -ListLog *Sysmon*
```

## Verification

Confirm:

* Agent connected
* Sysmon Operational log available
* Security logs collected
* Threat Hunting displays endpoint events

## Next Steps

Proceed with detection labs located in the labs directory.
