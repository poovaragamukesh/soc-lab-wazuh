# Troubleshooting Guide

## Sysmon Driver Blocked

### Problem

Sysmon installation failed with:

```text
This driver has been blocked from loading
```

### Cause

Windows ARM64 environment prevented the standalone Sysmon driver from loading.

### Resolution

Used the built-in Sysmon service installation method:

```powershell
sysmon -accepteula -i sysmonconfig-export.xml
```

Confirmed service status:

```powershell
Get-Service *sysmon*
```

---

## Sysmon Events Not Appearing In Wazuh

### Problem

Sysmon Operational logs existed but were not visible in Wazuh.

### Verification

Confirmed:

```powershell
Get-WinEvent -ListLog *Sysmon*
```

Confirmed:

```powershell
Get-Content ossec.conf | Select-String Sysmon
```

Confirmed:

```powershell
Select-String ossec.log -Pattern "Sysmon"
```

### Resolution

Restarted Wazuh Agent:

```powershell
net stop WazuhSvc
net start WazuhSvc
```

Verified:

```text
Analyzing event log:
Microsoft-Windows-Sysmon/Operational
```

---

## Wazuh Agent Offline

### Verification

```powershell
Get-Service WazuhSvc
```

### Resolution

```powershell
net stop WazuhSvc
net start WazuhSvc
```

Verify dashboard connectivity.

---

## File Integrity Monitoring Not Detecting Changes

### Verification

Check:

```xml
<directories realtime="yes">
```

Verify monitored directory.

### Resolution

Create, modify, and delete files in monitored locations.

Verify alerts in Threat Hunting.

---

## Lessons Learned

* Verify telemetry before creating detections.
* Validate data flow at every layer.
* Confirm events locally before troubleshooting Wazuh.
* Document all troubleshooting activities.
