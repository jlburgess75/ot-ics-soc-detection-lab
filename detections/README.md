# Detection Engineering

This directory contains Splunk detection rules used in the SOC detection lab.

Each detection includes:

• Detection objective  
• SPL query  
• MITRE ATT&CK mapping  
• Investigation guidance  
• Tuning considerations  

---

## Current Detections

| Detection | Purpose |
|----------|---------|
| powershell_encoded_command | Detects encoded PowerShell execution often used by attackers |
| suspicious_outbound_by_process | Detects unusual outbound connections initiated by suspicious processes |
| registry_runkey_persistence | Detects persistence via Windows Run registry keys |

---

## Detection Development Methodology

Each detection follows a structured workflow:

1. Identify attacker behavior
2. Identify telemetry source
3. Write detection logic
4. Test detection in lab environment
5. Reduce false positives
6. Document investigation steps

---

## Detection Lifecycle

---

## Tuning Notes

Detection rules must be tuned to reduce false positives.

Common tuning strategies include:

• filtering known administrative scripts  
• excluding known system processes  
• baselining normal network activity  

---

## Related Components

These detections rely on telemetry from:

• Sysmon endpoint logs  
• Windows Event Logs  
• Splunk SIEM
